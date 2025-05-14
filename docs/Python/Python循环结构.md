# 🔄 Python循环结构详解

在Python编程中，循环结构是实现重复执行某些代码块的重要方式。通过循环，我们可以自动化处理那些需要重复进行的任务，极大地提高了编程效率和代码的简洁性。本文将深入介绍Python中的主要循环结构及其使用方法。让我们一起探索吧！ 😊

---

## 📌 循环简介

循环是一种控制流语句，允许我们多次执行一个代码块，直到满足特定条件为止。Python提供了几种不同的循环结构，包括`for`循环、`while`循环以及列表推导式等高级用法。

---

## 🔄 `for` 循环

`for`循环是最常用的循环类型之一，主要用于遍历序列（如列表、元组、字符串）或其他可迭代对象。

### 1️⃣ 基本语法

```python
for item in iterable:
    # 执行代码块
```

例如，打印列表中的每个元素：

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

### 2️⃣ 使用`range()`函数

`range()`函数常用于生成一系列数字，非常适合用来控制循环次数。

```python
for i in range(5):  # 从0到4
    print(i)
```

### 3️⃣ 列表推导式

这是一种更加简洁的方式来创建列表，同时也可以看作一种特殊的`for`循环。

```python
squares = [x**2 for x in range(10)]
print(squares)  # 输出: [0, 1, 4, ..., 81]
```

---

## 🔁 `while` 循环

`while`循环会一直执行一段代码，直到指定的条件不再满足。

### 1️⃣ 基本语法

```python
while condition:
    # 执行代码块
```

例如，计算从1加到100的总和：

```python
sum = 0
i = 1
while i <= 100:
    sum += i
    i += 1
print(sum)  # 输出: 5050
```

### 2️⃣ 注意事项：避免无限循环

确保`while`循环的条件最终能够变为`False`，否则会导致程序进入无限循环状态。

```python
# 错误示例
while True:
    print("This will run forever!")
```

---

## 🛠️ 循环控制语句

Python提供了一些特殊的语句来控制循环的行为，使得我们可以更灵活地操作循环过程。

### 1️⃣ `break` 语句

`break`语句可以立即退出最内层的循环，通常用于提前结束循环。

```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

### 2️⃣ `continue` 语句

`continue`语句跳过当前循环体中剩余的语句，并继续下一个循环周期。

```python
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)  # 只打印奇数
```

### 3️⃣ `else` 子句

与`for`或`while`结合使用的`else`子句会在循环正常结束后执行（即没有遇到`break`时）。

```python
for n in range(2, 10):
    for x in range(2, n):
        if n % x == 0:
            print(n, 'equals', x, '*', n//x)
            break
    else:
        print(n, 'is a prime number')
```

---

## 🤔 结论

理解和掌握循环结构是编写高效Python代码的关键。无论是简单的遍历操作还是复杂的逻辑控制，合理利用`for`和`while`循环都能帮助我们写出更加简洁、易读且高效的代码。希望这篇文章能为你提供有价值的指导！

---
