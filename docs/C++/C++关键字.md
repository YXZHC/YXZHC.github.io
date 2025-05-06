# 🚀 C++ 关键字全解析：从基础到高级

> 💡 C++ 有超过 **80 个关键字**，它们是语言的基础构件。掌握这些关键字的含义和用法，是写出高效、规范代码的关键！本文将带你全面了解 C++ 中的重要关键字，并配以示例说明 😎。

---

## 📚 C++ 关键字概述

C++ 的关键字（Keywords）是语言保留的特殊标识符，不能作为变量名或函数名使用。它们构成了语言的语法结构和语义逻辑。

| 分类 | 示例关键字 |
|------|------------|
| 数据类型 | `int`, `float`, `double`, `char` |
| 控制流 | `if`, `else`, `for`, `while`, `switch` |
| 类与对象 | `class`, `struct`, `public`, `private`, `protected` |
| 存储类别 | `auto`, `register`, `static`, `extern`, `mutable` |
| 操作符重载 | `operator`, `new`, `delete` |
| 异常处理 | `try`, `catch`, `throw` |
| 多态与继承 | `virtual`, `override`, `final` |
| 模板编程 | `template`, `typename`, `constexpr` |

---

## 🔤 常见关键字详解

### 1. `int`, `float`, `double`, `char` —— 基础数据类型

```cpp
int age = 25;
float pi = 3.14f;
double gravity = 9.81;
char grade = 'A';
```

📌 **小贴士**：
- 使用 `sizeof()` 查看类型大小。
- 浮点数建议使用 `double`，除非内存敏感场景才用 `float`。

---

### 2. `bool` —— 布尔类型

```cpp
bool is_valid = true;
if (is_valid) {
    std::cout << "It's valid!" << std::endl;
}
```

✅ 推荐用于条件判断，使代码更清晰。

---

### 3. `void` —— 空类型

表示没有返回值或无参数。

```cpp
void greet() {
    std::cout << "Hello, World!" << std::endl;
}
```

也可以表示通用指针：

```cpp
void* ptr = &age;
```

⚠️ 注意：`void*` 不能直接解引用，必须转换为具体类型后再使用。

---

## ⚙️ 控制流程关键字

### 4. `if`, `else`, `switch`, `case`, `default`

```cpp
int score = 85;
if (score >= 60) {
    std::cout << "Pass" << std::endl;
} else {
    std::cout << "Fail" << std::endl;
}

switch (score / 10) {
    case 9: std::cout << "A"; break;
    case 8: std::cout << "B"; break;
    default: std::cout << "C or below"; break;
}
```

📌 **推荐**：使用 `switch` 替代多个 `if-else` 提高可读性。

---

### 5. `for`, `while`, `do-while` —— 循环控制

```cpp
for (int i = 0; i < 5; ++i)
    std::cout << i << " ";

int j = 0;
while (j < 5)
    std::cout << j++ << " ";

int k = 0;
do {
    std::cout << k++ << " ";
} while (k < 5);
```

💡 **技巧**：`do-while` 至少执行一次循环体。

---

## 🧱 类与对象相关关键字

### 6. `class`, `struct`, `union`

```cpp
class Person {
private:
    std::string name;
public:
    void setName(std::string n) { name = n; }
};

struct Point {
    int x, y;
}; // 默认 public 访问权限
```

📌 差异：
- `class` 默认成员为 `private`
- `struct` 默认成员为 `public`

---

### 7. `public`, `private`, `protected`

访问修饰符决定了类成员的可见性。

```cpp
class MyClass {
private:
    int secret;
public:
    void setSecret(int s) { secret = s; }
};
```

🔒 封装的核心机制！

---

### 8. `this` —— 当前对象指针

```cpp
class Student {
    std::string name;
public:
    void setName(const std::string& name) {
        this->name = name; // 区分参数与成员变量
    }
};
```

---

## 🔄 继承与多态关键字

### 9. `virtual` —— 虚函数支持多态

```cpp
class Base {
public:
    virtual void show() { std::cout << "Base class" << std::endl; }
};

class Derived : public Base {
public:
    void show() override { std::cout << "Derived class" << std::endl; }
};
```

📌 必须配合指针或引用使用虚函数才能体现多态行为。

---

### 10. `override` 和 `final`

- `override`: 显式声明重写父类方法（避免拼写错误）
- `final`: 防止类被继承或方法被重写

```cpp
class FinalClass final {
    // 无法被继承
};

class Parent {
public:
    virtual void foo() final; // 子类不能再重写
};
```

---

## 🛠️ 存储类别关键字

### 11. `static` —— 静态成员

静态成员属于类本身，而不是对象。

```cpp
class Counter {
    static int count;
public:
    Counter() { count++; }
    static int getCount() { return count; }
};

int Counter::count = 0;

int main() {
    Counter c1, c2;
    std::cout << Counter::getCount(); // 输出 2
}
```

---

### 12. `const` —— 常量限定符

```cpp
const double PI = 3.14159;
PI = 3.14; // ❌ 编译错误
```

还可以用于函数参数、返回值、成员函数等：

```cpp
void print(const std::string& msg) const {
    std::cout << msg << std::endl;
}
```

---

### 13. `extern` —— 外部变量/函数

用于声明在其他文件中定义的全局变量或函数。

```cpp
// file1.cpp
int globalVar = 10;

// file2.cpp
extern int globalVar;
std::cout << globalVar; // 可以访问
```

---

## 🧬 内存管理关键字

### 14. `new` 和 `delete`

动态分配/释放内存：

```cpp
int* p = new int(100);
std::cout << *p << std::endl;
delete p;
```

数组版本：

```cpp
int* arr = new int[5]{1, 2, 3, 4, 5};
delete[] arr;
```

⚠️ **注意**：记得成对使用，避免内存泄漏！

---

## 🧠 模板与泛型编程关键字

### 15. `template` 和 `typename`

用于定义模板类和模板函数：

```cpp
template<typename T>
T max(T a, T b) {
    return a > b ? a : b;
}

int main() {
    std::cout << max<int>(3, 5); // 输出 5
}
```

---

### 16. `constexpr` —— 编译时常量表达式

```cpp
constexpr int square(int x) {
    return x * x;
}

int arr[square(5)]; // 合法，因为 square(5) 是编译时常量
```

---

## 🛑 特殊用途关键字

### 17. `goto` —— 跳转语句（慎用）

```cpp
start:
    std::cout << "Jumping..." << std::endl;
    goto start;
```

⚠️ **警告**：滥用 `goto` 会导致“意大利面条式代码”，应尽量避免使用。

---

### 18. `namespace` —— 命名空间

防止命名冲突：

```cpp
namespace Math {
    int add(int a, int b) { return a + b; }
}

std::cout << Math::add(3, 5); // 输出 8
```

---

### 19. `using` —— 命名空间引入

```cpp
using namespace std;
cout << "Hello, World!" << endl;
```

🚫 **不推荐**在头文件中使用 `using namespace`，容易引发命名冲突。

---

### 20. `friend` —— 友元函数/类

允许非成员函数访问私有成员：

```cpp
class Box {
private:
    double width;
public:
    friend void printWidth(Box box);
};

void printWidth(Box box) {
    std::cout << "Width: " << box.width << std::endl;
}
```

---

## 📦 其他实用关键字

### 21. `enum`, `enum class` —— 枚举类型

```cpp
enum Color { RED, GREEN, BLUE };
Color c = RED;

enum class Direction { North, South, East, West };
Direction d = Direction::North;
```

📌 `enum class` 更安全，推荐使用。

---

### 22. `decltype` —— 自动推导表达式类型

```cpp
int x = 10;
decltype(x) y = 20; // y 的类型自动推断为 int
```

---

### 23. `nullptr` —— 空指针常量

代替旧式的 `NULL` 或 `0`：

```cpp
int* ptr = nullptr;
if (ptr == nullptr) {
    std::cout << "Pointer is null." << std::endl;
}
```

---

## 🧪 异常处理关键字

### 24. `try`, `catch`, `throw`

```cpp
try {
    throw std::runtime_error("Something went wrong!");
} catch (const std::exception& e) {
    std::cerr << "Caught exception: " << e.what() << std::endl;
}
```

---

## ✅ 总结表格：常用 C++ 关键字一览

| 关键字 | 用途 |
|--------|------|
| `int`, `float`, `double` | 基本数据类型 |
| `if`, `else`, `for`, `while` | 控制流程 |
| `class`, `struct`, `union` | 定义复合类型 |
| `public`, `private`, `protected` | 访问控制 |
| `virtual`, `override`, `final` | 多态与继承 |
| `static`, `const`, `extern` | 存储类别 |
| `new`, `delete` | 动态内存管理 |
| `template`, `typename` | 泛型编程 |
| `namespace`, `using` | 命名空间管理 |
| `try`, `catch`, `throw` | 异常处理 |

---