# 🐍 Python异常处理全攻略：从原理到实战 🚀

---

## 🧠 一、异常的概念

在Python中，**异常**（Exception）是程序运行时发生的错误事件，它会中断程序的正常执行流程。异常可以是可预见的（如文件不存在），也可以是不可预见的（如网络中断）。

### 📌 常见异常类型
| 异常类型          | 触发场景                      | 处理建议                  |
|-------------------|-------------------------------|---------------------------|
| `ValueError`      | 无效的值（如字符串转整数失败） | 验证输入合法性            |
| `KeyError`        | 字典键不存在                  | 使用`get()`方法替代       |
| `IndexError`      | 列表索引越界                  | 检查列表长度              |
| `FileNotFoundError` | 文件路径错误                | 路径合法性校验            |
| `TypeError`       | 操作应用于不适当类型          | 类型检查与转换            |

💡 **为什么处理异常很重要？**  
未处理的异常会导致程序直接崩溃，甚至可能引发数据丢失或系统不稳定。良好的异常处理可以提升程序的健壮性和用户体验。

---

## 🛠 二、异常处理基础

### 1️⃣ `try...except` 语法
```python
try:
    x = 10 / 0  # 触发 ZeroDivisionError
except ZeroDivisionError as e:
    print(f"捕获到异常: {e}")  # 输出：捕获到异常: division by zero
```

### 2️⃣ `else` 与 `finally`
- `else`: 无异常时执行。
- `finally`: 无论是否异常，始终执行（用于资源清理）。

```python
try:
    f = open("example.txt", "r")
    content = f.read()
except FileNotFoundError as e:
    print(f"文件未找到: {e}")
else:
    print("文件内容读取成功！")
finally:
    f.close() if 'f' in locals() else None  # 确保文件关闭
```

---

## ⚙️ 三、进阶异常处理技巧

### 1️⃣ 多异常捕获
```python
try:
    config = json.load(open("config.json"))
    port = int(config["server"]["port"])
except (FileNotFoundError, json.JSONDecodeError):
    print("配置文件加载失败，使用默认配置")
    port = 8080
except KeyError:
    print("端口配置缺失，使用默认端口")
    port = 8080
```

### 2️⃣ 上下文管理器（`with` 语句）
优雅地处理资源释放（如文件、数据库连接）：
```python
with open("data.txt", "r") as f:
    content = f.read()  # 自动关闭文件
```

---

## 🔧 四、自定义异常

### ✨ 创建自定义异常类
```python
class DataUnavailableError(Exception):
    def __init__(self, message="数据获取失败"):
        self.message = message
        super().__init__(self.message)

def fetch_data():
    raise DataUnavailableError("服务器无响应")

try:
    fetch_data()
except DataUnavailableError as e:
    print(f"自定义异常: {e}")  # 输出：自定义异常: 服务器无响应
```

---

## 🔗 五、异常链与传播

### 🔄 异常链（保留原始异常信息）
```python
try:
    x = 10 / 0  # 触发 ZeroDivisionError
except ZeroDivisionError as original:
    raise ValueError("除数不能为零") from original

# 输出:
# ValueError: 除数不能为零
# The above exception was the direct cause of the following exception:
# ZeroDivisionError: division by zero
```

---

## 🧹 六、异常处理最佳实践

### ✅ 建议清单
1. **精准捕获异常类型**：避免捕获过于宽泛的异常（如 `Exception`）。
2. **提供有用错误信息**：在 `except` 块中记录或输出详细错误信息。
3. **避免空 `except` 块**：空的 `except` 会静默忽略错误。
4. **合理使用 `finally`**：释放资源（如关闭文件、数据库连接）。
5. **文档化异常**：在函数文档中说明可能抛出的异常类型。

---

## 🛠 七、实战案例：智能文件备份工具

### 📁 功能需求
- 备份文件或文件夹。
- 捕获常见错误（权限错误、路径不存在等）。
- 记录日志。

```python
import shutil
import os

def safe_backup(src, dst):
    try:
        if not os.path.exists(src):
            raise FileNotFoundError(f"源文件 {src} 不存在")
        shutil.copytree(src, dst) if os.path.isdir(src) else shutil.copy(src, dst)
    except (PermissionError, NotADirectoryError) as e:
        print(f"权限错误: {e}")
        return False
    except Exception as e:
        print(f"未知错误: {type(e).__name__}")
        return False
    else:
        print(f"✅ 备份成功：{src} → {dst}")
        return True
    finally:
        print("== 备份操作日志已记录 ==")

# 使用示例
safe_backup("重要文档.txt", "D:/backup/文档备份.txt")
```

---

## 🧪 八、调试技巧

### 🛠 使用 `pdb` 调试
```python
import pdb

def divide(a, b):
    return a / b

def debug_divide():
    a = 10
    b = 0
    pdb.set_trace()  # 设置断点
    result = divide(a, b)
    print(f"结果是: {result}")

debug_divide()
```

### 💡 调试命令
| 命令 | 作用                     |
|------|--------------------------|
| `n`  | 执行下一行               |
| `s`  | 进入函数内部             |
| `c`  | 继续执行到下一个断点     |
| `p`  | 打印变量值               |
| `q`  | 退出调试器               |

---

## 📚 九、总结

异常处理是编写健壮程序的关键技能。通过掌握 `try...except`、自定义异常、异常链等技巧，你可以：
- **防止程序崩溃** 🚫
- **提高代码可维护性** 🛠
- **优化用户体验** 😊

