# 🚀 Python变量类型详解  

在Python编程中，变量是存储和操作数据的核心工具。Python是一种**动态类型语言**，这意味着变量的类型由赋值自动推断，无需显式声明。本文将带你全面了解Python中的变量类型及其使用方法！  

---

## 📦 什么是变量？  
变量是**存储数据的容器**，可以看作是内存中的一块命名空间。在Python中，变量的定义非常简单：  
```python  
x = 10  
name = "Alice"  
is_student = True  
```  
Python会根据赋值自动推断变量的类型（例如 `int`、`str`、`bool` 等）。  

---

## 🧱 Python基础数据类型  

### 1️⃣ 数字类型（Numbers）  
数字类型用于存储数值数据，包括以下几种：  

#### 🔹 整数（`int`）  
表示没有小数部分的数字，支持任意大小的整数：  
```python  
age = 25  
negative = -100  
zero = 0  
print(type(age))  # <class 'int'>  
```  

#### 🔹 浮点数（`float`）  
带有小数部分的数字，支持科学计数法：  
```python  
height = 1.75  
scientific = 1.23e-5  # 0.0000123  
print(type(height))  # <class 'float'>  
```  

#### 🔹 复数（`complex`）  
由实部和虚部组成，虚部用 `j` 表示：  
```python  
c = 2 + 3j  
print(c.real)  # 2.0  
print(c.imag)  # 3.0  
```  

---

### 2️⃣ 字符串类型（`str`）  
字符串是文本数据，用单引号 `'`、双引号 `"` 或三引号 `'''` 定义：  
```python  
greeting = "Hello, World!"  
multi_line = '''This is a  
multi-line string.'''  
print(len(greeting))  # 13  
```  

#### 🛠️ 字符串操作  
- **拼接**：`"Hello" + "World"` → `"HelloWorld"`  
- **切片**：`"Python"[0:3]` → `"Pyt"`  
- **格式化**：  
  ```python  
  name = "Alice"  
  print(f"Welcome, {name}!")  # Welcome, Alice!  
  ```  

---

### 3️⃣ 布尔类型（`bool`）  
布尔值只有两个取值：`True` 和 `False`，常用于逻辑判断：  
```python  
is_raining = True  
has_finished = False  
print(10 < 20)  # True  
```  

#### 📌 注意：  
- `0`、空字符串 `""`、空列表 `[]` 等在布尔上下文中会被视为 `False`。  

---

### 4️⃣ 序列类型  

#### 🔹 列表（`list`）  
可变的有序序列，用方括号 `[]` 定义：  
```python  
fruits = ["apple", "banana", "cherry"]  
fruits.append("orange")  # 添加元素  
print(fruits[1])  # banana  
```  

#### 🔹 元组（`tuple`）  
不可变的有序序列，用圆括号 `()` 定义：  
```python  
coordinates = (10.0, 20.0)  
print(coordinates[0])  # 10.0  
# coordinates[0] = 15  # ❌ 报错：不可变  
```  

#### 🔹 字典（`dict`）  
无序的键值对集合，用花括号 `{}` 定义：  
```python  
student = {"name": "Alice", "age": 25}  
print(student["name"])  # Alice  
student["age"] = 26  # 修改值  
```  

#### 🔹 集合（`set`）  
无序且不重复的元素集合：  
```python  
unique_numbers = {1, 2, 3, 3}  
print(unique_numbers)  # {1, 2, 3}  
```  

---

## 🧩 其他重要类型  

### 1️⃣ `NoneType`  
表示空值或未定义的值：  
```python  
result = None  
print(result is None)  # True  
```  

### 2️⃣ 类型转换  
Python支持隐式和显式类型转换：  
```python  
num_str = "123"  
num_int = int(num_str)  # 字符串→整数  
num_float = float("3.14")  # 字符串→浮点数  
```  

---

## 🧪 变量的动态特性  

### 🔄 变量类型可变  
Python变量可以重新赋值为不同类型的对象：  
```python  
x = 10  
print(type(x))  # <class 'int'>  

x = "Hello"  
print(type(x))  # <class 'str'>  
```  

### 🚫 变量命名规则  
- 以字母或下划线开头（如 `_private_var` 表示私有变量）。  
- 后续字符可以是字母、数字或下划线。  
- 不能使用保留字（如 `if`、`for`）。  

---

## 🧠 常见问题  

### ❓ Q: 如何删除变量？  
使用 `del` 语句：  
```python  
x = 100  
del x  
print(x)  # ❌ NameError: name 'x' is not defined  
```  

### ❓ Q: 如何查看变量类型？  
使用 `type()` 函数：  
```python  
print(type(3.14))  # <class 'float'>  
```  

---

## 🌟 总结  

| 类型       | 符号/示例      | 特性                  |  
|------------|----------------|-----------------------|  
| 整数       | `int`          | 无大小限制            |  
| 浮点数     | `float`        | 支持科学计数法        |  
| 字符串     | `str`          | 不可变                |  
| 布尔值     | `bool`         | `True`/`False`        |  
| 列表       | `list`         | 可变有序序列          |  
| 元组       | `tuple`        | 不可变有序序列        |  
| 字典       | `dict`         | 无序键值对            |  
| 集合       | `set`          | 无序且元素唯一        |  

掌握Python变量类型是编写高效代码的基础！🚀  