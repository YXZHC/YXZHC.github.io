# 🐍 Python 正则表达式完全指南：从基础到实战  

---

## 🌟 什么是正则表达式？  
正则表达式（**Regex**）是一种用于**文本匹配、查找和替换**的强大工具。它通过**特殊字符和模式**描述复杂的字符串规则，广泛应用于数据清洗、日志分析、字符串解析等场景。  

在 Python 中，我们通过 `re` 模块实现正则表达式操作。  

---

## 🧱 正则表达式基本语法  

### ✅ 特殊字符与元字符  

| 符号 | 含义 | 示例 |
|------|------|------|
| `.` | 匹配任意单个字符（除换行符） | `a.b` → `"acb"`, `"a0b"` |
| `^` | 匹配字符串开头 | `^Hello` → `"Hello world"` |
| `$` | 匹配字符串结尾 | `world$` → `"Hello world"` |
| `*` | 前面字符重复 **0 或多次** | `ab*` → `"a"`, `"ab"`, `"abb"` |
| `+` | 前面字符重复 **1 或多次** | `ab+` → `"ab"`, `"abb"` |
| `?` | 前面字符 **0 次或 1 次** | `ab?` → `"a"`, `"ab"` |
| `{n}` | 前面字符 **恰好 n 次** | `a{3}` → `"aaa"` |
| `{n,}` | 前面字符 **至少 n 次** | `a{2,}` → `"aa"`, `"aaa"` |
| `{n,m}` | 前面字符 **n 到 m 次** | `a{1,3}` → `"a"`, `"aa"`, `"aaa"` |
| `[]` | 字符类，匹配任意一个字符 | `[abc]` → `"a"`, `"b"`, `"c"` |
| `\d` | 数字 `[0-9]` | `\d{3}` → `"123"` |
| `\D` | 非数字 | `\D` → `"a"`, `"@"` |
| `\s` | 空白字符（空格、制表符等） | `\s+` → `" "` |
| `\w` | 单词字符（字母、数字、下划线） | `\w+` → `"hello123"` |

---

### ✅ 修饰符（Flags）  

| 标志 | 描述 | 示例 |
|------|------|------|
| `re.IGNORECASE` (`re.I`) | 忽略大小写 | `re.match(r'hello', 'HELLO', re.I)` |
| `re.MULTILINE` (`re.M`) | 多行匹配（`^` 和 `$` 匹配每行的首尾） | `re.search(r'^Line', text, re.M)` |
| `re.DOTALL` (`re.S`) | `.` 匹配包括换行符在内的任意字符 | `re.match(r'a.c', 'a\nb', re.S)` |
| `re.VERBOSE` (`re.X`) | 允许在正则中添加空白和注释 | 
```python
pattern = re.compile(r"""
    \d{4}-\d{2}-\d{2}  # 匹配日期格式 YYYY-MM-DD
""", re.X)
```

---

## 🔍 `re` 模块核心操作  

### 1. `re.match()`：从字符串开头匹配  
```python
import re

pattern = r"hello"
text = "hello world"

match = re.match(pattern, text)
if match:
    print("匹配成功:", match.group())  # 输出: hello
else:
    print("匹配失败")
```

---

### 2. `re.search()`：在字符串中搜索第一个匹配项  
```python
import re

pattern = r"world"
text = "hello world"

search = re.search(pattern, text)
if search:
    print("匹配成功:", search.group())  # 输出: world
```

---

### 3. `re.findall()`：查找所有匹配项  
```python
import re

text = "联系我们：support@example.com 或者 sales.department@another-example.net.cn"
pattern = r"\w+@\w+\.\w+"

emails = re.findall(pattern, text)
print("提取到的邮箱地址:", emails)
# 输出: ['support@example.com', 'sales.department@another-example.net.cn']
```

---

### 4. `re.sub()`：替换匹配项  
```python
import re

text = "Hello world! Welcome to the world of Python."
new_text = re.sub(r"world", "Python", text)
print(new_text)
# 输出: Hello Python! Welcome to the Python of Python.
```

---

### 5. `re.split()`：根据正则分割字符串  
```python
import re

text = "apple,banana;orange:grape"
split_result = re.split(r"[,;:]", text)
print(split_result)
# 输出: ['apple', 'banana', 'orange', 'grape']
```

---

## 🚀 实战案例  

### ✅ 案例 1：验证中国大陆手机号  
```python
import re

def is_valid_phone(number):
    pattern = r"^1[3-9]\d{9}$"  # 以 1 开头，第二位 3-9，共 11 位
    return bool(re.match(pattern, number))

print(is_valid_phone("13800138000"))  # True
print(is_valid_phone("12345678901"))  # False
```

---

### ✅ 案例 2：提取中文文本  
```python
import re

text = "Python 是一门强大的编程语言，真香！"
chinese_chars = re.findall(r"[\u4e00-\u9fa5]", text)
print("提取到的中文字符:", chinese_chars)
# 输出: ['是', '门', '强', '大', '的', '编', '程', '语', '言', '真', '香']
```

---

### ✅ 案例 3：解析日志文件  
假设日志文件内容如下：  
```
2025-05-28 08:00:00 INFO User login
2025-05-28 08:05:00 ERROR Failed to connect
```

提取时间戳和日志级别：  
```python
import re

log = """
2025-05-28 08:00:00 INFO User login
2025-05-28 08:05:00 ERROR Failed to connect
"""

pattern = r"(\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}) (\w+) .*"
matches = re.findall(pattern, log)

for timestamp, level in matches:
    print(f"[{timestamp}] {level}")
```

---

## ⚠️ 常见问题与最佳实践  

### 1. **转义字符问题**  
在正则表达式中，反斜杠 `\` 需要转义，建议使用**原始字符串**（`r""`）：  
```python
# ❌ 错误写法（需手动转义）
pattern = "\d{3}"

# ✅ 正确写法
pattern = r"\d{3}"
```

---

### 2. **正则性能优化**  
- **避免贪婪匹配**：使用 `?` 修饰符（非贪婪模式）  
  ```python
  re.match(r"<.*?>", "<div>test</div>")  # 匹配到 <div>
  ```
- **预编译正则**：重复使用时编译一次  
  ```python
  pattern = re.compile(r"\d{4}-\d{2}-\d{2}")
  ```

---

### 3. **复杂正则建议**  
- 使用 `re.VERBOSE` 添加注释  
  ```python
  pattern = re.compile(r"""
      ^                   # 匹配开头
      \d{4}-\d{2}-\d{2}  # 匹配日期格式 YYYY-MM-DD
      $                   # 匹配结尾
  """, re.X)
  ```

---

## 🎉 总结  

| 功能 | 方法 |
|------|------|
| 匹配 | `re.match()`, `re.search()` |
| 查找 | `re.findall()`, `re.finditer()` |
| 替换 | `re.sub()` |
| 分割 | `re.split()` |

正则表达式是文本处理的“瑞士军刀”，掌握它能极大提升开发效率！  

