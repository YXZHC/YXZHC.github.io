# ROS2 Node 基础知识与应用

---

## 概述
ROS2（Robot Operating System 2）中的**节点（Node）**是执行特定任务的最小功能单元，是ROS2系统的核心组件。节点通过**话题（Topics）、服务（Services）和动作（Actions）**与其他节点进行通信，共同构建复杂的机器人系统。本文将介绍节点的基本概念、常用操作指令及典型应用场景。

---

## 核心概念

### 1. 节点的作用
- **功能单一性**：每个节点负责单一功能（如传感器数据采集、运动控制等）。
- **可执行文件**：节点本质是一个可执行文件（`.o`或`.exe`），通过ROS2框架进行通信。
- **通信桥梁**：节点通过发布/订阅消息、调用服务或执行动作实现与其他节点的交互。

### 2. 节点通信方式
| 通信类型       | 说明                                                                 | 常用场景                     |
|----------------|----------------------------------------------------------------------|------------------------------|
| **话题（Topics）** | 异步、一对多通信，用于实时数据传输（如传感器数据、控制指令）。       | `/cmd_vel`（运动控制）、`/scan`（激光雷达数据） |
| **服务（Services）** | 同步、请求-应答通信，用于执行特定操作（如机器人复位、参数配置）。     | `/spawn`（创建乌龟）、`/reset`（重置模拟器）     |
| **动作（Actions）** | 带反馈的长期操作，支持取消和状态监控（如移动机器人到指定位置）。     | 长距离导航、复杂任务执行       |

### 3. 节点生命周期
1. **创建**：通过编译生成可执行文件。
2. **启动**：使用`ros2 run`命令运行节点。
3. **通信**：与其他节点交换数据。
4. **终止**：手动停止或因异常退出。

---

## 常用指令及用法

### 1. 启动节点
```bash
ros2 run <package_name> <node_name>
```
**示例**：启动小乌龟模拟器节点：
```bash
ros2 run turtlesim turtlesim_node
```

### 2. 列出运行中的节点
```bash
ros2 node list
```
**输出示例**：
```
/turtlesim
```

### 3. 查看节点详细信息
```bash
ros2 node info <node_name>
```
**示例**：查看`turtlesim`节点信息：
```bash
ros2 node info /turtlesim
```
**输出内容**：
- 节点名称
- 发布的话题（如`/turtle1/pose`）
- 订阅的话题（如`/turtle1/cmd_vel`）
- 提供的服务（如`/clear`）
- 动作支持（如`/turtle1/action/rotate_absolute`）

---

### 4. 其他相关指令
#### **话题操作**
- **查看所有话题**：
  ```bash
  ros2 topic list
  ```
- **查看话题类型**：
  ```bash
  ros2 topic type /cmd_vel
  ```
- **订阅并查看话题数据**：
  ```bash
  ros2 topic echo /turtle1/pose
  ```
- **发布自定义消息**：
  ```bash
  ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 1.0}}"
  ```

#### **服务操作**
- **调用服务**：
  ```bash
  ros2 service call /spawn turtlesim/srv/Spawn "{x: 2, y: 2, theta: 0.2}"
  ```
- **查看服务类型**：
  ```bash
  ros2 service type /clear
  ```

#### **参数操作**
- **设置节点参数**：
  ```bash
  ros2 param set /turtlesim background_r 200
  ```
- **获取参数值**：
  ```bash
  ros2 param get /turtlesim background_r
  ```

---

## 应用示例：小乌龟模拟器

### 步骤1：启动节点
```bash
ros2 run turtlesim turtlesim_node
```

### 步骤2：启动遥控器节点
```bash
ros2 run turtlesim turtle_teleop_key
```

### 步骤3：查看节点列表
```bash
ros2 node list
# 输出：
# /turtlesim
# /turtle_teleop_key
```

### 步骤4：控制乌龟移动
1. 进入遥控器终端，按方向键控制乌龟移动。
2. 使用`ros2 topic echo /turtle1/pose`实时查看位置数据。

---

## 常见问题与解决

### 问题1：节点无法启动
**可能原因**：
- 软件包未正确安装。
- 节点名称或包名拼写错误。
**解决方法**：
```bash
# 检查软件包是否安装
ros2 pkg list | grep turtlesim
# 确认节点名称
ros2 run turtlesim --help
```

### 问题2：节点间通信失败
**可能原因**：
- 未在同一个ROS2会话中运行。
- 主机未配置ROS_DOMAIN_ID。
**解决方法**：
```bash
# 设置同一域ID
export ROS_DOMAIN_ID=30
```

---

## 扩展阅读
- [ROS2 Humble 官方文档](https://docs.ros.org/en/humble/Tutorials.html) 
---

通过本文，您已掌握ROS2节点的基础知识、常用指令及典型应用场景。熟练使用这些工具将帮助您高效开发和调试ROS2系统。