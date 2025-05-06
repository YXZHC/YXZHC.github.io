# 🚀 C++ 面向对象编程（OOP）入门全攻略

> 💡 面向对象编程是现代软件开发的核心思想，C++ 作为一门强大的面向对象语言，提供了类、对象、继承、多态等核心特性。本文将带你全面了解 C++ 中的 OOP 特性，适合初学者快速上手！

---

## 🧱 什么是面向对象编程？

面向对象编程（Object-Oriented Programming, OOP）是一种**以对象为中心**的编程范式，强调数据和操作的封装。C++ 的 OOP 主要基于三个基本概念：

1. **封装（Encapsulation）**
2. **继承（Inheritance）**
3. **多态（Polymorphism）**

🎯 **目标**：提高代码的可重用性、灵活性和可维护性。

---

## 🔧 类与对象：OOP 的基石

### 类（Class）

类是对象的模板或蓝图，定义了对象的属性和行为。

```cpp
class Dog {
private:
    std::string name;
    int age;

public:
    // 构造函数
    Dog(std::string n, int a) : name(n), age(a) {}

    // 成员方法
    void bark() {
        std::cout << name << " is barking!" << std::endl;
    }

    void info() {
        std::cout << "Name: " << name << ", Age: " << age << std::endl;
    }
};
```

### 对象（Object）

对象是类的具体实例。

```cpp
int main() {
    Dog myDog("Buddy", 3); // 创建一个 Dog 对象
    myDog.bark();          // 调用方法
    myDog.info();

    return 0;
}
```

🎉 输出：
```
Buddy is barking!
Name: Buddy, Age: 3
```

📌 **关键点**：
- `private` 成员只能在类内部访问。
- `public` 成员对外可见，可通过对象调用。

---

## 🔐 封装（Encapsulation）

封装是将数据设为私有，并通过公共方法进行访问的方式。

### 示例：银行账户类

```cpp
class BankAccount {
private:
    double balance;

public:
    BankAccount(double initial) : balance(initial) {}

    void deposit(double amount) {
        if (amount > 0) balance += amount;
    }

    void withdraw(double amount) {
        if (amount > 0 && amount <= balance)
            balance -= amount;
    }

    double getBalance() const {
        return balance;
    }
};
```

🔒 **优点**：
- 数据安全
- 提高模块化程度
- 易于调试和维护

---

## 🧬 继承（Inheritance）

继承允许我们创建一个新类（派生类），从已有的类（基类）继承其属性和方法。

### 示例：动物类与狗类

```cpp
// 基类
class Animal {
public:
    void eat() {
        std::cout << "Animal is eating..." << std::endl;
    }
};

// 派生类
class Dog : public Animal {
public:
    void bark() {
        std::cout << "Dog is barking!" << std::endl;
    }
};

int main() {
    Dog d;
    d.eat();   // 来自父类
    d.bark();  // 自己的方法

    return 0;
}
```

🎯 **输出**：
```
Animal is eating...
Dog is barking!
```

📌 **继承方式**：
- `public`: 公共继承
- `protected`: 受保护继承
- `private`: 私有继承

---

## 🎭 多态（Polymorphism）

多态是指同一接口可以有不同的实现方式。C++ 支持运行时多态（通过虚函数实现）。

### 示例：形状类与子类

```cpp
#include <iostream>
using namespace std;

// 基类
class Shape {
public:
    virtual void draw() const = 0; // 纯虚函数
    virtual ~Shape() {} // 虚析构函数
};

// 派生类
class Circle : public Shape {
public:
    void draw() const override {
        cout << "Drawing a circle." << endl;
    }
};

class Rectangle : public Shape {
public:
    void draw() const override {
        cout << "Drawing a rectangle." << endl;
    }
};

int main() {
    Shape* s1 = new Circle();
    Shape* s2 = new Rectangle();

    s1->draw(); // 动态绑定
    s2->draw();

    delete s1;
    delete s2;

    return 0;
}
```

🎯 **输出**：
```
Drawing a circle.
Drawing a rectangle.
```

📌 **关键点**：
- 使用 `virtual` 关键字声明虚函数
- 纯虚函数使类成为抽象类（不能实例化）
- 多态需要通过指针或引用调用

---

## 🧠 构造函数与析构函数

### 构造函数（Constructor）

用于初始化对象的状态。

```cpp
class Person {
public:
    Person() {
        cout << "Person created!" << endl;
    }
};
```

### 析构函数（Destructor）

用于释放资源，在对象销毁时自动调用。

```cpp
~Person() {
    cout << "Person destroyed!" << endl;
}
```

💡 **注意**：继承链中构造函数和析构函数的调用顺序是相反的！

---

## 🧩 this 指针与静态成员

### `this` 指针

指向当前对象的指针。

```cpp
class MyClass {
    int value;
public:
    MyClass(int value) {
        this->value = value; // 区分参数与成员变量
    }
};
```

### 静态成员（Static Members）

属于类本身而非对象。

```cpp
class Counter {
private:
    static int count; // 静态变量
public:
    Counter() { count++; }
    static int getCount() { return count; }
};

int Counter::count = 0; // 必须在类外初始化

int main() {
    cout << Counter::getCount() << endl; // 0
    Counter c1, c2;
    cout << Counter::getCount() << endl; // 2
}
```

---

## 🧪 运算符重载（Operator Overloading）

允许为已有运算符赋予用户自定义含义。

```cpp
class Complex {
    double real, imag;
public:
    Complex(double r = 0, double i = 0) : real(r), imag(i) {}

    Complex operator+(const Complex& other) const {
        return Complex(real + other.real, imag + other.imag);
    }

    void print() const {
        cout << real << " + " << imag << "i" << endl;
    }
};

int main() {
    Complex c1(2, 3), c2(4, 5);
    Complex c3 = c1 + c2;
    c3.print(); // 6 + 8i
}
```

---

## 🛠️ 命名空间与友元函数

### 命名空间（Namespace）

避免命名冲突。

```cpp
namespace Math {
    int add(int a, int b) {
        return a + b;
    }
}

int result = Math::add(3, 5);
```

### 友元函数（Friend Function）

非类成员函数，但可以访问类的私有成员。

```cpp
class Box {
private:
    double width;
public:
    friend void printWidth(Box box);
};

void printWidth(Box box) {
    cout << "Width: " << box.width << endl;
}
```

---

## ❓ 常见问题解答

### Q1: 为什么要有虚析构函数？
A: 如果删除一个指向派生类的基类指针，没有虚析构函数会导致未定义行为。

### Q2: 如何防止类被继承？
A: 使用 `final` 关键字：
```cpp
class Base final { }; // 无法被继承
```

### Q3: 类和结构体的区别？
A: 在 C++ 中，唯一区别是默认访问权限：
- `class` 默认 `private`
- `struct` 默认 `public`
