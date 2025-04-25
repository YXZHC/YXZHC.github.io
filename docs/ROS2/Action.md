# ROS2 Action 基础知识与应用

---

## 概述
ROS2中的**Action（动作）**是一种用于长时间运行任务的通信机制，结合了话题和服务的特点，适用于需要**过程反馈**和**可取消操作**的场景。例如机器人导航、机械臂运动控制等。Action通过**目标（Goal）、反馈（Feedback）和结果（Result）**实现客户端与服务端的交互，是ROS2系统中高级任务管理的核心工具。

---

## 核心概念

### 1. Action的组成部分
| 组件       | 作用                                                                 | 示例场景                     |
|------------|----------------------------------------------------------------------|------------------------------|
| **目标（Goal）** | 客户端发送的指令，定义任务目标（如旋转角度、移动距离）。               | 旋转乌龟到指定角度           |
| **反馈（Feedback）** | 服务端实时返回任务执行状态（如当前进度、剩余时间）。                 | 旋转过程中返回剩余角度       |
| **结果（Result）** | 任务完成后返回最终状态（成功、失败、取消等）。                       | 旋转完成后返回实际旋转角度   |

### 2. Action与话题/服务的区别
| 特性                | Action                          | 话题（Topics）                | 服务（Services）             |
|---------------------|---------------------------------|-------------------------------|-----------------------------|
| **通信模式**         | 同步+异步（目标发送同步，反馈异步） | 异步，一对多                   | 同步，请求-应答             |
| **反馈机制**         | 支持实时反馈（Feedback）         | 无反馈                        | 仅最终响应                  |
| **可取消性**         | 可中途取消（通过Cancel Goal）     | 无法取消                      | 无取消机制                  |
| **适用场景**         | 长时任务（导航、机械臂控制）      | 实时数据传输（传感器数据）     | 短时操作（复位、参数设置）   |

### 3. Action生命周期
1. **发送目标**：客户端通过`send_goal`发送指令。
2. **执行任务**：服务端开始执行目标，持续发送反馈。
3. **反馈更新**：客户端通过订阅反馈话题获取进度。
4. **结果返回**：任务完成后返回结果状态（成功、失败、取消）。

---

## 常用指令及用法

### 1. 查看系统中所有Action
```bash
ros2 action list
```
**示例输出**：
```
/turtle1/rotate_absolute
```

### 2. 查看Action的详细信息
```bash
ros2 action info <action_name>
```
**示例**：查看乌龟旋转Action的信息：
```bash
ros2 action info /turtle1/rotate_absolute
```
**输出内容**：
- 消息类型：`turtlesim/action/RotateAbsolute`
- 支持的目标、反馈和结果字段。

### 3. 发送Action目标
```bash
ros2 action send_goal <action_name> <action_type> "{参数}"
```
**示例**：让乌龟旋转到180度：
```bash
ros2 action send_goal /turtle1/rotate_absolute turtlesim/action/RotateAbsolute "{theta: 3.14}"
```
**带反馈的发送**：
```bash
ros2 action send_goal /turtle1/rotate_absolute turtlesim/action/RotateAbsolute "{theta: -1.57}" --feedback
```

### 4. 其他相关指令
#### **查看Action消息类型**
```bash
ros2 interface show <action_type>
```
**示例**：查看`RotateAbsolute`的Action结构：
```bash
ros2 interface show turtlesim/action/RotateAbsolute
```
**输出**：
```yaml
float32 theta  # 目标角度
---
float32 delta  # 实际旋转角度
---
float32 remaining  # 剩余角度
```

#### **取消正在进行的Action目标**
```bash
ros2 action cancel <action_name> <goal_id>
```
**示例**：取消目标ID为`f8db8f44410849eaa93d3feb747dd444`的Action：
```bash
ros2 action cancel /turtle1/rotate_absolute f8db8f44410849eaa93d3feb747dd444
```

---

## 应用示例：小乌龟旋转控制

### 步骤1：启动小乌龟仿真
```bash
ros2 run turtlesim turtlesim_node
```

### 步骤2：发送旋转Action
```bash
ros2 action send_goal /turtle1/rotate_absolute turtlesim/action/RotateAbsolute "{theta: 1.57}" --feedback
```
**终端输出**：
```
Waiting for an action server to become available...
Sending goal: theta: 1.57
Goal accepted with ID: e6092c831f994afda92f0086f220da27
Feedback: remaining: 1.5680003166198732
Feedback: remaining: 0.0
Result: delta: 1.57
Goal finished with status: SUCCEEDED
```

### 步骤3：中途取消Action
```bash
ros2 action cancel /turtle1/rotate_absolute e6092c831f994afda92f0086f220da27
```

---

## 自定义Action接口开发

### 1. 定义Action接口文件（*.action）
```bash
# MoveCircle.action
float32 radius  # 目标半径
---
float32 distance # 实际移动距离
---
float32 progress # 当前进度百分比
```

### 2. 实现Action服务器（Server）
```python
# action_server.py
from action_msgs.msg import GoalStatus
from your_package.action import MoveCircle

def execute_callback(goal_handle):
    # 任务逻辑（如控制乌龟画圈）
    while not done:
        # 发布反馈
        feedback = MoveCircle.Feedback()
        feedback.progress = current_progress
        goal_handle.publish_feedback(feedback)
    # 返回结果
    result = MoveCircle.Result()
    result.distance = total_distance
    goal_handle.succeed()
    return result
```

### 3. 实现Action客户端（Client）
```python
# action_client.py
from your_package.action import MoveCircle

async def send_goal():
    action_client = ActionClient(node, MoveCircle, 'move_circle')
    goal_msg = MoveCircle.Goal()
    goal_msg.radius = 0.5
    send_goal_future = action_client.send_goal_async(goal_msg)
    # 等待结果并处理反馈
```

---

## 常见问题与解决

### 问题1：Action未被接受
**可能原因**：
- 目标参数格式错误。
- Action服务器未启动。
**解决方法**：
```bash
# 检查服务器是否运行
ros2 node list | grep turtlesim

# 确认Action名称和类型
ros2 action list
ros2 action info /turtle1/rotate_absolute
```

### 问题2：反馈未显示
**可能原因**：
- 未添加`--feedback`参数。
- 反馈话题未正确订阅。
**解决方法**：
```bash
# 重新发送目标并添加反馈参数
ros2 action send_goal ... --feedback
```

---

## 扩展阅读
- [ROS2 Humble 官方文档](https://docs.ros.org/en/humble/Tutorials.html) 
---

通过本文，您已掌握ROS2 Action的核心概念、常用指令及开发实践。结合小乌龟案例和自定义接口开发，能够高效实现复杂任务的流程控制与状态管理。
