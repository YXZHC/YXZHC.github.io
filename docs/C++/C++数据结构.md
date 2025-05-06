# 🚀 C++ 数据结构详解：从基础到实战

> 💡 数据结构是编程的骨架，C++ 提供了丰富的内置类型和 STL 容器，帮助我们高效地组织和操作数据。本文将带你系统学习 C++ 中常见的数据结构，适合初学者入门与进阶！

---

## 🧱 什么是数据结构？

**数据结构（Data Structure）** 是计算机中存储、组织数据的方式。在 C++ 中，我们可以使用基本数据类型（如 `int`, `float`）以及自定义结构体、类来构建复杂的数据模型。

🎯 **目标**：
- 理解常用数据结构的原理与实现
- 掌握如何选择合适的数据结构解决实际问题
- 熟悉 STL 容器的使用技巧

---

## 📦 常见数据结构分类

| 类型 | 描述 |
|------|------|
| 线性结构 | 如数组、链表、栈、队列 |
| 树形结构 | 如二叉树、堆、平衡树 |
| 图形结构 | 图由节点和边组成 |
| 散列结构 | 如哈希表、集合 |

---

## 🔢 1. 数组（Array）

### 定义方式：

```cpp
int arr[5] = {1, 2, 3, 4, 5};
```

### 特点：
- 固定大小
- 随机访问快（O(1)）
- 插入/删除慢（需要移动元素）

📌 **小贴士**：数组下标从 `0` 开始 😊

---

## 🔗 2. 链表（Linked List）

链表是一种动态结构，每个节点包含数据和指向下一个节点的指针。

### 单链表示例：

```cpp
struct Node {
    int data;
    Node* next;
};

Node* head = new Node{1, nullptr};
head->next = new Node{2, nullptr};
```

### 特点：
- 动态扩容
- 插入/删除快（O(1)，若已知位置）
- 查找慢（O(n)）

🧩 **进阶知识**：双向链表、循环链表、智能指针管理内存更安全！

---

## ⬆️ 3. 栈（Stack）

栈是一种“后进先出”（LIFO）的数据结构。

### 使用 STL 示例：

```cpp
#include <stack>
std::stack<int> s;
s.push(1);
s.push(2);
std::cout << s.top(); // 输出 2
s.pop();
```

### 应用场景：
- 函数调用栈
- 括号匹配检查
- 表达式求值

🧠 **记忆口诀**：最后进来的第一个出去 😎

---

## ⬇️ 4. 队列（Queue）

队列是一种“先进先出”（FIFO）的数据结构。

### 使用 STL 示例：

```cpp
#include <queue>
std::queue<int> q;
q.push(1);
q.push(2);
std::cout << q.front(); // 输出 1
q.pop();
```

### 双端队列（deque）：
支持两端插入/删除，功能更强大！

---

## 🌳 5. 树（Tree）

树是一种非线性的分层结构，最常见的是**二叉树**。

### 二叉树节点定义示例：

```cpp
struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};
```

### 常见变种：
- 二叉搜索树（BST）
- 平衡二叉树（AVL Tree）
- 堆（Heap）
- B树、红黑树等

🛠 **用途**：数据库索引、文件系统、表达式树等

---

## 🧮 6. 图（Graph）

图是由节点（顶点）和边组成的结构。

### 图的表示方法：
- 邻接矩阵
- 邻接表

```cpp
#include <vector>
using namespace std;

vector<vector<int>> adjList(5); // 5个顶点的邻接表
adjList[0].push_back(1);
adjList[1].push_back(0);
```

🗺 **应用场景**：社交网络、地图导航、任务调度

---

## 🔍 7. 散列表（Hash Table）

散列表通过哈希函数将键映射到值，查找效率高（平均 O(1)）。

### C++ STL 实现：
- `unordered_map`
- `unordered_set`

```cpp
#include <unordered_map>
std::unordered_map<std::string, int> scores;
scores["Alice"] = 95;
std::cout << scores["Alice"]; // 输出 95
```

🔐 **注意**：处理哈希冲突（开放地址法、拉链法）

---

## 🧰 C++ STL 容器一览

| 容器类型 | 描述 | 头文件 |
|----------|------|--------|
| `vector` | 动态数组 | `<vector>` |
| `list` | 双向链表 | `<list>` |
| `deque` | 双端队列 | `<deque>` |
| `map`, `set` | 关联容器（有序） | `<map>`, `<set>` |
| `unordered_map`, `unordered_set` | 哈希容器（无序） | `<unordered_map>`, `<unordered_set>` |
| `stack`, `queue` | 适配器容器 | `<stack>`, `<queue>` |

🌟 **推荐**：优先使用 STL 容器，提高开发效率与安全性！

---

## 🛠️ 自定义数据结构示例：学生信息管理系统

### 定义结构体：

```cpp
struct Student {
    std::string name;
    int age;
    float gpa;

    void print() const {
        std::cout << "Name: " << name
                  << ", Age: " << age
                  << ", GPA: " << gpa << std::endl;
    }
};
```

### 使用 vector 存储多个学生：

```cpp
#include <vector>
std::vector<Student> students;
students.push_back({"Alice", 20, 3.8});
students.push_back({"Bob", 22, 3.5});

for (const auto& s : students)
    s.print();
```

🎉 输出：
```
Name: Alice, Age: 20, GPA: 3.8
Name: Bob, Age: 22, GPA: 3.5
```

---

## 🧪 性能比较表（时间复杂度）

| 操作 | 数组 | 链表 | 向量 | map/set | unordered_map/set |
|------|------|------|------|---------|-------------------|
| 访问 | O(1) | O(n) | O(1) | O(log n) | O(1) avg |
| 插入 | O(n) | O(1) | amortized O(1) | O(log n) | O(1) avg |
| 删除 | O(n) | O(1) | O(n) | O(log n) | O(1) avg |

📊 **建议**：
- 快速查找选哈希表
- 需要排序选 set/map
- 动态扩容首选 vector

---

## ❓ 常见问题解答

### Q1: vector 和 list 的区别？
A:
- `vector` 支持随机访问，尾部插入快。
- `list` 插入/删除快，但不支持随机访问。

### Q2: map 和 unordered_map 的区别？
A:
- `map` 内部是红黑树，有序。
- `unordered_map` 是哈希表，无序但查找更快。

### Q3: 如何选择合适的数据结构？
A:
- 分析你的需求：是否需要快速查找？是否频繁增删？
- 结合时间和空间复杂度进行权衡。

---

## ✅ 总结

| 数据结构 | 适用场景 |
|----------|----------|
| 数组 | 固定大小，快速访问 |
| 链表 | 动态增删频繁 |
| 栈 | LIFO 场景 |
| 队列 | FIFO 场景 |
| 树 | 层次化数据、搜索优化 |
| 图 | 网络关系建模 |
| 哈希表 | 快速查找、去重 |

