## 一、ROS2 Service 概述

### 1.1 什么是 Service？
- **通信模型**：基于 **客户端-服务器（Client-Server）** 模型，实现 **请求-响应（Request-Response）** 机制。
- **特点**：
  - **同步通信**：客户端发送请求后会阻塞，直到收到服务端的响应。
  - **一对一关系**：同一服务名称只能有一个服务端，但可被多个客户端调用。
  - **适用场景**：配置参数、单次任务（如清屏、生成新海龟）等对实时性要求较高的操作。

### 1.2 与 Topic 的区别
| **特性**         | **Topic**                | **Service**              |
|------------------|--------------------------|--------------------------|
| **通信模式**     | 发布-订阅（一对多/多对多）| 请求-响应（一对一）       |
| **数据流**       | 持续发布数据             | 按需请求数据             |
| **同步性**       | 异步                     | 同步                     |
| **服务端数量**   | 无限制                   | 仅允许一个服务端         |

---

## 二、Service 核心概念

### 2.1 Service 生命周期
1. **服务端**：等待客户端请求，处理请求并返回响应。
2. **客户端**：主动发起请求，等待并处理服务端的响应。

### 2.2 自定义 Service 接口
#### 2.2.1 定义 `.srv` 文件
```bash
# 示例：AddInts.srv
int32 a
int32 b
---
int32 sum
```
- **格式**：
  - `---` 前为 **请求（Request）** 字段。
  - `---` 后为 **响应（Response）** 字段。

#### 2.2.2 配置功能包
1. **创建功能包目录结构**：
   ```bash
   mkdir -p my_package/srv
   touch my_package/srv/AddInts.srv
   ```
2. **修改 `package.xml`**：
   ```xml
   <depend>rosidl_default_generators</depend>
   ```
3. **修改 `CMakeLists.txt`**：
   ```cmake
   find_package(rosidl_default_generators REQUIRED)
   rosidl_generate_interfaces(${PROJECT_NAME}
     "srv/AddInts.srv"
   )
   ```

---

## 三、Service 实现步骤

### 3.1 服务端（Server）实现
#### 3.1.1 C++ 示例代码
```cpp
#include "rclcpp/rclcpp.hpp"
#include "my_package/srv/addints.hpp"

class ServiceServer : public rclcpp::Node {
public:
  ServiceServer() : Node("service_server") {
    service_ = this->create_service<my_package::srv::AddInts>(
      "add_two_ints",
      std::bind(&ServiceServer::add, this, std::placeholders::_1, std::placeholders::_2)
    );
  }

private:
  void add(
    const std::shared_ptr<my_package::srv::AddInts::Request> request,
    std::shared_ptr<my_package::srv::AddInts::Response> response
  ) {
    response->sum = request->a + request->b;
    RCLCPP_INFO(this->get_logger(), "Sum: %d + %d = %d", request->a, request->b, response->sum);
  }

  rclcpp::Service<my_package::srv::AddInts>::SharedPtr service_;
};

int main(int argc, char **argv) {
  rclcpp::init(argc, argv);
  auto node = std::make_shared<ServiceServer>();
  rclcpp::spin(node);
  rclcpp::shutdown();
  return 0;
}
```

#### 3.1.2 Python 示例代码
```python
import rclpy
from rclpy.node import Node
from my_package.srv import AddInts

class ServiceServer(Node):
    def __init__(self):
        super().__init__('service_server')
        self.srv = self.create_service(AddInts, 'add_two_ints', self.add_callback)

    def add_callback(self, request, response):
        response.sum = request.a + request.b
        self.get_logger().info(f"Sum: {request.a} + {request.b} = {response.sum}")
        return response

def main(args=None):
    rclpy.init(args=args)
    server = ServiceServer()
    rclpy.spin(server)
    rclpy.shutdown()

if __name__ == '__main__':
    main()
```

### 3.2 客户端（Client）实现
#### 3.2.1 C++ 示例代码
```cpp
#include "rclcpp/rclcpp.hpp"
#include "my_package/srv/addints.hpp"

class ServiceClient : public rclcpp::Node {
public:
  ServiceClient() : Node("service_client") {
    client_ = this->create_client<my_package::srv::AddInts>("add_two_ints");
    while (!client_->wait_for_service(std::chrono::seconds(1))) {
      if (!rclcpp::ok()) {
        RCLCPP_ERROR_STREAM(this->get_logger(), "Service unavailable");
        rclcpp::shutdown();
        return;
      }
    }
    call_service();
  }

private:
  void call_service() {
    auto request = std::make_shared<my_package::srv::AddInts::Request>();
    request->a = 5;
    request->b = 3;
    client_->async_send_request(request, std::bind(&ServiceClient::response_callback, this, _1));
  }

  void response_callback(const rclcpp::Client<my_package::srv::AddInts>::SharedFuture future) {
    auto response = future.get();
    RCLCPP_INFO(this->get_logger(), "Result: %d", response->sum);
  }

  rclcpp::Client<my_package::srv::AddInts>::SharedPtr client_;
};

int main(int argc, char **argv) {
  rclcpp::init(argc, argv);
  auto node = std::make_shared<ServiceClient>();
  rclcpp::spin(node);
  rclcpp::shutdown();
  return 0;
}
```

#### 3.2.2 Python 示例代码
```python
import rclpy
from rclpy.node import Node
from my_package.srv import AddInts

class ServiceClient(Node):
    def __init__(self):
        super().__init__('service_client')
        self.cli = self.create_client(AddInts, 'add_two_ints')
        while not self.cli.wait_for_service(timeout_sec=1.0):
            self.get_logger().info('Service not available, waiting again...')
        self.request = AddInts.Request()
        self.request.a = 5
        self.request.b = 3
        self.future = self.cli.call_async(self.request)

    def send_request(self):
        while rclpy.ok():
            rclpy.spin_once(self)
            if self.future.done():
                try:
                    response = self.future.result()
                except Exception as e:
                    self.get_logger().info('Service call failed %r' % (e,))
                else:
                    self.get_logger().info(f'Result: {response.sum}')
                break

def main(args=None):
    rclpy.init(args=args)
    client = ServiceClient()
    client.send_request()
    rclpy.shutdown()

if __name__ == '__main__':
    main()
```

---

## 四、常用命令行工具

### 4.1 列出所有 Service
```bash
ros2 service list
# 输出示例：
# /add_two_ints
# /clear
# /reset
```

### 4.2 查看 Service 类型
```bash
ros2 service type /add_two_ints
# 输出：
# my_package/srv/AddInts
```

### 4.3 查看 Service 接口定义
```bash
ros2 interface show my_package/srv/AddInts
# 输出：
# int32 a
# int32 b
# ---
# int32 sum
```

### 4.4 调用 Service
```bash
ros2 service call /add_two_ints my_package/srv/AddInts "{a: 5, b: 3}"
# 响应示例：
# response:
#   sum: 8
```

---

## 五、应用场景与最佳实践

### 5.1 典型应用场景
- **参数配置**：动态修改节点参数（如清空海龟画布 `/clear`）。
- **单次操作**：生成新海龟 `/spawn`、重置位置 `/reset`。
- **设备控制**：打开/关闭传感器、执行特定动作。

### 5.2 注意事项
1. **服务唯一性**：确保同一服务名称仅有一个服务端实例。
2. **超时处理**：客户端需处理服务不可用或响应超时的情况。
3. **数据格式**：请求和响应字段需严格匹配 `.srv` 定义。

---

## 六、与 Action 的对比
| **特性**         | **Service**                | **Action**                |
|------------------|---------------------------|---------------------------|
| **通信模式**     | 请求-响应（同步）         | 目标-反馈-结果（异步）    |
| **反馈机制**     | 无进度反馈                | 支持中间反馈（Feedback）  |
| **适用场景**     | 简单单次操作              | 长期任务（如导航、抓取）  |

---

## 七、扩展阅读
- [ROS2 Humble 官方文档](https://docs.ros.org/en/humble/Tutorials.html) 

> **提示**：实际开发中，建议结合 `ros2 service list` 和 `ros2 interface show` 快速定位服务接口定义，提升开发效率。