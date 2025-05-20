# 🚀 ROS2 Humble `create_client` 使用指南 🚀

ROS2 中的 `create_client` 是创建服务客户端（Client）的核心方法之一，它允许节点通过 **请求/响应** 模式与服务服务器（Server）交互。本文将详细介绍如何在 ROS2 Humble 中使用 `create_client`，并提供 Python 和 C++ 的完整示例程序。📚

---

## 🧩 什么是服务客户端（Client）？

服务客户端是 ROS2 中的 **请求方**，用于向服务服务器发送请求并接收响应。与服务服务器的通信流程如下：
1. 客户端调用服务并发送请求（Request）
2. 服务器处理请求并返回响应（Response）

服务通信适用于需要 **即时响应** 的场景，例如：
- 请求生成新海龟（`/spawn` 服务）
- 查询系统状态（`/get_system_info` 服务）

---

## 🛠️ 创建服务客户端的步骤

### 1. 确保服务接口已定义
服务接口（`.srv` 文件）需要在服务器和客户端之间共享。例如，一个简单的加法服务 `AddTwoInts.srv` 内容如下：

```srv
int64 a
int64 b
---
int64 sum
```

- `a` 和 `b` 是请求数据
- `sum` 是响应数据

### 2. 编写客户端节点
客户端节点需要：
1. 初始化 ROS2 客户端库
2. 创建节点对象
3. 定义服务客户端并发送请求
4. 处理响应结果

---

## 📦 示例程序

### ✅ Python 示例（加法服务客户端）

```python
import rclpy
from rclpy.node import Node
from example_interfaces.srv import AddTwoInts

class AddClient(Node):
    def __init__(self):
        super().__init__('add_client')
        # 创建服务客户端
        self.client = self.create_client(AddTwoInts, 'add_two_ints')
        # 等待服务可用
        while not self.client.wait_for_service(timeout_sec=1.0):
            self.get_logger().info('服务不可用，等待中...⏳')

    def send_request(self, a, b):
        self.get_logger().info(f'发送请求: a={a}, b={b}')
        request = AddTwoInts.Request()
        request.a = a
        request.b = b
        # 发送请求并等待响应
        future = self.client.call_async(request)
        rclpy.spin_until_future_complete(self, future)
        return future.result()

def main(args=None):
    rclpy.init(args=args)
    client = AddClient()
    result = client.send_request(3, 5)
    client.get_logger().info(f'收到响应: sum={result.sum} ✅')
    rclpy.shutdown()

if __name__ == '__main__':
    main()
```

#### 🧪 测试客户端
1. 启动服务节点（如前文的 `add_service` 示例）：
   ```bash
   ros2 run your_package add_service
   ```
2. 运行客户端节点：
   ```bash
   ros2 run your_package add_client
   ```
   输出结果：
   ```
   [INFO] 收到响应: sum=8 ✅
   ```

---

### ⚙️ C++ 示例（加法服务客户端）

```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"

using namespace std::chrono_literals;

class AddClient : public rclcpp::Node {
public:
    AddClient() : Node("add_client_cpp") {
        // 创建服务客户端
        client_ = this->create_client<example_interfaces::srv::AddTwoInts>("add_two_ints");
        // 等待服务可用
        while (!client_->wait_for_service(1s)) {
            RCLCPP_INFO(this->get_logger(), "服务不可用，等待中...⏳");
        }
    }

    void send_request(int64_t a, int64_t b) {
        RCLCPP_INFO(this->get_logger(), "发送请求: a=%ld, b=%ld", a, b);
        auto request = std::make_shared<example_interfaces::srv::AddTwoInts::Request>();
        request->a = a;
        request->b = b;
        // 发送请求并等待响应
        auto future = client_->async_send_request(request);
        // 阻塞直到响应返回
        if (auto response = future.get()) {
            RCLCPP_INFO(this->get_logger(), "收到响应: sum=%ld ✅", response->sum);
        } else {
            RCLCPP_ERROR(this->get_logger(), "请求失败 ❌");
        }
    }

private:
    rclcpp::Client<example_interfaces::srv::AddTwoInts>::SharedPtr client_;
};

int main(int argc, char *argv[]) {
    rclcpp::init(argc, argv);
    auto client = std::make_shared<AddClient>();
    client->send_request(10, 20);
    rclcpp::shutdown();
    return 0;
}
```

#### 🧪 测试客户端
1. 启动服务节点（如前文的 `add_service_cpp` 示例）：
   ```bash
   ros2 run your_package add_service_cpp
   ```
2. 运行客户端节点：
   ```bash
   ros2 run your_package add_client_cpp
   ```
   输出结果：
   ```
   [INFO] 收到响应: sum=30 ✅
   ```

---

## ⚠️ 注意事项

### 1. 服务名称和接口类型必须一致
- 客户端和服务端的 **服务名称** 和 **接口类型** 必须完全匹配，否则会报错。

### 2. 服务调用的异步特性
- ROS2 的服务调用默认是 **异步** 的，需使用 `spin_until_future_complete`（Python）或 `async_send_request`（C++）处理响应。

### 3. 服务不可用时的处理
- 使用 `wait_for_service` 检查服务是否可用，避免因服务未启动导致程序崩溃。

---

## 📌 总结

ROS2 的 `create_client` 提供了灵活的服务调用方式，适用于需要即时响应的场景。通过 Python 或 C++ 示例，你可以快速实现自定义服务客户端。记得根据需求选择合适的服务接口，并确保服务名称和类型匹配！

如果你喜欢这篇文章，请点赞！👍  
有问题欢迎留言讨论 💬  
--- 

> 📚 参考文档：ROS2 Humble 官方文档、CSDN 技术社区、ROS2 学习笔记