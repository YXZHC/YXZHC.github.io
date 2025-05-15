# 🐧 Linux 命令大全 —— 从入门到熟练

Linux 是一个强大而灵活的操作系统，广泛用于服务器、开发环境以及云计算领域。掌握常用的 Linux 命令不仅能提升你的工作效率，还能让你更好地理解和掌控系统运行状态。本文将带你走进 Linux 的世界，学习最实用的命令，并附上示例和小贴士，助你快速上手！🚀

---

## 📌 基础概念

在开始之前，先了解几个基本概念：

- **终端（Terminal）**：用户与操作系统交互的界面。
- **Shell**：命令行解释器，负责执行用户输入的命令（如 bash、zsh 等）。
- **路径（Path）**：
  - 绝对路径：以 `/` 开头，表示完整路径（例如 `/home/user/documents`）。
  - 相对路径：相对于当前目录的路径（例如 `./documents`）。

---

## 🧭 常用命令分类详解

### 1️⃣ 文件与目录操作

#### 🔍 查看当前所在目录
```bash
pwd
```

#### 🗂️ 列出当前目录内容
```bash
ls
ls -l   # 显示详细信息
ls -a   # 显示隐藏文件
```

#### 📁 进入指定目录
```bash
cd /path/to/directory
cd ..    # 返回上一级目录
cd ~     # 回到主目录
```

#### 📄 创建新文件
```bash
touch filename.txt
```

#### 📁 创建新目录
```bash
mkdir directory_name
mkdir -p a/b/c  # 递归创建多级目录
```

#### 🚮 删除文件或目录
```bash
rm filename.txt
rm -r directory_name  # 删除整个目录及其内容
```

#### ✏️ 移动/重命名文件
```bash
mv oldname.txt newname.txt
mv file.txt /new/path/
```

#### 📋 复制文件
```bash
cp source.txt destination.txt
cp -r folder/ new_folder/  # 复制目录
```

---

### 2️⃣ 文件查看与编辑

#### 👀 查看文件内容
```bash
cat filename.txt
less filename.txt  # 分页查看大文件
head filename.txt  # 查看前几行
tail filename.txt  # 查看最后几行
```

#### 🖹 编辑文件（使用 Vim）
```bash
vim filename.txt
```
> 💡 小提示：Vim 模式说明：
> - 按 `i` 进入插入模式
> - 按 `Esc` 退出插入模式
> - 输入 `:wq` 保存并退出
> - 输入 `:q!` 不保存强制退出

---

### 3️⃣ 权限管理

Linux 是一个多用户系统，权限控制非常重要。

#### 🔒 查看文件权限
```bash
ls -l
# 输出示例： -rw-r--r-- 1 user group 0 Apr 5 10:00 file.txt
```

#### 🔧 修改权限
```bash
chmod 755 filename.txt
# 7 = rwx, 5 = r-x
```

#### 🧑‍💻 修改所有者
```bash
chown user:group filename.txt
```

---

### 4️⃣ 用户与进程管理

#### 👤 查看当前登录用户
```bash
whoami
```

#### 🕵️ 查看运行中的进程
```bash
ps aux
top      # 实时监控系统资源
htop     # 更友好的 top 替代工具（需安装）
```

#### 🚫 结束进程
```bash
kill PID
kill -9 PID  # 强制结束
```

---

### 5️⃣ 网络相关命令

#### 🌐 查看 IP 地址
```bash
ip addr show
ifconfig   # 旧版命令（部分系统仍可用）
```

#### 📡 测试网络连通性
```bash
ping google.com
```

#### 📦 下载文件
```bash
wget http://example.com/file.txt
curl -O http://example.com/file.txt
```

---

### 6️⃣ 系统信息查看

#### ⚙️ 查看系统版本
```bash
uname -a
cat /etc/os-release
```

#### 💾 查看磁盘空间
```bash
df -h
```

#### 🧠 查看内存使用情况
```bash
free -h
```

#### 📅 查看当前日期时间
```bash
date
```

---

## 🧪 高级技巧与组合命令

### 🔥 使用管道符（`|`）组合命令
```bash
ps aux | grep "python"
# 查找所有包含 python 的进程
```

### 📊 使用 `>` 和 `>>` 重定向输出
```bash
echo "Hello World" > output.txt  # 覆盖写入
echo "Another line" >> output.txt  # 追加写入
```

### 🔄 使用别名简化命令
```bash
alias ll='ls -l'
ll  # 现在可以使用 ll 快速列出详细信息
```


**小贴士**: 每天花几分钟练习命令，你会越来越熟练！试着在虚拟机或云服务器上动手实践吧 🌟！