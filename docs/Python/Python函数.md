# 🚀 Python 函数全攻略：从入门到精通  

函数是 Python 编程的核心模块之一，它可以帮助我们将代码逻辑组织成可复用、易维护的单元。本文将深入解析 Python 函数的定义、调用、参数传递、高级技巧及实际应用，并通过示例代码帮助你快速掌握！  


## 1. 什么是函数？ 🤔  
函数是一段具有特定功能的代码块，可以通过名称多次调用。它的核心优势包括：  
- ✅ **代码复用**：避免重复编写相同逻辑  
- ✅ **增强可读性**：将复杂逻辑模块化  
- ✅ **易于维护**：修改函数即可影响所有调用点  

### 示例：简单的问候函数  
```python
def greet():
    """打印欢迎信息"""
    print("👋 你好，欢迎学习 Python 函数！")

greet()  # 调用函数
```
**输出**：  
```
👋 你好，欢迎学习 Python 函数！
```

---

## 2. 定义与调用函数 🛠️  
使用 `def` 关键字定义函数，语法如下：  
```python
def 函数名(参数1, 参数2, ...):
    """文档字符串（可选）"""
    # 函数体
    return 返回值（可选）
```

### 示例：计算两个数的和  
```python
def add(a, b):
    """返回两个数的和"""
    return a + b

result = add(3, 5)
print("3 + 5 =", result)  # 输出: 3 + 5 = 8
```

---

## 3. 函数参数详解 🔄  
Python 支持多种参数传递方式：  

### 3.1 位置参数（Positional Arguments）  
按顺序传递参数：  
```python
def subtract(a, b):
    return a - b

print(subtract(10, 3))  # 输出: 7
```

### 3.2 关键字参数（Keyword Arguments）  
通过参数名传递，顺序无关：  
```python
def introduce(name, age):
    print(f"我的名字是{name}，我{age}岁了。")

introduce(age=25, name="小明")  # 输出: 我的名字是小明，我25岁了。
```

### 3.3 默认参数（Default Arguments）  
为参数设置默认值：  
```python
def power(base, exponent=2):
    return base ** exponent

print(power(3))       # 输出: 9 (3^2)
print(power(3, 3))    # 输出: 27 (3^3)
```

### 3.4 可变参数（*args 和 **kwargs）  
- `*args`：接收任意数量的位置参数（元组形式）  
- `**kwargs`：接收任意数量的关键字参数（字典形式）  

```python
def show_info(*args, **kwargs):
    print("位置参数:", args)
    print("关键字参数:", kwargs)

show_info(1, 2, 3, name="Alice", role="Developer")
```
**输出**：  
```
位置参数: (1, 2, 3)
关键字参数: {'name': 'Alice', 'role': 'Developer'}
```

---

## 4. 返回值与作用域 🔄  
### 4.1 返回值  
使用 `return` 语句返回结果，若无 `return`，默认返回 `None`。  

```python
def is_even(num):
    return num % 2 == 0

print(is_even(4))  # 输出: True
```

### 4.2 作用域  
- **局部变量**：在函数内部定义，仅函数内可访问  
- **全局变量**：在函数外部定义，使用 `global` 关键字修改  

```python
counter = 0  # 全局变量

def increment():
    global counter
    counter += 1

increment()
print(counter)  # 输出: 1
```

---

## 5. 高阶函数与装饰器 🌟  
### 5.1 高阶函数  
函数可以作为参数或返回值传递：  

```python
def apply_operation(func, a, b):
    return func(a, b)

def multiply(x, y):
    return x * y

result = apply_operation(multiply, 4, 5)
print("4 * 5 =", result)  # 输出: 4 * 5 = 20
```

### 5.2 装饰器（Decorator）  
用于增强函数功能，无需修改原函数：  

```python
def timing_decorator(func):
    import time
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"⏱️ {func.__name__} 执行时间: {end - start:.4f} 秒")
        return result
    return wrapper

@timing_decorator
def slow_function():
    time.sleep(2)

slow_function()
```
**输出**：  
```
⏱️ slow_function 执行时间: 2.0001 秒
```

---

## 6. 生成器与迭代器 🔁  
### 6.1 生成器（Generator）  
使用 `yield` 关键字按需生成值：  

```python
def fibonacci():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

fib = fibonacci()
for _ in range(5):
    print(next(fib))  # 输出: 0 1 1 2 3
```

### 6.2 生成器表达式  
类似列表推导，但更节省内存：  
```python
squares = (x**2 for x in range(10))
print(list(squares))  # 输出: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

---

## 7. 常见问题与技巧 🧩  
### Q1: 如何动态传递参数？  
使用 `*args` 和 `**kwargs`，如：  
```python
def dynamic_function(*args, **kwargs):
    print("参数:", args, kwargs)

dynamic_function(1, 2, 3, key1="value1", key2="value2")
```

### Q2: 如何处理递归函数？  
确保有终止条件，避免无限递归：  
```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n-1)

print(factorial(5))  # 输出: 120
```

### Q3: 如何优化函数性能？  
使用 `@lru_cache` 缓存结果（适用于重复计算场景）：  
```python
from functools import lru_cache

@lru_cache(maxsize=None)
def fib(n):
    if n < 2:
        return n
    return fib(n-1) + fib(n-2)

print(fib(100))  # 快速计算斐波那契数列
```
