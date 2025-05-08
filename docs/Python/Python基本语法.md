# 🚀 Python 基本语法指南

欢迎来到 Python 世界！本文将带你快速了解 Python 的基本语法，涵盖变量、数据类型、控制结构、函数、模块、异常处理等核心内容。学习完这篇文档后，你将能编写简单的 Python 程序啦！😊

---

## 1. 变量与赋值

Python 的变量无需声明类型，直接赋值即可使用。变量名可由字母、数字和下划线组成，不能以数字开头。

```python
# 示例：变量赋值
name = "Alice"  # 字符串
age = 30        # 整数
height = 1.75   # 浮点数
is_student = False  # 布尔值

print(f"Name: {name}, Age: {age}, Height: {height}, Student: {is_student}")
```

💡 **小贴士**：
- 变量名推荐使用小写字母和下划线（`snake_case`）。
- Python 是动态类型语言，变量类型会自动推断。

---

## 2. 数据类型

Python 支持多种内置数据类型，以下是常见的几种：

### 2.1 基础数据类型

| 类型       | 示例              | 说明                  |
|------------|-------------------|-----------------------|
| 整数       | `x = 10`          | 支持正负整数          |
| 浮点数     | `y = 3.14`        | 带小数点的数字        |
| 字符串     | `s = "Hello"`     | 用单引号或双引号包裹  |
| 布尔值     | `flag = True`     | `True` 或 `False`     |

### 2.2 集合类型

| 类型       | 示例                          | 说明                  |
|------------|-------------------------------|-----------------------|
| 列表       | `lst = [1, 2, 3]`             | 可变有序序列          |
| 元组       | `tup = (1, 2, 3)`             | 不可变有序序列        |
| 字典       | `dict = {"name": "Alice"}`    | 键值对存储            |
| 集合       | `set = {1, 2, 3}`             | 无序不重复元素        |

```python
# 示例：集合类型操作
fruits = ["apple", "banana", "cherry"]  # 列表
coordinates = (10, 20)                   # 元组
person = {"name": "Alice", "age": 30}    # 字典
unique_numbers = {1, 2, 3, 3, 4}         # 集合

print("Fruits:", fruits)
print("Coordinates:", coordinates)
print("Person:", person)
print("Unique Numbers:", unique_numbers)
```

---

## 3. 控制结构

### 3.1 条件语句

使用 `if-elif-else` 判断条件分支：

```python
temperature = 25

if temperature > 30:
    print("It's hot!")
elif 20 <= temperature <= 30:
    print("It's warm.")
else:
    print("It's cool.")
```

### 3.2 循环语句

- **`for` 循环**：遍历序列或迭代对象
- **`while` 循环**：满足条件时重复执行

```python
# 示例：for 循环
for i in range(5):
    print(f"Iteration {i}")

# 示例：while 循环
count = 0
while count < 3:
    print("Count:", count)
    count += 1
```

💡 **小贴士**：
- 使用 `break` 提前退出循环。
- 使用 `continue` 跳过当前迭代。

---

## 4. 函数定义

函数使用 `def` 关键字定义，支持参数和返回值：

```python
def greet(name):
    """打印问候语"""
    return f"Hello, {name}!"

print(greet("Alice"))
```

### 4.1 Lambda 函数

匿名函数适用于简单操作：

```python
add = lambda x, y: x + y
print("Sum:", add(3, 5))  # 输出 8
```

---

## 5. 模块与包

Python 使用 `import` 导入模块或包：

```python
import math
from datetime import datetime

print("Pi:", math.pi)
print("Current Time:", datetime.now())
```

💡 **小贴士**：
- 使用 `as` 为模块或函数起别名：
  ```python
  import numpy as np
  ```

---

## 6. 异常处理

使用 `try-except` 捕获异常：

```python
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print("Error:", e)
finally:
    print("This will always execute.")
```

---

## 7. 高级特性

### 7.1 列表推导式

简洁地创建列表：

```python
squared = [x**2 for x in range(5)]
print("Squared Numbers:", squared)
```

### 7.2 生成器

使用 `yield` 创建生成器，节省内存：

```python
def fibonacci(n):
    a, b = 0, 1
    while a < n:
        yield a
        a, b = b, a + b

for num in fibonacci(10):
    print(num, end=" ")  # 输出 0 1 1 2 3 5 8
```

---

## 8. 小结

| 语法点       | 关键词/符号       | 说明                  |
|--------------|-------------------|-----------------------|
| 变量         | `=`               | 动态类型赋值          |
| 条件判断     | `if-elif-else`    | 多分支逻辑            |
| 循环         | `for`, `while`    | 遍历或重复操作        |
| 函数         | `def`, `lambda`   | 封装可复用代码        |
| 异常处理     | `try-except`      | 捕获运行时错误        |
| 模块导入     | `import`, `as`    | 使用外部功能          |

