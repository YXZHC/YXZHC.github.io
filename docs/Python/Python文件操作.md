# 🐍 Python 文件操作完全指南：从基础到高级实战  

---

## 🌟 什么是文件操作？  
文件操作是编程中最基础、最常用的功能之一。Python 提供了丰富的内置方法，支持对文本文件、二进制文件、CSV 文件等进行读取、写入和管理。通过文件操作，你可以实现数据持久化存储、日志记录、配置文件管理等功能。  

---

## 🛠️ 基础文件操作  

### 1. 打开文件  
使用 `open()` 函数打开文件，支持多种模式：  

| 模式 | 描述 | 示例 |
|------|------|------|
| `r`  | 只读（默认） | `open('file.txt', 'r')` |
| `w`  | 写入（覆盖内容） | `open('file.txt', 'w')` |
| `a`  | 追加写入 | `open('file.txt', 'a')` |
| `b`  | 二进制模式 | `open('image.jpg', 'rb')` |
| `+`  | 读写模式 | `open('file.txt', 'r+')` |

**示例代码**：  
```python
# 以只读模式打开文件
with open('example.txt', 'r', encoding='utf-8') as f:
    content = f.read()
    print(content)
```

---

### 2. 读取文件  
Python 提供多种读取方式，适合不同场景：  

#### ✅ 一次性读取全部内容  
```python
with open('example.txt', 'r', encoding='utf-8') as f:
    content = f.read()  # 读取全部内容
    print(content)
```

#### ✅ 逐行读取（推荐处理大文件）  
```python
with open('example.txt', 'r', encoding='utf-8') as f:
    for line in f:
        print(line.strip())  # 去除换行符
```

#### ✅ 读取为列表  
```python
with open('example.txt', 'r', encoding='utf-8') as f:
    lines = f.readlines()  # 返回列表
    for line in lines:
        print(line.strip())
```

---

### 3. 写入文件  
文件写入分为 **覆盖写入** 和 **追加写入**：  

#### 🔄 覆盖写入（`w` 模式）  
```python
with open('output.txt', 'w', encoding='utf-8') as f:
    f.write('Hello, World!\n')
    f.writelines(['Line 1\n', 'Line 2\n'])  # 写入多行
```

#### ➕ 追加写入（`a` 模式）  
```python
with open('output.txt', 'a', encoding='utf-8') as f:
    f.write('New content added!\n')
```

---

## 🚀 高级文件操作  

### 1. 处理大文件  
对于大文件，建议分块读取以避免内存溢出：  
```python
def process_large_file(filename):
    with open(filename, 'r', encoding='utf-8') as f:
        while True:
            chunk = f.read(1024 * 1024)  # 每次读取 1MB
            if not chunk:
                break
            # 处理数据块
            print(f"Processing {len(chunk)} bytes...")
```

---

### 2. 二进制文件操作  
读写图片、音频等二进制文件时，需使用 `b` 模式：  
```python
# 复制图片文件
with open('input.jpg', 'rb') as src, open('copy.jpg', 'wb') as dst:
    dst.write(src.read())
```

---

### 3. 路径管理（`pathlib` 模块）  
Python 3.4+ 推荐使用 `pathlib` 模块管理文件路径：  
```python
from pathlib import Path

current_dir = Path.cwd()
new_file = current_dir / "data" / "new_file.txt"

# 创建目录（自动处理多级）
new_file.parent.mkdir(parents=True, exist_ok=True)

# 验证文件是否存在
if new_file.exists():
    print(f"文件大小：{new_file.stat().st_size} 字节")
else:
    new_file.touch()  # 创建空文件
```

---

## ⚠️ 常见异常处理  
文件操作中需捕获常见异常，确保程序健壮性：  
```python
try:
    with open('missing.txt', 'r') as f:
        content = f.read()
except FileNotFoundError:
    print("❌ 错误：文件不存在！")
except UnicodeDecodeError:
    print("❌ 错误：文件编码不匹配！")
except Exception as e:
    print(f"❌ 未知错误：{str(e)}")
finally:
    print("✅ 清理操作完成。")
```

---

## 📊 CSV 文件处理  
使用 `csv` 模块高效处理表格数据：  

### ✅ 写入 CSV 文件  
```python
import csv

headers = ['姓名', '年龄', '城市']
data = [
    ['张三', 28, '北京'],
    ['李四', 35, '上海']
]

with open('people.csv', 'w', newline='', encoding='utf-8-sig') as f:
    writer = csv.writer(f)
    writer.writerow(headers)
    writer.writerows(data)  # 写入多行
```

### ✅ 读取 CSV 文件  
```python
with open('people.csv', 'r', encoding='utf-8-sig') as f:
    reader = csv.reader(f)
    for row in reader:
        print(f"{row[0]} | {row[1]}岁 | {row[2]}")
```

---

## 🧩 实战案例  

### 1. 批量重命名文件  
```python
import os

def batch_rename(folder_path, old_str, new_str):
    count = 0
    for filename in os.listdir(folder_path):
        if old_str in filename:
            new_name = filename.replace(old_str, new_str)
            os.rename(
                os.path.join(folder_path, filename),
                os.path.join(folder_path, new_name)
            )
            print(f"重命名: {filename} -> {new_name}")
            count += 1
    print(f"共重命名了 {count} 个文件")
```

---

## ✅ 最佳实践  
1. **始终使用 `with` 语句**：自动关闭文件，避免资源泄漏。  
2. **指定编码格式**：如 `encoding='utf-8'`，避免中文乱码。  
3. **分块处理大文件**：减少内存占用。  
4. **路径管理**：优先使用 `pathlib` 模块。  

---

## 🎉 总结  
Python 的文件操作功能强大且灵活，掌握这些技能能让你轻松处理文本、二进制文件甚至 CSV 数据。通过合理使用 `with` 语句、异常处理和高级库（如 `pathlib` 和 `csv`），你可以在实际项目中高效管理文件资源！  

