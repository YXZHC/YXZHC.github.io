# ROS2 Topic 介绍及应用

## 概述
ROS2（Robot Operating System 2）的 **Topic** 是节点（Node）之间进行异步通信的核心机制。通过 Topic，节点可以发布（Publish）或订阅（Subscribe）特定类型的消息（Message），实现一对多、多对一或多对多的通信模式。与 ROS1 相比，ROS2 的 Topic 机制基于 **DDS（Data Distribution Service）** 中间件，支持更灵活的实时性和服务质量（QoS）策略。

---

## 核心概念
### 1. 核心组件
- **Publisher（发布者）**：向 Topic 发布消息的节点。
- **Subscriber（订阅者）**：从 Topic 订阅并接收消息的节点。
- **Topic（主题）**：由名称和消息类型定义的逻辑通道，用于标识消息的传输路径。
- **QoS Policy（服务质量策略）**：控制数据传输的可靠性、持久性、历史深度等行为（如 `RELIABLE`、`BEST_EFFORT`、`HISTORY_KEEP_LAST`）。

### 2. 通信模型
ROS2 的 Topic 采用 **发布/订阅（Publish-Subscribe）模型**：
- **异步通信**：发布者与订阅者无需直接关联，发布消息后不等待确认。
- **多对多支持**：一个 Topic 可以有多个发布者和订阅者。
- **DDS 中间件**：通过 RTPS（Real-Time Publish-Subscribe）协议实现跨供应商的互操作性。

---

## Topic 通信机制
### 1. 核心流程
1. **发布者**：创建 Publisher 对象，绑定 Topic 名称和消息类型，并配置 QoS 策略。
2. **订阅者**：创建 Subscriber 对象，订阅同一 Topic 名称和消息类型，并定义回调函数处理消息。
3. **DDS 中间件**：自动匹配发布者和订阅者，通过 RTPS 协议传输数据。

### 2. 关键特性
- **无耦合性**：发布者和订阅者无需知道彼此的存在，仅需通过 Topic 名称和消息类型通信。
- **实时性**：通过 QoS 策略（如 `Deadline`、`Liveliness`）保障实时性要求。
- **灵活性**：支持自定义消息类型（如定义 `.msg` 文件）。

---

## 代码示例
### 1. 创建 Publisher 节点（C++）
```cpp
#include <chrono>
#include <memory>
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class MinimalPublisher : public rclcpp::Node {
 public:
  MinimalPublisher() : Node("minimal_publisher"), count_(0) {
    publisher_ = this->create_publisher<std_msgs::msg::String>("topic", 10);
    timer_ = this->create_wall_timer(
        500ms, std::bind(&MinimalPublisher::timer_callback, this));
  }

 private:
  void timer_callback() {
    auto message = std_msgs::msg::String();
    message.data = "Hello, world! " + std::to_string(count_++);
    RCLCPP_INFO(this->get_logger(), "Publishing: '%s'", message.data.c_str());
    publisher_->publish(message);
  }

  rclcpp::TimerBase::SharedPtr timer_;
  rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
  size_t count_;
};

int main(int argc, char *argv[]) {
  rclcpp::init(argc, argv);
  rclcpp::spin(std::make_shared<MinimalPublisher>());
  rclcpp::shutdown();
  return 0;
}
```

### 2. 创建 Subscriber 节点（Python）
```python
import rclpy
from rclpy.node import Node
from std_msgs.msg import String

class MinimalSubscriber(Node):
    def __init__(self):
        super().__init__('minimal_subscriber')
        self.subscription = self.create_subscription(
            String,
            'topic',
            self.listener_callback,
            10)
        self.subscription  # 避免被静态分析工具警告

    def listener_callback(self, msg):
        self.get_logger().info('Received: "%s"' % msg.data)

def main(args=None):
    rclpy.init(args=args)
    minimal_subscriber = MinimalSubscriber()
    rclpy.spin(minimal_subscriber)
    minimal_subscriber.destroy_node()
    rclpy.shutdown()

if __name__ == '__main__':
    main()
```

---

## 常用命令
ROS2 提供了一系列命令行工具用于调试和监控 Topic：
### 1. 查看 Topic 列表
```bash
ros2 topic list  # 列出所有 Topic
ros2 topic list -t  # 显示 Topic 及其消息类型
```

### 2. 查看 Topic 详细信息
```bash
ros2 topic info /topic_name  # 显示 Topic 的发布者、订阅者及 QoS 策略
ros2 topic info -v /topic_name  # 显示详细信息（包括 DDS 实现细节）
```

### 3. 发布与接收消息
```bash
ros2 topic pub /topic_name std_msgs/msg/String "data: 'Hello ROS2'"  # 手动发布消息
ros2 topic echo /topic_name  # 实时显示 Topic 的消息内容
```

### 4. 监控 Topic 性能
```bash
ros2 topic hz /topic_name  # 显示 Topic 的发布频率（Hz）
ros2 topic bw /topic_name  # 显示 Topic 的带宽（Byte/s）
```

---

## 应用场景
1. **传感器数据传输**：如相机、激光雷达的实时数据通过 Topic 分发。
2. **控制指令传递**：发送机器人运动指令（如 Twist 消息控制小车）。
3. **状态监控**：发布机器人状态（如电池电量、关节角度）供其他节点订阅。
4. **分布式系统协调**：多个节点通过 Topic 协同完成复杂任务（如多机协作）。

---

## ROS2 与 ROS1 的区别
| **特性**       | **ROS1**                          | **ROS2**                          |
|----------------|-----------------------------------|-----------------------------------|
| 通信机制       | 基于 ROS Master 的中心化架构      | 基于 DDS 的去中心化架构           |
| 实时性         | 依赖第三方 RTOS 改进               | 内置 QoS 策略支持硬实时场景       |
| Topic 支持     | 同步/异步通信混合                 | 纯异步通信，QoS 策略灵活配置      |
| 跨平台性       | 主要支持 Linux                    | 支持 Linux、Windows、macOS        |

---

## 总结
ROS2 的 Topic 机制通过 DDS 中间件提供了高效、灵活的异步通信能力，适用于机器人系统的传感器数据传输、控制指令分发等场景。结合 QoS 策略和丰富的命令工具，开发者可以快速构建高可靠性和实时性的机器人应用。