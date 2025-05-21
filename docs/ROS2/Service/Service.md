# 🚀 ROS2 Humble `create_service` 使用指南 🚀

ROS2 中的 `create_service` 是创建服务（Service）的核心方法之一，它允许节点通过 **请求/响应** 模式与其他节点通信。本文将详细介绍如何在 ROS2 Humble 中使用 `create_service`，并提供 Python 和 C++ 的完整示例程序。📚

---

## 🧩 什么是服务（Service）？

服务是 ROS2 中的一种 **双向通信机制**，适用于需要 **即时响应** 的场景。与话题（Topic）的单向通信不同，服务通过客户端（Client）和服务器（Server）的交互完成任务。例如：

- 请求生成新海龟（`/spawn` 服务）
- 清除海龟绘制的轨迹（`/clear` 服务）

服务的通信流程如下：
1. 客户端发送请求（Request）
2. 服务器处理请求并返回响应（Response）

---

## 🛠️ 创建服务的步骤

### 1. 定义服务类型
ROS2 使用 `.srv` 文件定义服务接口。例如，一个简单的加法服务 `AddTwoInts.srv` 内容如下：

```srv
int64 a
int64 b
---
int64 sum
```

- `a` 和 `b` 是请求数据
- `sum` 是响应数据

### 2. 编写服务节点
服务节点需要：
1. 初始化 ROS2 客户端库
2. 创建节点对象
3. 定义服务回调函数
4. 注册服务并启动节点

---

## 📦 示例程序

### ✅ Python 示例（加法服务）

```python
import rclpy
from rclpy.node import Node
from example_interfaces.srv import AddTwoInts

class AddService(Node):
    def __init__(self):
        super().__init__('add_service')
        # 创建服务
        self.service = self.create_service(
            AddTwoInts,  # 服务类型
            'add_two_ints',  # 服务名称
            self.add_callback  # 回调函数
        )
        self.get_logger().info('服务已启动！🎉')

    def add_callback(self, request, response):
        self.get_logger().info(f'收到请求: a={request.a}, b={request.b}')
        response.sum = request.a + request.b
        return response

def main(args=None):
    rclpy.init(args=args)
    node = AddService()
    rclpy.spin(node)  # 保持节点运行
    rclpy.shutdown()

if __name__ == '__main__':
    main()
```

#### 🧪 测试服务
1. 启动服务节点：
   ```bash
   ros2 run your_package add_service
   ```
2. 使用客户端调用：
   ```bash
   ros2 service call /add_two_ints example_interfaces/AddTwoInts "{a: 3, b: 5}"
   ```
   输出结果：
   ```
   result:
     sum: 8
   ```

---

### ⚙️ C++ 示例（加法服务）

```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"

using namespace std::chrono_literals;

class AddService : public rclcpp::Node {
public:
    AddService() : Node("add_service_cpp") {
        // 创建服务
        service_ = this->create_service<example_interfaces::srv::AddTwoInts>(
            "add_two_ints",
            std::bind(&AddService::add_callback, this, std::placeholders::_1, std::placeholders::_2)
        );
        RCLCPP_INFO(this->get_logger(), "服务已启动！🚀");
    }

private:
    void add_callback(
        const std::shared_ptr<example_interfaces::srv::AddTwoInts::Request> request,
        std::shared_ptr<example_interfaces::srv::AddTwoInts::Response> response
    ) {
        RCLCPP_INFO(this->get_logger(), "收到请求: a=%ld, b=%ld", request->a, request->b);
        response->sum = request->a + request->b;
    }

    rclcpp::Service<example_interfaces::srv::AddTwoInts>::SharedPtr service_;
};

int main(int argc, char *argv[]) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<AddService>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```

#### 🧪 测试服务
1. 启动服务节点：
   ```bash
   ros2 run your_package add_service_cpp
   ```
2. 使用客户端调用：
   ```bash
   ros2 service call /add_two_ints example_interfaces/AddTwoInts "{a: 10, b: 20}"
   ```
   输出结果：
   ```
   result:
     sum: 30
   ```

---

## ⚠️ 注意事项

### 1. 服务回调的执行方式
- 默认情况下，服务回调在 **互斥回调组（Mutually Exclusive Callback Group）** 中运行，即同一时间只能处理一个请求。
- 如果需要并发处理请求，需使用 **可重入回调组（Reentrant Callback Group）**。

### 2. 服务通信的适用场景
- **适合**：短时任务（如计算、查询）
- **不适合**：连续数据流（如传感器数据） → 使用话题（Topic）或动作（Action）

### 3. 服务接口定义
- 确保 `.srv` 文件已正确注册到 `package.xml` 和 `CMakeLists.txt` 中。

---

## 📌 总结

ROS2 的 `create_service` 提供了强大的服务通信能力，适用于需要即时响应的场景。通过 Python 或 C++ 示例，你可以快速实现自定义服务。记得根据需求选择合适的回调组类型，并遵循接口定义规范！

如果你喜欢这篇文章，请点赞！👍  
有问题欢迎留言讨论 💬  
--- 

> 📚 参考文档：ROS2 Humble 官方文档、CSDN 技术社区、ROS2 学习笔记