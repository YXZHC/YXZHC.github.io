# C++ 学习笔记



# 一、C++ 初识

## 1、C++ 简介

C++ 是一种高级语言，它是由 Bjarne Stroustrup 于 1979 年在贝尔实验室开始设计开发的。C++ 进一步扩充和完善了 C 语言，是一种面向对象的程序设计语言。C++ 可运行于多种平台上，如 Windows、MAC 操作系统以及 UNIX 的各种版本。

C++ 是一种静态类型的、编译式的、通用的、大小写敏感的、不规则的编程语言，支持过程化编程、面向对象编程和泛型编程。C++ 程序的源文件通常使用扩展名 .cpp、.cp 或 .c。

```C++
#include <iostream>
using namespace std;
int main()
{
    cout << "Hello, world!" << endl;	// 打印“Hello, world”
    return 0;
}
```



### 面向对象程序设计

C++ 完全支持面向对象的程序设计，包括面向对象开发的四大特性：

- **封装（Encapsulation）**：封装是将数据和方法组合在一起，对外部隐藏实现细节，只公开对外提供的接口。这样可以提高安全性、可靠性和灵活性。
- **继承（Inheritance）**：继承是从已有类中派生出新类，新类具有已有类的属性和方法，并且可以扩展或修改这些属性和方法。这样可以提高代码的复用性和可扩展性。
- **多态（Polymorphism）**：多态是指同一种操作作用于不同的对象，可以有不同的解释和实现。它可以通过接口或继承实现，可以提高代码的灵活性和可读性。
- **抽象（Abstraction）**：抽象是从具体的实例中提取共同的特征，形成抽象类或接口，以便于代码的复用和扩展。抽象类和接口可以让程序员专注于高层次的设计和业务逻辑，而不必关注底层的实现细节。



### C++ 标准库

标准的 C++ 由三个重要部分组成：

- 核心语言，提供了所有构件块，包括变量、数据类型和常量，等等。
- C++ 标准库，提供了大量的函数，用于操作文件、字符串等。
- 标准模板库（STL），提供了大量的方法，用于操作数据结构等。



### ANSI 标准

ANSI 标准是为了确保 C++ 的便携性 —— 您所编写的代码在 Mac、UNIX、Windows、Alpha 计算机上都能通过编译。由于 ANSI 标准已稳定使用了很长的时间，所有主要的 C++ 编译器的制造商都支持 ANSI 标准。



### C++ 的学习

学习 C++，关键是要理解概念，多看、多想、多练或者开发实例来提升经验，而不应过于深究语言的技术细节。

学习程序设计语言的目的是为了成为一个更好的程序员，也就是说，是为了能更有效率地设计和实现新系统，以及维护旧系统。

C++ 支持多种编程风格。您可以使用 Fortran、C、Smalltalk 等任意一种语言的编程风格来编写代码。每种风格都能有效地保证运行时间效率和空间效率。



### C++ 的使用

C++ 语言在许多行业和领域都有广泛应用，包括：

- 游戏开发：C++ 是游戏开发领域中最常用的编程语言之一，因为它具有高效的性能和直接控制硬件的能力。许多主要的游戏引擎，如 Unreal Engine 和 Unity，都使用 C++ 编写。
- 嵌入式系统开发：C++ 可以在嵌入式系统中发挥重要作用，如智能手机、汽车、机器人和家电等领域。由于嵌入式系统通常具有严格的资源限制和实时要求，因此 C++ 的高效性能和内存控制功能非常有用。
- 金融领域：C++ 在金融领域中被广泛应用，如高频交易、算法交易和风险管理等领域。由于这些应用程序需要高效的性能和对硬件的直接控制，C++ 语言是一个合适的选择。
- 图形图像处理：C++ 可以用于开发图形和图像处理应用程序，如计算机视觉、计算机图形学和人工智能领域。由于这些应用程序需要高效的计算能力和对硬件的控制，因此 C++ 是一个很好的选择。
- 科学计算和数值分析：C++ 可以用于开发科学计算和数值分析应用程序，如数值模拟和高性能计算等领域。由于这些应用程序需要高效的计算能力和对硬件的直接控制，C++ 语言是一个很好的选择。



### 标准化

| 发布时间 | 通称                    | 备注                       |
| :------- | :---------------------- | :------------------------- |
| 2020     | C++20, C++2a            | ISO/IEC 14882:2020         |
| 2017     | C++17                   | 第五个C++标准              |
| 2017     | coroutines TS           | 协程库扩展                 |
| 2017     | ranges TS               | 提供范围机制               |
| 2017     | library fundamentals TS | 标准库扩展                 |
| 2016     | concurrency TS          | 用于并发计算的扩展         |
| 2015     | concepts TS             | 概念库，用于优化编译期信息 |
| 2015     | TM TS                   | 事务性内存操作             |
| 2015     | parallelism TS          | 用于并行计算的扩展         |
| 2015     | filesystem TS           | 文件系统                   |
| 2014     | C++14                   | 第四个C++标准              |
| 2011     | -                       | 十进制浮点数扩展           |
| 2011     | C++11                   | 第三个C++标准              |
| 2010     | -                       | 数学函数扩展               |
| 2007     | C++TR1                  | C++技术报告：库扩展        |
| 2006     | -                       | C++性能技术报告            |
| 2003     | C++03                   | 第二个C++标准              |
| 1998     | C++98                   | 第一个C++标准              |





## 2、C++ 环境配置

### Windows 上安装

##### 下载MinGW：

下载地址：https://sourceforge.net/projects/mingw-w64/files/

下载文件：进入网站，关闭翻译功能，不要点击“Downlod Latest Version”，往下滑，找到最新版的“x86_64-posix-seh”。

##### 安装MinGW：

下载后是一个压缩包，解压后移动到你想安装的位置即可。这里推荐安装位置是：

C:\Program Files (x86)\mingw64

##### 配置环境变量：

配置对象：WinGW，把你刚刚安装WinGW的路径复制一下

配置环境变量：到达第7步之后，所有打开的系统窗口都要按下确定，否则会失败。

【注意】：win7需要添加路径，不要覆盖了。万一真的覆盖了，点击取消重来一遍，只要不点确定啥都好说 					>o<

![image-20240108090421353](C:\Users\HOH\AppData\Roaming\Typora\typora-user-images\image-20240108090421353.png)

##### 验证环境变量是否配置成功：

按下 **win + R**，输出 **cmd** 进入终端之后，输入 **g++** 再回车，如果提示信息[1]，则环境变量配置成功。如果提示信息[2]，则环境变量配置失败。

**[1]**：g++: fatal error: no input files

**[2]**：'g++' 不是内部或外部命令，也不是可运行的程序或批处理文件。



### Visual Studio Code 配置C和C++编程环境

VSCode是一款微软出的轻量级编辑器，它本身只是一款文本编辑器而已，所有的功能都是以插件扩展的形式所存在，想用什么功能就安装对应的扩展即可，非常方便，同时也支持非常多的主题和图标，外观比较好看，重要的是VSCode支持各大主流操作系统，包括Windows、Linux和Mac OS。所以就选择它作为自己的一款主要的编辑器来使用。

##### 安装VSCode

直接去[VSCode官网](https://link.zhihu.com/?target=https%3A//code.visualstudio.com/)下载对应操作系统版本的安装包即可。因为我使用的是64位的Windows，所以下载的是64位的exe文件，直接打开下载好的.exe文件运行安装即可，步骤比较简单。

【注意】在安装到”选择其他任务“界面，需要确认勾选”添加到PATH(重启后生效)“选项，其他选项自行选择。

![image-20240108093924014](C:\Users\HOH\AppData\Roaming\Typora\typora-user-images\image-20240108093924014.png)

##### 设置中文环境

打开VSCode后，首先是欢迎界面。可以看到，这里默认的是英文环境。按照以下步骤设置，第4步完成之后，重启VSCode即可完成中文环境配置。

![v2-f21191dcc3f14d0890328be18a48a3f0_b](C:\Users\HOH\Desktop\C++ 学习笔记\v2-f21191dcc3f14d0890328be18a48a3f0_b.jpg)

##### 安装C/C++扩展

在VSCode左侧栏进入商店，搜索以下扩展进行安装：

- **C/C++**

- **C/C++ Extension Pack**

- **C/C++ Extension Pack**

![image-20240108095117579](C:\Users\HOH\AppData\Roaming\Typora\typora-user-images\image-20240108095117579.png)

安装完成后，需要重启VSCode让扩展生效。

##### 配置*launch.json*、*tasks.json*文件

1. 新建 hello.cpp 文件（以最简单的 Hello C++ 为例）

   先在本地新建一个文件夹，从 VSCode 工作区打开文件夹，然后新建一个后缀为 .cpp 的文件，输入下面代码。

   ```c++
   #include <iostream>
   using namespace std;
   
   int main()
   {
       // 输出打印语句，在屏幕中输出 你好 C++!
       cout << "你好 C++!" << endl;
       return 0;
   }
   ```

   

2. 创建 launch.json 文件

   进入调试界面，点击 ”创建 launch.json 文件“，此时顶部出现一个弹窗，选择”C++(GBD/LLDB)“

   ![image-20240108100937087](C:\Users\HOH\AppData\Roaming\Typora\typora-user-images\image-20240108100937087.png)

3. 创建 tasks.json 文件

   然后我们看向界面右上角，点击运行旁边的下箭头，选择”运行C/C++文件“，此时弹窗上选择g++，生成 tasks.json 文件。或者返回.cpp文件，按F5进行调试，会弹出找不到任务"task g++"，选择 "配置任务"，会自动生成 tasks.json 文件。

   ![image-20240108101424648](C:\Users\HOH\AppData\Roaming\Typora\typora-user-images\image-20240108101424648.png)

4. 配置 launch.json、tasks.json 文件

   ![image-20240108102248187](C:\Users\HOH\AppData\Roaming\Typora\typora-user-images\image-20240108102248187.png)

   ![image-20240108102909536](C:\Users\HOH\AppData\Roaming\Typora\typora-user-images\image-20240108102909536.png)

5. 配置 launch.json 文件

   ```json
   {
       // 使用 IntelliSense 了解相关属性。 
       // 悬停以查看现有属性的描述。
       // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
       "version": "0.2.0",
       "configurations": [
           {
               "name": "g++.exe - 生成和调试活动文件",
               "type": "cppdbg",
               "request": "launch",
               "program": "${fileDirname}\\${fileBasenameNoExtension}.exe",
               "args": [],
               "stopAtEntry": false,
               "cwd": "${workspaceFolder}",
               "environment": [],
               "externalConsole": true, //修改此处
               "MIMode": "gdb",
               "miDebuggerPath": "C:\\Program Files\\mingw64\\bin\\gdb.exe", //修改路径
               "setupCommands": [
                   {
                       "description": "为 gdb 启用整齐打印",
                       "text": "-enable-pretty-printing",
                       "ignoreFailures": true
                   }
               ],
               "preLaunchTask": "g++" //修改此处，与 tasks.json文件中的label的值相同
           }
       ]
   }
   ```

6. 配置  tasks.json 文件

   ```json
   {
       "tasks": [
           {
               "type": "cppbuild",
               "label": "g++",  //修改此处，与 launch.json文件中的值相同
               "command": "C:\\Program Files\\mingw64\\bin\\g++.exe", //修改路径
               "args": [
                   "-g",
                   "${file}",
                   "-o",
                   "${fileDirname}\\${fileBasenameNoExtension}.exe"
               ],
               "options": {
                   "cwd": "${workspaceFolder}"
               },
               "problemMatcher": [
                   "$gcc"
               ],
               "group": {
                   "kind": "build",
                   "isDefault": true
               },
               "detail": "调试器生成的任务。"
           }
       ],
       "version": "2.0.0"
   }
   ```

7.  运行

   返回 hello.cpp 文件，按F5调试，发现完全OK了！

   【注】每个文件夹中都会有这么一个.vscode配置文件。将此文件夹放在常用文件夹顶层，就不需要重复配置了。在.vscode文件夹中，新建两个（只需两个）配置文件，即launch.json、tasks.json。将上面内容复制进去即可，或则将.vscode文件夹复制到自己对应的项目文件中

   vs code中项目路径不支持中文路径。

##### Vscode输出中文乱码情况的解决

Vscode配置好c++编译环境之后，在实用**vscode调试**代码输出中文字符的时候出现了**中文乱码**的情况，

![](C:\Users\HOH\Desktop\C++ 学习笔记\图片1.png)

**解决办法很简单：**
修改代码在文本编辑器（vscode）中的保存格式即可。vscode默认的编码格式为UTF8, 

我们通过重新编码以gbk格式保存就可以了。调试即可正常显示中文，如下：

![在这里插入图片描述](file:///C:/Users/HOH/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

 ![在这里插入图片描述](file:///C:/Users/HOH/AppData/Local/Temp/msohtmlclip1/01/clip_image006.png)

 ![在这里插入图片描述](file:///C:/Users/HOH/AppData/Local/Temp/msohtmlclip1/01/clip_image008.png)

**小结一下**
编码转换原理如下（了解就行）：
这里有点类似，编译器必须知道你的源文件保存的编码! （编译器要得到正确的二进制代码，所以必须知道编码格式（即保存的字符与二进制码的对应关系））
编译器gcc默认使用UTF8编码，所以用MinGW编译的源文件中有中文宽字符必须保存为UTF-8编码。而VS默认是ANSI码（跟随windows系统，一般就是我们说的gbk编码）,如果你用mingw编译ANSI编码保存的源文件,一般会出错。我们在Vscode上面就是告诉编译器，我们的代码保存格式，让他能够找到对应关系。





# 二、C++ 基础教程

## 1、基本语法

### 注释

作用：

注释可以用于解释代码的目的、变量的意义、函数的作用和算法的步骤等。 编写良好的注释可以提高码的可读性和可维护性，方便自己或其他程序员阅读代码。

两种格式：

1.单行注释：`// 注释信息`

2.多行注释：`/* 注释信息 */`



### 变量与常量

**变量(variable)：**

作用：给一段指定的内存空间起名，方便操作。运行时数据可变

语法：

> **数据类型 变量名 = 初始值**

```c++
int day = 365;		//定义一个叫day的变量，初始值为365
```



**常量(constant)：**

作用：记录程序中不能更改的数据。运行时数据不可变

两种语法：

1.  #define 宏常量：		（通常在文件上方定义，表示一个常量）

   > **#define 常量名 初始值**

   ```c++
   #define month 12		//宏定义常量 month，初始值为12
   ```

2.  const修饰的变量：      （通常在变量定义前加关键字，修饰该变量为常量）

   > **const 数据类型 变量名 = 初始值**

   ```c++
   const int year = 2024;		//用 const 修饰变量year，将其变成不可更改
   ```

### 关键字

作用：关键字是C++中预先保留的单词（标识符）

【注意】**在定义变量或者常量的时候，不要使用关键字来命名变量或常量**

C++ 关键字如下：

| [`alignas`](https://learn.microsoft.com/zh-cn/cpp/cpp/alignas-specifier?view=msvc-170) | [`char16_t`](https://learn.microsoft.com/zh-cn/cpp/cpp/char-wchar-t-char16-t-char32-t?view=msvc-170) | [`decltype`](https://learn.microsoft.com/zh-cn/cpp/cpp/decltype-cpp?view=msvc-170) | [`friend`](https://learn.microsoft.com/zh-cn/cpp/cpp/friend-cpp?view=msvc-170) | [`or`](https://learn.microsoft.com/zh-cn/cpp/cpp/logical-or-operator-pipe-pipe?view=msvc-170)b |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`alignof`](https://learn.microsoft.com/zh-cn/cpp/cpp/alignof-operator?view=msvc-170) | [`char32_t`](https://learn.microsoft.com/zh-cn/cpp/cpp/char-wchar-t-char16-t-char32-t?view=msvc-170) | [`default`](https://learn.microsoft.com/zh-cn/cpp/cpp/switch-statement-cpp?view=msvc-170) | [`goto`](https://learn.microsoft.com/zh-cn/cpp/cpp/goto-statement-cpp?view=msvc-170) | [`or_eq`](https://learn.microsoft.com/zh-cn/cpp/cpp/assignment-operators?view=msvc-170)b |
| [`and`](https://learn.microsoft.com/zh-cn/cpp/cpp/logical-and-operator-amp-amp?view=msvc-170)b | [`class`](https://learn.microsoft.com/zh-cn/cpp/cpp/class-cpp?view=msvc-170) | [`delete`](https://learn.microsoft.com/zh-cn/cpp/cpp/delete-operator-cpp?view=msvc-170) | [`if`](https://learn.microsoft.com/zh-cn/cpp/cpp/if-else-statement-cpp?view=msvc-170) | [`private`](https://learn.microsoft.com/zh-cn/cpp/cpp/private-cpp?view=msvc-170) |
| [`and_eq`](https://learn.microsoft.com/zh-cn/cpp/cpp/assignment-operators?view=msvc-170)b | [`compl`](https://learn.microsoft.com/zh-cn/cpp/cpp/one-s-complement-operator-tilde?view=msvc-170)b | [`do`](https://learn.microsoft.com/zh-cn/cpp/cpp/do-while-statement-cpp?view=msvc-170) | [`inline`](https://learn.microsoft.com/zh-cn/cpp/cpp/inline-functions-cpp?view=msvc-170) | [`protected`](https://learn.microsoft.com/zh-cn/cpp/cpp/protected-cpp?view=msvc-170) |
| [`asm`](https://learn.microsoft.com/zh-cn/cpp/assembler/inline/asm?view=msvc-170)a | **`concept`**c                                               | [`double`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170) | [`int`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170) | [`public`](https://learn.microsoft.com/zh-cn/cpp/cpp/public-cpp?view=msvc-170) |
| [`auto`](https://learn.microsoft.com/zh-cn/cpp/cpp/auto-cpp?view=msvc-170) | [`const`](https://learn.microsoft.com/zh-cn/cpp/cpp/const-cpp?view=msvc-170) | [`dynamic_cast`](https://learn.microsoft.com/zh-cn/cpp/cpp/dynamic-cast-operator?view=msvc-170) | [`long`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170) | [`register`](https://learn.microsoft.com/zh-cn/cpp/cpp/storage-classes-cpp?view=msvc-170#register) |
| [`bitand`](https://learn.microsoft.com/zh-cn/cpp/cpp/bitwise-and-operator-amp?view=msvc-170)b | [`const_cast`](https://learn.microsoft.com/zh-cn/cpp/cpp/const-cast-operator?view=msvc-170) | [`else`](https://learn.microsoft.com/zh-cn/cpp/cpp/if-else-statement-cpp?view=msvc-170) | [`mutable`](https://learn.microsoft.com/zh-cn/cpp/cpp/mutable-data-members-cpp?view=msvc-170) | [`reinterpret_cast`](https://learn.microsoft.com/zh-cn/cpp/cpp/reinterpret-cast-operator?view=msvc-170) |
| [`bitor`](https://learn.microsoft.com/zh-cn/cpp/cpp/bitwise-inclusive-or-operator-pipe?view=msvc-170)b | **`consteval`**c                                             | [`enum`](https://learn.microsoft.com/zh-cn/cpp/cpp/enumerations-cpp?view=msvc-170) | [`namespace`](https://learn.microsoft.com/zh-cn/cpp/cpp/namespaces-cpp?view=msvc-170) | **`requires`**c                                              |
| [`bool`](https://learn.microsoft.com/zh-cn/cpp/cpp/bool-cpp?view=msvc-170) | [`constexpr`](https://learn.microsoft.com/zh-cn/cpp/cpp/constexpr-cpp?view=msvc-170) | [`explicit`](https://learn.microsoft.com/zh-cn/cpp/cpp/user-defined-type-conversions-cpp?view=msvc-170) | [`new`](https://learn.microsoft.com/zh-cn/cpp/cpp/new-operator-cpp?view=msvc-170) | [`return`](https://learn.microsoft.com/zh-cn/cpp/cpp/return-statement-cpp?view=msvc-170) |
| [`break`](https://learn.microsoft.com/zh-cn/cpp/cpp/break-statement-cpp?view=msvc-170) | **`constinit`**c                                             | **`export`**c                                                | [`noexcept`](https://learn.microsoft.com/zh-cn/cpp/cpp/noexcept-cpp?view=msvc-170) | [`short`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170) |
| [`case`](https://learn.microsoft.com/zh-cn/cpp/cpp/switch-statement-cpp?view=msvc-170) | [`continue`](https://learn.microsoft.com/zh-cn/cpp/cpp/continue-statement-cpp?view=msvc-170) | [`extern`](https://learn.microsoft.com/zh-cn/cpp/cpp/extern-cpp?view=msvc-170) | [`not`](https://learn.microsoft.com/zh-cn/cpp/cpp/logical-negation-operator-exclpt?view=msvc-170)b | [`signed`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170) |
| [`catch`](https://learn.microsoft.com/zh-cn/cpp/cpp/try-throw-and-catch-statements-cpp?view=msvc-170) | **`co_await`**c                                              | [`false`](https://learn.microsoft.com/zh-cn/cpp/cpp/false-cpp?view=msvc-170) | [`not_eq`](https://learn.microsoft.com/zh-cn/cpp/cpp/equality-operators-equal-equal-and-exclpt-equal?view=msvc-170)b | [`sizeof`](https://learn.microsoft.com/zh-cn/cpp/cpp/sizeof-operator?view=msvc-170) |
| [`char`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170) | **`co_return`**c                                             | [`float`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170) | [`nullptr`](https://learn.microsoft.com/zh-cn/cpp/cpp/nullptr?view=msvc-170) | [`static`](https://learn.microsoft.com/zh-cn/cpp/cpp/storage-classes-cpp?view=msvc-170) |
| [`char8_t`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170)c | **`co_yield`**c                                              | [`for`](https://learn.microsoft.com/zh-cn/cpp/cpp/for-statement-cpp?view=msvc-170) | [`operator`](https://learn.microsoft.com/zh-cn/cpp/cpp/operator-overloading?view=msvc-170) | [`static_assert`](https://learn.microsoft.com/zh-cn/cpp/cpp/static-assert?view=msvc-170) |
| [`struct`](https://learn.microsoft.com/zh-cn/cpp/cpp/struct-cpp?view=msvc-170) | [`switch`](https://learn.microsoft.com/zh-cn/cpp/cpp/switch-statement-cpp?view=msvc-170) | [`template`](https://learn.microsoft.com/zh-cn/cpp/cpp/templates-cpp?view=msvc-170) | [`this`](https://learn.microsoft.com/zh-cn/cpp/cpp/this-pointer?view=msvc-170) | [`thread_local`](https://learn.microsoft.com/zh-cn/cpp/cpp/storage-classes-cpp?view=msvc-170#thread_local) |
| [`throw`](https://learn.microsoft.com/zh-cn/cpp/cpp/try-throw-and-catch-statements-cpp?view=msvc-170) | [`true`](https://learn.microsoft.com/zh-cn/cpp/cpp/true-cpp?view=msvc-170) | [`try`](https://learn.microsoft.com/zh-cn/cpp/cpp/try-throw-and-catch-statements-cpp?view=msvc-170) | [`typedef`](https://learn.microsoft.com/zh-cn/cpp/cpp/aliases-and-typedefs-cpp?view=msvc-170) | [`typeid`](https://learn.microsoft.com/zh-cn/cpp/cpp/typeid-operator?view=msvc-170) |
| [`typename`](https://learn.microsoft.com/zh-cn/cpp/cpp/typename?view=msvc-170) | [`union`](https://learn.microsoft.com/zh-cn/cpp/cpp/unions?view=msvc-170) | [`unsigned`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170) | [`using`](https://learn.microsoft.com/zh-cn/cpp/cpp/using-declaration?view=msvc-170) 声明 | [`using`](https://learn.microsoft.com/zh-cn/cpp/cpp/namespaces-cpp?view=msvc-170#using_directives) 指令 |
| [`virtual`](https://learn.microsoft.com/zh-cn/cpp/cpp/virtual-cpp?view=msvc-170) | [`void`](https://learn.microsoft.com/zh-cn/cpp/cpp/void-cpp?view=msvc-170) | [`volatile`](https://learn.microsoft.com/zh-cn/cpp/cpp/volatile-cpp?view=msvc-170) | [`wchar_t`](https://learn.microsoft.com/zh-cn/cpp/cpp/fundamental-types-cpp?view=msvc-170) | [`while`](https://learn.microsoft.com/zh-cn/cpp/cpp/while-statement-cpp?view=msvc-170) |
| [`xor`](https://learn.microsoft.com/zh-cn/cpp/cpp/bitwise-exclusive-or-operator-hat?view=msvc-170)b | [`xor_eq`](https://learn.microsoft.com/zh-cn/cpp/cpp/assignment-operators?view=msvc-170)b |                                                              |                                                              |                                                              |



### 标识符命名规则

作用：C++规定给标识符（变量、常量）命名时，有一套自己的规则。规则如下：

- 标识符不能是关键字
- 标识符只有由字母、数字、下划线组成
- 第一个字符必须是字母或下划线
- 标识符中字母区分大小写

> 建议：给标识符命名时，争取做到见名知其意的效果，方便自己和他人的阅读。



### 定义与声明的区别

**区别：**内存分配

- 声明只是告诉编译器变量或类型的名称，但并不为它分配内存。
- 定义实际上是为变量或数据类型分配了内存。





## 2、数据类型

使用编程语言进行编程时，需要用到各种变量来存储各种信息。变量保留的是它所存储的值的内存位置。这意味着，当您创建一个变量时，就会在内存中保留一些空间。您可能需要存储各种数据类型（比如字符型、宽字符型、整型、浮点型、双浮点型、布尔型等）的信息，操作系统会根据变量的数据类型，来分配内存和决定在保留内存中存储什么。而数据类型存在的意义，就是给变量分配合适的内存空间。

| 类型     | 关键字  |
| :------- | :------ |
| 布尔型   | bool    |
| 字符型   | char    |
| 整型     | int     |
| 浮点型   | float   |
| 双浮点型 | double  |
| 无类型   | void    |
| 宽字符型 | wchar_t |



### 整型

作用：用于表示整数类型的数据

C++中能够表示整型的类型有以下几种方式，**区别在于所占内存空间不同：**

| 数据类型            | 占用空间（字节）                            | 取值范围                  |
| ------------------- | ------------------------------------------- | ------------------------- |
| short(短整型)       | 2byte                                       | (-2^15~2^15-1) 65535      |
| **int(整型)**       | 4byte                                       | (-2^31~2^31-1) 4294967295 |
| long(长整型)        | Windows 4byte,Linux 4byte(32位) 8byte(64位) | (-2^31~2^31-1) 4294967295 |
| long long(长长整型) | 8byte                                       | (-2^63~2^63-1) 1844兆     |



### sizeof 关键字

作用：sizeof用于统计数据类型所占内存大小，并返回

语法：

> 1、用于数据类型：siziof( 数据类型 ) 

```c++
sizeof(int);
```

> 2、用于变量：sizeof( 变量 )

```c++
sizeof(variable)
```

结论：按内存占用排序 short < int <= long <= long long



### 实型（浮点型）

作用：用于表示小数（可以表示数学中的实数集（还包括 Infinity(无穷)、NaN(不可表示)））

**浮点型变量**分为两种：

1. 单精度 float       （注：小数值默认一般是double类型，可以用"f"转换为float类型）

```c++
float num1 = 3.1415926f;
```

1. 双精度 double

```c++
double num2 = 3.1415926;
```

**区别：**两者区别在于表示的有效数字范围不同，双精度显示范围更广。

| 数据类型 | 占用空间（字节） | 有效数字范围    | 取值范围           |
| -------- | ---------------- | --------------- | ------------------ |
| float    | 4byte            | 7位有效数字     | (-2^149~2^128-1)   |
| double   | 8byte            | 15~16位有效数字 | (-2^1074~2^1024-1) |

【注】C++中默认情况下，输出一个浮点类型，最多会显示**6位**有效数字。



**扩展：科学计数法**：

```c++
float f1 = 3e2;     //3 * 10^2 = 300
float f1 = 3e-2;    //3 * 0.1^2 = 0.03
```



### 字符型

作用：字符型变量用于显示单个字符

语法：

```c++
char ch = 'a';
```

> 【注意1】在显示字符型变量时，用单引号将字符括起来，不能用双引号
>
> 【注意2】单引号内只能有一个字符，也不可以中文字符()

- 字符型变量并不是把字符本身放到内存中存储，而是将对应的ASCII编码放入到存储单元

| 数据类型 | 占用空间（字节） | 取值范围 |
| -------- | ---------------- | -------- |
| char     | 1byte            |          |

示例：

```c++
int main()
{
    char ch = 'a';
    cout << ch << endl;
    cout << sizeof(char) << endl;

    cout << (int)ch << endl;  //使用强制转换查看字符a对应的ASCII码

    char ch = 'A';    //可以直接用ASCII码给字符型变量赋值
    cout << ch << endl;

    return 0;
}
```

### [ASCII](https://en.cppreference.com/w/cpp/language/ascii)码表

大致由以下两部分组成：

- ASCII 非打印控制字符：ASCII表上的数字**0-31**分配给了控制字符，用于控制像打印机等一些外围设备。
- ASCII 打印字符：数字**32-126**分配给了能在键盘上找到的字符，当查看或打印文档时就会出现。

**ASCII码表**

| **ASCII值** | **控制字符** | **ASCII值** | **控制字符** | **ASCII值** | **控制字符** | **ASCII值** | **控制字符** |
| ----------- | ------------ | ----------- | ------------ | ----------- | ------------ | ----------- | ------------ |
| 0           | NUL          | 32          | (space)      | 64          | @            | 96          | 、           |
| 1           | SOH          | 33          | ！           | 65          | A            | 97          | a            |
| 2           | STX          | 34          | ”            | 66          | B            | 98          | b            |
| 3           | ETX          | 35          | #            | 67          | C            | 99          | c            |
| 4           | EOT          | 36          | $            | 68          | D            | 100         | d            |
| 5           | ENQ          | 37          | %            | 69          | E            | 101         | e            |
| 6           | ACK          | 38          | &            | 70          | F            | 102         | f            |
| 7           | BEL          | 39          | '            | 71          | G            | 103         | g            |
| 8           | BS           | 40          | (            | 72          | H            | 104         | h            |
| 9           | HT           | 41          | )            | 73          | I            | 105         | i            |
| 10          | LF           | 42          | *            | 74          | J            | 106         | j            |
| 11          | VT           | 43          | +            | 75          | K            | 107         | k            |
| 12          | FF           | 44          | ,            | 76          | L            | 108         | l            |
| 13          | CR           | 45          | -            | 77          | M            | 109         | m            |
| 14          | SO           | 46          | .            | 78          | N            | 110         | n            |
| 15          | SI           | 47          | /            | 79          | O            | 111         | o            |
| 16          | DLE          | 48          | 0            | 80          | P            | 112         | p            |
| 17          | DCI          | 49          | 1            | 81          | Q            | 113         | q            |
| 18          | DC2          | 50          | 2            | 82          | R            | 114         | r            |
| 19          | DC3          | 51          | 3            | 83          | X            | 115         | s            |
| 20          | DC4          | 52          | 4            | 84          | T            | 116         | t            |
| 21          | NAK          | 53          | 5            | 85          | U            | 117         | u            |
| 22          | SYN          | 54          | 6            | 86          | V            | 118         | v            |
| 23          | TB           | 55          | 7            | 87          | W            | 119         | w            |
| 24          | CAN          | 56          | 8            | 88          | X            | 120         | x            |
| 25          | EM           | 57          | 9            | 89          | Y            | 121         | y            |
| 26          | SUB          | 58          | :            | 90          | Z            | 122         | z            |
| 27          | ESC          | 59          | ;            | 91          | [            | 123         | {            |
| 28          | FS           | 60          | <            | 92          | \            | 124         | \|           |
| 29          | GS           | 61          | =            | 93          | ]            | 125         | }            |
| 30          | RS           | 62          | >            | 94          | ^            | 126         | ~            |
| 31          | US           | 63          | ?            | 95          | —            | 127         | DEL          |

**ASCII诠释部分**

ASCII中的0~31为控制字符；32~126为打印字符；127为Delete(删除)命令。下表为控制字符释义。

| **十进制** | **十六进制** | **字符**   | **十进制** | **十六进制** | **字符**     |
| ---------- | ------------ | ---------- | ---------- | ------------ | ------------ |
| 0          | 00           | 空         | 16         | 10           | 数据链路转意 |
| 1          | 01           | 头标开始   | 17         | 11           | 设备控制 1   |
| 2          | 02           | 正文开始   | 18         | 12           | 设备控制 2   |
| 3          | 03           | 正文结束   | 19         | 13           | 设备控制 3   |
| 4          | 04           | 传输结束   | 20         | 14           | 设备控制 4   |
| 5          | 05           | 查询       | 21         | 15           | 反确认       |
| 6          | 06           | 确认       | 22         | 16           | 同步空闲     |
| 7          | 07           | 震铃       | 23         | 17           | 传输块结束   |
| 8          | 08           | backspace  | 24         | 18           | 取消         |
| 9          | 09           | 水平制表符 | 25         | 19           | 媒体结束     |
| 10         | 0A           | 换行/新行  | 26         | 1A           | 替换         |
| 11         | 0B           | 竖直制表符 | 27         | 1B           | 转意         |
| 12         | 0C           | 换页/新页  | 28         | 1C           | 文件分隔符   |
| 13         | 0D           | 回车       | 29         | 1D           | 组分隔符     |
| 14         | 0E           | 移出       | 30         | 1E           | 记录分隔符   |
| 15         | 0F           | 移入       | 31         | 1F           | 单元分隔符   |



### 转义字符

作用：用于表示一些不能显示出来的ASCII字符

| 转义字符 | 含义                                | ASCII码值（十进制） | 作用             |
| -------- | ----------------------------------- | ------------------- | ---------------- |
| \a       | 警报                                | 007                 |                  |
| \b       | 退格(BS) ，将当前位置移到前一列     | 008                 |                  |
| \f       | 换页(FF)，将当前位置移到下页开头    | 012                 |                  |
| \n       | 换行(LF) ，将当前位置移到下一行开头 | 010                 |                  |
| \r       | 回车(CR) ，将当前位置移到本行开头   | 013                 |                  |
| \t       | 水平制表(HT) （跳到下一个TAB位置）  | 009                 | 可以整齐输出数据 |
| \v       | 垂直制表(VT)                        | 011                 |                  |
| \\\\     | 代表一个反斜线字符''\'              | 09                  |                  |
| \\'      | 代表一个单引号（撇号）字符          | 039                 |                  |
| \\"      | 代表一个双引号字符                  | 034                 |                  |
| \?       | 代表一个问号                        | 063                 |                  |
| \0       | 空字符(NUL)                         | 000                 |                  |
| \ddd     | 1到3位八进制数所代表的任意字符      | 三位八进制          |                  |
| \xhh     | 十六进制所代表的任意字符            | 十六进制            |                  |

示例：

```c++
int main()
{
    // 换行符 \n
	cout << "Hello world!\n";
	// 反斜杠 \\;
	cout << "打印一个反斜杠：\\" << endl;
	// 水平制表符 \t  (一个\t占8个位置)
	cout << "aaaa\tHello world" << endl;
	cout << "aa\tHello world" << endl;
	cout << "aaaaaaa\tHello world" << endl;
    return 0;
}
```



### 字符串型

作用：用于表示一串字符

两种风格

1. **C风格字符串**   `char var_name[] = "value"`

   ```c++
   char str1[] = "Hello world!";	// 使用字符数组接收字符串
   cout << str1 << endl;
   ```

2. **C++风格字符串**    `string var_name = "value"`

   ```c++
   #include <string>		//需要添加string头文件
   string str2 = "Hello worl";
   string str3 = "hello world";
   str2 += str[10];		//字符串可以使用索引下标
   cout << str2 << endl;
   ```
   
   > 【注意】C++风格字符串，需要加入头文件 `#include <string>`
   >
   > 如需把字符串拆分多行显示，再上一行末尾加入"\\"即可。



### 布尔类型 bool

作用：布尔类型代表真或假的值

bool类型只有两个值：

- true ··· 真（1）
- false ··· 假（0）

bool类型只占用1个字节大小。【注】bool类型，只要非0的值都代表真。

示例：

```c++
int main()
{
    bool bo = true;
    cout << bo << endl;		// 输出：1
    
    bool bo = false;
    cout << bo << endl;		// 输出：0
}
```



### 数据输入

作用：从键盘中获取数据

关键字：cin

语法：`cin >> var_name`

示例：

```c++
int main()
{
	float f = 0.f;
	cout << "请输入浮点型变量：" << endl;
	cin >> f;
	cout << f << endl;
}
```





## 3、运算符

作用：运算符是一种告诉编译器执行特定的数学或逻辑操作的符号。

| 运算符类型 | 作用                                   |
| ---------- | -------------------------------------- |
| 算术运算符 | 用于处理四则运算                       |
| 赋值运算符 | 用于将表达式的值赋给变量               |
| 比较运算符 | 用于表达式的比较，并返回一个真值或假值 |
| 逻辑运算符 | 根据表达式的值返回真值或假值           |
| 位运算符   | 位运算符作用于位，并逐位执行操作       |
| 其他运算符 | C++ 支持的其他一些重要的运算符         |



### 算术运算符

作用：用于处理四则运算

算术运算符包括以下符号：

| 运算符 | 术语       | 示例           | 结果      |
| ------ | ---------- | -------------- | --------- |
| +，+   | 正号，加   | +2，10 + 5     | 2，15     |
| -，-   | 负号，减   | -2，10 - 5     | -2，5     |
| *      | 乘         | 10 * 5         | 50        |
| /      | 除         | 10 / 5         | 2         |
| %      | 取模(取余) | 10 % 3         | 1         |
| ++     | 前置递增   | a=2  b=++a * 5 | a=3  b=15 |
| ++     | 后置递增   | a=2  b=a++ * 5 | a=3  b=10 |
| --     | 前置递减   | a=2  b=--a * 5 | a=1  b=5  |
| --     | 后置递减   | a=2  b=a-- * 5 | a=1  b=10 |

示例：

```c++
int main()
{
    int a = 13;  int b = 4;
    double d1 = 0.5;  double d2 = 0.22;
    
    cout << a + b << endl;		// 17
    cout << a - b << endl;		// 9
    cout << a * b << endl;		// 52
    cout << a / b << endl;		// 3  两个整数相除，结果一定是整数，将小数部分去除
    cout << a % b << endl;		// 1  取模运算的本质，就是求余数(小数不能取模运算)
    
    return 0;
}
```

【总结】

> **取模：**只有整型变量可以进行取模运算
>
> **递增递减：**
>
> 1. 前置递增 先让变量+1，然后进行表达式运算
> 2. 后置递增 先进行表达式运算，然后再让变量+1
> 3. 前置递增 先让变量-1，然后进行表达式运算
> 4. 后置递增 先进行表达式运算，然后再让变量-1



### 赋值运算符

作用：用于将表达式的值赋值给变量

赋值运算符包括以下符号：

| 运算符 | 术语   | 示例             | 展开       | 结果   |
| ------ | ------ | ---------------- | ---------- | ------ |
| =      | 赋值   | a = 2;           | a = 2;     | a = 2; |
| +=     | 加等于 | a = 0; a += 2;   | a = a + 2; | a = 2; |
| -=     | 减等于 | a = 5; a -= 3;   | a = a - 3; | a = 2; |
| *=     | 乘等于 | a = 2; a *= 2;   | a = a * 2; | a = 4; |
| /=     | 除等于 | a = 10; a /=  2; | a = a / 2; | a = 5; |
| %=     | 模等于 | a = 3; a %= 2;   | a = a % 2; | a = 1; |



### 比较运算符

作用：用于表达式的比较，并返回一个真值或假值

比较运算符包括以下符号：

| 运算符 | 术语     | 示例   | 结果      |
| ------ | -------- | ------ | --------- |
| ==     | 相等于   | 2 == 3 | 0   false |
| !=     | 不等于   | 2 != 3 | 1   true  |
| <      | 小于     | 2 < 3  | 1   true  |
| >      | 大于     | 2 > 3  | 0   false |
| <=     | 小于等于 | 2 <= 3 | 1   true  |
| >=     | 大于等于 | 2 >= 3 | 0   false |



### 逻辑运算符

作用：根据表达式的值返回真值或假值

逻辑运算符包括以下符号：

| 运算符 | 术语      | 示例     | 结果                                     |
| ------ | --------- | -------- | ---------------------------------------- |
| &&     | 与（and） | a && b   | 如果a和b都为真，结果为真，否则为假       |
| \|\|   | 或（or）  | a \|\| b | 如果a和b有一个为真，结果为真，全假时为假 |
| !      | 非（non） | !a       | 如果a为假，结果为真；如果a为真，结果为假 |



### 位运算符

作用：位运算符作用于位，并逐位执行操作

详细解释：

- [原码、反码、补码 详解！_原码反码补码-CSDN博客](https://blog.csdn.net/chuixue24/article/details/130607588?ops_request_misc=%7B%22request%5Fid%22%3A%22170521921516800213087150%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=170521921516800213087150&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-4-130607588-null-null.142^v99^pc_search_result_base1&utm_term=原码、反码、补码&spm=1018.2226.3001.4187)

- [位运算符——取反运算符~的理解-CSDN博客](https://blog.csdn.net/qq_55786319/article/details/122353818#:~:text=学习位运算符中的取反运算符—— ~ 时，要搞清楚以下几点： 正数的补码是其原码，原码就是其二进制数表示,负数的补码为符号位不变，原码取反再加一 二进制数有八位数，第一位就是符号位 符号位中，0代表正数，1代表负数 取反即1变0，0变1)

位运算符包括以下符号：

| 运算符 | 术语       | 描述                                                         | 示例     | 结果 |
| ------ | ---------- | ------------------------------------------------------------ | -------- | ---- |
| &      | 按位与     | 按二进制位进行"与"运算                                       | 60 & 13  | 12   |
| \|     | 按位或     | 按二进制位进行"或"运算                                       | 60 \| 13 | 61   |
| ~      | 取反       | 按二进制位进行"取反"运算                                     | ~60      | -61  |
| ^      | 按位异或   | 按二进制位进行"异或"运算                                     | 60 ^ 13  | 49   |
| <<     | 二进制左移 | 将一个运算对象的各二进制位全部左移<br/>若干位（左边的二进制位丢弃，右边补0）。 | 60 << 2  | 240  |
| \>>    | 二进制右移 | 二进制右移运算符。将一个数的各二进制位全部<br>右移若干位，正数左补0，负数左补1，右边丢弃。 | 13 >> 2  | 15   |

示例：

```c++
int main()
{
    int c = 0;
    unsigned int a = 60;    // 60 = 0011 1100	unsigned：用于声明无符号整数类型
    unsigned int b = 13;    // 13 = 0000 1101
    
	c = a & b;             // 12 = 0000 1100
    cout << "& - c的值: " << c << endl;
    c = a | b;             // 61 = 0011 1101
    cout << "| - c的值: " << c << endl;
    c = ~a;                // -61 = 1100 0011
    cout << "~ - c的值: " << c << endl;
    c = a ^ b;             // 49 = 0011 0001
    cout << "^ - c的值: " << c << endl;
    c = a << 2;            // 240 = 1111 0000
    cout << "<< - c的值: " << c << endl;
    c = b >> 2;            // 3 = 0000 0011
    cout << ">> - c的值: " << c << endl;
}
```



## 4、程序流程结构

C/C++支持最基本的三种程序运行结构：顺序结构、选择结构、循环结构

- 顺序结构：程序按顺序执行，不发生跳转
- 选择结构：依据条件是否满足，有选择地执行某段代码
- 循环结构：依据条件是否满足，循环多次执行某段代码

### 选择结构

#### if 语句

作用：分开执行满足条件和不满足条件的语句

if 语句的三种语法形式

1. 多行格式if语句：`if(条件){ 条件满足执行语句 }else{ 条件不满足执行语句 }`

```c++
int main()
{
    int score = 0;
    cout << "请输入分数：" << endl;
    cin >> score;
    
    if(score >= 600)
    {
        cout << "恭喜你考上了大学！" << endl;
    }
    else
    {
        cout << "很遗憾，你未考上大学。" << endl;
    }
    
    return 0;
}
```

2. 多条件的if语句：`if(条件){ 条件满足执行语句 }else if{ 条件不满足执行语句 }...else{ 条件不满足... }`

```c++
int main()
{
    int score = 0;
    cout << "请输入分数：" << endl;
    cin >> score;
    
    if(score >= 600)
    {
        cout << "恭喜你考上了一本大学！" << endl;
    }
    else if(score >= 500)
    {
        cout << "恭喜你考上了二本大学！" << endl;
    }
    else
    {
        cout << "很遗憾，没有考上大学。" << endl;
    }
    
    return 0;
}
```

3. 嵌套if语句：可以嵌套使用if语句，以达到更精准的条件判断。

   案例需求：

   - 提示用户输入考试分数，根据分数做以下判断
   - 考试分数：大于600分视为考上一本，大于500分考上二本，大于400分考上三本，再小于则未考上
   - 一本线：北大分数线680分，清华700分，人大600分

   ```c++
   int main()
   {
       double score = 0;
       cout << "这里是分数线查询小管家，请输入考试分数：" << endl;
       cin >> score;
       
       if(score <= 500)
       {
           if(score <= 400)
           {
               cout << "很遗憾，你未考上本科。但也请不要沮丧，上帝为你关上一扇门，\
   同时也会为你打开一扇窗，你的人生才刚刚开始呢！加油小废物";
           }
           else
           {
               cout << "恭喜你啊！考上了三本大学！\n";
           }
       }
       else if(score <= 600)
       {
           cout << "恭喜你啊！考上了二本大学！\n";
       }
       else
       {
           if(score > 650)
           {
               if(score > 700)
           	{
               	cout << "恭喜你小子啊！考上了清华大学！\n";
           	}
               else
               {
                   cout << "恭喜你小子啊！考上了北京大学！\n";
               }
           }
           else
           {
               cout << "恭喜你小子啊！考上了人民大学！\n";
           }
       }
       return 0;
   }
   ```

   

#### 三目运算符

作用：通过三目运算符实现简单的判断

语法：`表达式1 ? 表达式2 : 表达式3`

```c++
a > B ? a : b;		//如果a = 5,b = 4 结果：5
```

解释：

如果表达式1为真，执行并返回表达式2的结果；

如果表达式1为假，执行并返回表达式3的结果。

示例：

```c++
int main()
{
    // 判断abc中的最大值
	int a = 5;
    int b = 15;
    int c = 10;
    cout << "最大的值是：" << ( (a>b ? a:b)>c ? (a>b ? a:b):c ) << endl;
    
    //三目运算符返回的是变量，可以继续赋值
    ( a>b ? a : b ) = 100;		//将一百赋值给最大的变量
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
    cout << "c = " << c << endl;
    
    return 0;
}
```

【总结】三目运算符既可以在赋值的右边，将结果返回给变量；又可以在赋值的左边，返回的变量接收赋值。



#### switch 语句

作用：可执行多条件分支语句

语法：

```c++
switch(表达式)				// 表达式：根据表达式的结果，判断从哪个分支(case 结果n)开始执行
{
    case 结果1: 			// case：分支		结果：只能是整数或字符型
        执行语句; break;   // break：中断跳出
    case 结果2: 
        执行语句; break;
	...
	default:
        执行语句; break;
}
```

示例：

```c++
int main()
{
    int score = 0;
    // 提示
    cout << "请给电影A打个分：";
    // 用户打分
    cin >> score;
    // 根据分数，提示用户最后的结果
    switch(score)
    {
        case 10:
            cout << "您认为是经典" << endl;
            break;
            break;
        case 9:
            cout << "您认为是很好看" << endl;
            break;
            break;
        default:
            cout << "您认为是烂片" << endl;
    }
    return 0;
}
```

> 注意1：switch语句中的表达式只能是整数或字符类型。
>
> 注意2：case里如果没有break，那么程序会一直向下执行。
>
> 总结：与if语句相比，对于多条件判断时，switch的结构清晰明了，且执行效率高。缺点是switch没法判断			区间。



### 循环结构

#### while循环

作用：满足循环条件判断，执行循环语句

语法：`while(条件判断){循环语句}`

解释：只要循环条件为真，就执行循环语句，直到条件为假结束。

示例：

```c++
int main()
{
    int num = 0;
    while(num < 10)
    {
        cout << "当前循环" << (num+1) << "次" << endl;
        num++;
    }
    return 0;
}
```

> 【注意】在执行循环语句时，程序必须要提供跳出循环的出口，否则出现死循环
>

**while循环练习案例**：猜数字

**案例描述：**系统随机生成一个0到100之间的数字，玩家进行猜测，如果猜错，提示玩家过大过小，如果猜对恭喜玩家胜利，并退出游戏。

```c++
//系统时间头文件
#include <ctime>

int main()
{
    // 添加随机数种子 利用当前时间生成随机数
    srand((unsigned int)time(NULL));
    //1、系统生成 1~100 的随机数
    int num = rand()%100+1;		//rand()生成随机数的函数，生成(0~99)+1范围的随机数
    cout << num << endl;
    //2、玩家猜测
    int temp;
    while(1)
	{
        cout << "请输入你心中的数字(1~100)：";
        cin >> temp;
        cout << temp << endl;
        if(temp == num){
            cout << "恭喜你猜对了！" << endl;
            break;
        }
        else{
            if(temp > num){
                cout << "很遗憾，猜大了。" << endl;
            }
            else{
                cout << "很遗憾，猜小了。" << endl;
            }
        }
    }
    return 0;
}
```



#### do...while循环

区别：与while循环区别在于，do...while循环会先执行一次循环语句，再判断循环条件

语法：`do{循环语句} while(条件判断);`

示例：

```c++
int main()
{
    int num = 0;
    do
    {
        cout << num << endl;
        num++;
    }
    while(0);
    return 0;
}
```



##### 练习案例：水仙花数

**案例描述：**水仙花数是指一个3位数，它的每个位上的数字的3次幂之和，等于它本身

例如：1^3 + 5^3 + 3^3 = 153

利用do...while语句，求出所有3位数中的水仙花数

```C++
int main()
{
    int num = 100;
    do{
        int a,b,c = 0;
        a = num %10;
        b = num /10%10;
        c = num /100%10;
        if(a*a*a+b*b*b+c*c*c == num){
            cout << num << endl;
        }
        num++;
    }while(num <= 999);
    return 0;
}
```



#### for循环

作用：可指定循环次数的循环结构体

语法：`for(起始表达式;条件表达式;末尾表达式){ 执行语句; }`

```c++
for(int i=0;i<5;i++){
    // 0 起始表达式：不参与循环，作用是做一些变量的初值，创建变量声明等。
    // 1 条件表达式：满足条件循环才执行。
    // 2 执行语句
    // 3 末尾表达式：可以用于计数的增加。

    // 执行顺序：0123 123 123...
}
```



##### 练习案例：敲桌子

**案例描述：**从1开始数到100，如果数字十位或各位含有7，或者数字是7的倍数，我们打印**敲桌子**，其余数字直接打印输出。

```c++
int main()
{
    for(int i=1;i<101;i++){
        if(i%10==7 || i/10%10==7 || i/100%10==7){
            cout << "敲桌子" << endl;
        }
        else{
            cout << i << endl;
        }
    }
    return 0;
}
```



#### 嵌套循环

作用：在循环体中再套一层循环，可以解决一些实际问题。

如：利用嵌套循环实现二维星图

```c++
int main()
{	
    // 外层执行1次，内层执行1轮
    for(int i=0;i<11;i++){
        for(int j=0;j<11;j++){
            cout << "* ";
        }
        cout << endl;
    }
    return 0;
}
```



##### 练习案例：乘法口诀表

**案例描述：**利用嵌套循环，实现九九乘法表

```c++
int main()
{
    // 九九乘法表
    for(int i=1;i<10;i++){
        for(int j=1;j<=i;j++){
            cout << j << "*" << i << "=" << (i*j) << " ";
        }
        cout << endl;
    }
    return 0;
}
```



### 跳转语句

#### break语句

作用：用于提前结束、跳出选择结构或循环结构

break 使用时机：

- switch条件语句：作用是终止case并跳出switch
- 循环语句：作用是跳出当前整个循环体。
- 嵌套循环：跳出最近的内层循环语句。

示例：

```c++
int i = 0;
while(1){
    if(i > 10){
        break;		// 跳出死循环
    }
}
```



#### continue语句

作用：在循环语句中，跳出本次循环，continue后面的代码不会执行，直接执行下次循环。

示例：

```c++
for(int i=0;i<100;i++){
    if(i%2 == 0){
        continue;		//利用continue语句，过滤偶数。
    }
    cout << i << endl;	// 如果continue语句执行，那么下面的代码将不会执行。
}
```

> 【区别】与break语句相比，continue不会跳出循环体，只会跳过当前循环。



#### goto语句

作用：用于将程序的执行流程跳转到指定的标签位置。它通常用于跳出多重循环或跳转到错误处理的代码块。

语法：`goto label(大写);`

解释：如果标记的名称存在，那么执行到goto语句时，会跳转到标记的位置。

示例：

```c++
int main()
{
    cout << "1.*****" << endl;
    cout << "2.*****" << endl;
    goto FLAG;			// 创建 goto标签
    cout << "3.*****" << endl;
    cout << "4.*****" << endl;
    FLAG:				// 使用标签，这里使用的是冒号
    cout << "5.*****" << endl;
}
```





## 5、数组

概念：数组是用来存储一系列数据，但它往往被认为是一系列相同类型的变量

**特点1：**数组中每个元素都是相同类型的数据类型

**特点2：**数组中的元素放在一块连续的内存空间中



### 一维数组

#### 一维定义方式

1. `数据类型 数组名[长度];`

2. `数据类型 数组名[长度] = { 元素1,元素2... };`

   > 注：如果{ }不足[长度]个元素，剩余元素自动用0补全

3. `数据类型 数组名[] = { 元素1,元素2... };`

示例：

```c++
int main()
{
    // 定义一个数组，指定元素5个
    int arr[5];
    // 通过索引下标，访问数组中的元素
    arr[0] = 11;		// 索引下标从零开始
    arr[1] = 22;
    arr[2] = 33;
    arr[3] = 44;
    arr[4] = 55;
    // 遍历
    for(int i=0;i< sizeof(arr)/sizeof(arr[0];i++)){
        cout << arr[i] << endl;
    }
}
```

> 总结1：数组名的命名规范与变量名命名规范一致
>
> 总结2：数组中的下标从0开始索引（0 -> 第一个,1 -> 第二个......）



#### 一维数组名称

数组名称的用途：

1. 可以统计整个数组在内存中的长度
2. 可以获取数组在内存中的首地址

示例：

```c++
    // 数组名用途
	int arr[10] = {1,2,3,4,5,6,7,8,9,10};

	// 1、可以获取数组所占内存大小
    cout << "	数组所占内存空间为：" << sizeof(arr) << endl;
    cout << "每个元素所占内存空间为：" << sizeof(arr[0]) << endl;
    cout << "数组的元素个数为：" << (sizeof(arr)/sizeof(arr[0])) << endl;

	// 2、可以通过数组名获取首地址，数组地址和第一个元素是同一个地址
    cout << "数组首地址为：" << arr << " -> " << (uint64_t)arr << endl;
    cout << "数组第一个元素的地址为：" << &arr[0] << " -> " << (int64_t)&arr[0] << endl;
    cout << "数组第二个元素的地址为：" << &arr[1] << " -> " << (int64_t)&arr[1] << endl;


```

> 【注意1】 arr = 100;  错误，数组是常量，因此不可以直接赋值
>
> 【注意2】&：逻辑与，又叫取址符，加在变量前可以获取地址



##### 练习案例1：五只小猪称体重

**案例描述：**在一个数组中记录了五只小猪的体重，如：int arr[5] = {300,350,200,400,250};找出并打印最重的小猪体重。

```c++
int main()
{
    int arr[5] = {300,350,200,400,250};
    
    int max = 0;
    for(int i=0;i<5;i++){
        max = arr[i]>max ? arr[i]:max;		//依次索引比较，大的存入max变量中
    }
    cout << "最重的小猪体重为：" << max << endl;
}
```



##### 练习案例2：数组排序 -- 逆置

**案例描述：**请声明一个元素个数为5的数组，并且将元素逆置

(如原数组排序为：1,3,2,5,4  逆置后输出结果：4,5,2,3,1 )

```c++
int main()
{
    int arr[] = {1,2,3,4,5};
    int num = sizeof(arr) / sizeof(arr[0])-1;
    
    for(int i=0;i<num+1;i++){
        if(i >= num){
            break;  }
        // 首尾交换
        int temp = arr[i];
        arr[i] = arr[num-i];
        arr[num-i] = temp;
    }
    for(int i=0;i<num+1;i++){
        cout << arr[i] << endl;
    }
}
```



#### 冒泡排序

作用：最常用的排序算法，对数组内元素按某种规定进行排序

1. 比较相邻的元素，如果第一个比第二个大，就交换他们俩。
2. 对每一对相邻元素做同样工作，执行完毕后，找到第一个最大值。
3. 重复以上步骤，每次比较次数-1，直到不需要。

示例：

```c++
int main()
{
    int arr[9] = {4,2,8,0,5,7,1,3,9};
    int length = sizeof(arr) / sizeof(arr[0])-1;
    
    for(int i=0;i<length;i++){
		for(int j=0;j<length-i;j++){
        	if(arr[j]>arr[j+1]){
            	int temp = arr[j];
            	arr[j] = arr[j+1];
            	arr[j+1] = temp;
			}
        }
    }
    for(int k=0;k<length+1;k++){
        cout << arr[k] << endl;
    }
}
```



### 二维数组

#### 二维定义方式

1. `数据类型 数组名[行数][列数];`
2. `数据类型 数组名[行数][列数] = { {元素1...},{元素n...} };`
3. `数据类型 数组名[行数][列数] = { 元素1...,元素n };`
4. `数据类型 数组名[][列数] = { 元素1...,元素n };`

示例：

```c++
int main()
{
    //方式1
    int arr1[2][3];
    //方式2
    int arr2[2][3] = { {1,2,3},{10,11,12} };
    //方式3
    int arr3[2][3] = { 1,2,3,10,11,12 };
    //方式4
    int arr4[][3] = { 1,2,3,10,11,12 };
}
```

> 建议：以上4种定义方式，第二种更加直观，提高代码的可读性
>
> 总结：在定义二维数组时，如果初始化了数据，可以省略行数(列数不能省略)



#### 二维数组名称

作用：

- 查看二维数组所占内存空间
- 获取二维数组首地址

示例：

```c++
int main()
{
    int arr[2][3] = {
        {10,20,30},
        {40,50,60},
    };
    // 1、可以获取数组所占内存大小
    cout << "二维数组所占内存空间为：" << sizeof(arr) << endl;
    cout << "一行元素所占内存空间为：" << sizeof(arr[0]) << endl;
    cout << "一个元素所占内存空间为：" << sizeof(arr[0][0]) << endl;
    cout << "二维数组行数为：" << (sizeof(arr)/sizeof(arr[0])) << endl;
    cout << "二维数组列数为：" << (sizeof(arr[0])/sizeof(arr[0][0])) << endl;
    cout << "数组的元素个数为：" << (sizeof(arr)/sizeof(arr[0][0])) << endl;

	// 2、可以通过数组名获取首地址，数组地址和第一个元素是同一个地址
    cout << "二维数组首地址为：" << arr << " -> " << (uint64_t)arr << endl;
    cout << "二维数组第一行首地址为：" << &arr[0] << " -> " << (int64_t)&arr[0] << endl;
    cout << "二维数组第一个元素地址：" << &arr[0][0] << " -> " << (int64_t)&arr[0][0] << endl;
	return 0;
}
```



#### 练习案例：成绩考试统计

**案件描述：**有三名同学(张三，李四，王五)，在一次考试中的成绩分别如下表，**请分别输出三名同学的总成绩**

| 姓名 | 语文 | 数学 | 英语 |
| ---- | ---- | ---- | ---- |
| 张三 | 100  | 70   | 90   |
| 李四 | 85   | 100  | 80   |
| 王五 | 90   | 95   | 100  |

答案：

```c++
int main()
{
    // 1、创建三名同学的成绩
    double score[3][3] = {
        {100,70,90},
        {85,100,80},
        {90,95,100}
    };
    string name[] = {"张三","李四","王五"};
    
    // 2、计算每位同学的总成绩
    for(int i=0;i<3;i++){
        int sum = 0;
        for(int j=0;j<3;j++){
            sum += score[i][j];
        }
        // 3、输出打印三位同学的总成绩
        cout << name[i] << "总成绩：" << sum << endl;
    }
}
```



## 6、函数

作用：将可以重复使用的代码封装起来，减少代码重复性
一个较大的程序，一般分为若干个程序块，每块负责一个特定的功能，更易于管理。

### 函数基础

#### 函数的定义

函数的定义一般分为5个步骤：

1. 返回值类型：也就向外返回 return 表达式结果的类型
2. 函数名：给函数起个名称，用于调用
3. 参数列表：使用该参数时，传入的参数
4. 函数体语句：花括号内执行的代码块
5. return 表达式：和返回值挂钩，返回表达式的数据结果

**语法：**

```c++
//	返回值类型 函数名(参数列表)
//	{
//		函数体语句;
//		return 表达式;
//	}
```

示例：

```c++
// 加法函数，实现两个浮点数相加，并且将结果返回
double add(double a,double b)
{
    int sum = a + b;
    return sum;
}
```

> 注：如果函数不需要返回值，声明的时候返回值类型可以写**void**，这时的**return**可以省略不写。



#### 函数的调用

作用：使用定义好的函数

语法：`函数名(参数1,参数2...);`

示例：

```c++
// 函数定义
// 加法函数，实现两个浮点数相加，并且将结果返回
double add(double a,double b)	// 函数定义时的参数没有真实数据，是一个形式上的参数（形参）
{
    int sum = a + b;
    return sum;
}
// 函数调用
int main()
{
    double a = 9.5;
    double b = 12.3;
    // 调用 add函数
    double sum = add(a,b);	// 调用时的a、b称为实际参数（实参）
    cout << "sum = " << sum << endl;
    return 0;
}
```

> 总结1：函数定义里小括号内称为形参列表，函数调用时传入的参数称为实参。
>
> 总结2：当调用函数时，实参的值会传递给形参，通过形参传递到函数中使用。



#### 值传递

- 所谓值传递，就是函数调用时，填入的实参将值传递给形参
- 值传递时，如果形参发生改变，不会影响到实参

```c++
// 值传递
// 定义函数，实现两个数字的数值交换功能
void swap(int a,int b)
{
    cout << "交换前：" << endl;
    cout << "a = " << a << "  " << "b = " << b << endl;
    
    int temp = a;
    a = b;
    b = temp;
    cout << "交换后：" << endl;
    cout << "a = " << a << "  " << "b = " << b << endl;
}
int main()
{
    int a = 15;
    int b = 20;
    // 当我们做值传递的时候，函数的形参发生改变时，不会影响到实参
    swap(a,b);
    cout << "变量a = " << a << endl;
    cout << "变量b = " << b << endl;
    return 0;
}
```

> 总结：值传递时，形式是修饰不了实参的



#### 函数常见样式

常见的函数样式有4种

1. 无参无返
2. 有参无返
3. 无参有返
4. 有参有返

示例：

```c++
// 函数常见样式
// 1、无参无返
void test01()
{
    cout << "this is test01" << endl;
    //test01();		调用时
}
// 2、有参无返
void test02(int height)
{
    cout << "小明的身高是" << height << "cm" << endl;
    //test02(182);		调用时
}
// 3、无参有返
int test03()
{
    cout << "this is test03"
    return 110;
    //int a = test03();
}
// 4、有参有返
int test04(int a)
{
    cout << "this is test04 a = " << a<< endl;
    return a*a*a;
    //int cube = test04(15);
}
```



#### 函数的声明

作用：提前告诉编译器函数的名称及返回类型和参数列表，函数的实际主体可以单独定义。

> 【注意】函数的声明可以很多次，但是函数的**定义只能有一次**



示例：

```c++
// 函数的声明
// 提前告诉编译器函数的存在，可以利用函数声明
int max();				// 声明时可以不写形参列表
int max(int a,int b);	// 声明可以有多次，但是定义只能有一次

int main()
{
    max(20,25);
    return 0;
}

// 函数定义
int max(int a,int b)
{
    return a > b ? a:b;
}
```



#### 函数的分文件编写

作用：让代码结构更加清晰

函数份文件编写一般有4个步骤

1. 创建后缀名为**.h的头文件**
2. 创建后缀名为**.cpp的源文件**
3. 在头文件中写函数的**声明**
4. 在源文件中写函数的**定义**

示例：

```c++
// swap.h文件
// 声明写在.h文件中
#include <iostream>
using namespace std;

void swap(int a,int b);
```

```c++
// swap.cpp
// 定义写在.cpp文件中
#include "swap.h"		// .cpp文件需要包含.h头文件
						// 使用系统头文件用<>包含，自定义头文件使用""包含
int main()
{
    swap(12,24);
    return 0;
}

void swap(int a,int b)
{
    cout << "交换前：a=" << a << "  b=" << b << endl;
    int temp = a;
    a = b;
    b = temp;
    cout << "交换后：a=" << a << "  b=" << b << endl;
}
```



### 函数提高

#### 函数默认参数

在c++中，函数的形参列表中的形参是可以由默认值的。

语法：`返回值类型 函数名(参数=默认值) {}`

```c++
int func(int a=10,int b=15)
```

示例：

```c++
// 函数默认参数
// 注意1：默认参数变量必须在无参变量的后面
int func1(int b,int a=10,int c=20)  {
    return a + b + c;
}
// 注意2：如果函数声明有默认值，在函数实现时就不能有默认参数
int func2(int a,int b=6,int c=7);
int func2(int a=5,int b,int c){
    return a + b + c;
}
int main(){
    int sum = func2();
    cout << sum << endl;
    return 0;
}
```



#### 函数占位参数

C++中函数的形参列表里可以有占位参数，用来做占位，调用函数时必须填补该位置

语法：`返回值类型 函数名(数据类型) {}`

示例：

```c++
// 占位参数，还可以有占位默认参数
void func(int a,int,int =20){
    cout << "this is func" << endl;
}
int main(){
    func(10,15);	// 占位参数必须填补
}
```



#### 函数重载(多态)

作用：函数名可以相同，提高复用性

**函数重载满足条件：**

- 同一个作用域下
- 函数名称相同
- 函数参数的**类型不同** 或者 **个数不同** 或者 **类型顺序不同**

注意：函数返回值不可以作为函数重载条件

示例：

```c++
void func(){
    cout << "func1 无参" << endl;
}
void func(int a,double b){
    cout << "func2 int double" << endl;
}
void func(double a,int b){
    cout << "func3 double int" << endl;
}
int main()
{
    func();			//func1
    func(10,2.5);	//func2
    func(2.5,10);	//func3
    return 0;
}
```



#### 函数重载注意事项

- 引用作为重载条件
- 函数重载碰到函数默认参数

示例：

```c++
// 函数重载注意事项
//1、常量引用作为函数重载条件
void func(int &a){
    cout << "func" << endl;
}
void func(const int &a){
    cout << "func const" << endl;
}
//2、函数重载遇到默认参数
void func2(int a){
    cout << "func2" << endl;
}
void func2(int a,int b=10){
    cout << "func2 默认参数" << endl;
}
int main(){
    int a = 10;
    const int b = 10;
    func(a);	//func
    func(b);	//func const
    func(10);   //func const
    // func2(a);  //碰到默认参数产生歧义，需要避免
}
```























## 7、指针

**指针**是一个变量，其值为另一个变量的地址，即，内存位置的直接地址。就像其他变量或常量一样，您必须在使用指针存储其他变量地址之前，对其进行声明。

**指针的作用：**可以通过指针间接访问内存

- 内存编号是从0开始记录的，一般用十六进制数字表示
- 可以利用指针变量保存地址



### 指针变量的定义和使用

指针变量定义语法：`数据类型 * 变量名;`

示例：

```c++
    // 1、指针定义
    int a = 10;			//定义整型变量a
    int * p;			//创建指针变量p，此时指针p是空指针
    // 通过取址符& 获取变量a的地址，记录到指针变量内存中
    p = &a;				
    cout << "变量a的地址：" << &a << endl;
    cout << "指针p指向的地址" << p << endl;

	// 2、使用指针
    // 解引用的方式来找到指针指向的内存中的数据
    // 指针前加* 代表解引用
	*p = 500;
	cout << "a = ：" << a << endl;
    cout << "*p = " << p << endl;
```

`& ：取址符`  `* ：解引用`

> 【区别】
>
> 普通变量(int)：内存下保存的是数据
>
> 指针变量(int*)：内存下保存的是地址



### 指针所占内存空间

指针也是一种数据类型，这种数据类型占用4个内存空间

示例：

```c++
int main()
{
    int a = 10;
    int* p = &a;		//指针指向数据a的地址
    
    cout << "int* = " << sizeof(int*) << endl;
    cout << "double* = " << sizeof(double*) << endl;
    cout << "float* = " << sizeof(float*) << endl;
    cout << "char* = " << sizeof(char*) << endl;
    cout << "string* = " << sizeof(string*) << endl;
	return 0;
}
```

> 【总结】所有类型的指针变量所占内存相同。
>
> 在32位操作系统下：占4个字节空间。64位操作系统下：占8个字节空间。



### 空指针和野指针

**空指针：**指针变量指向内存中变量为0或NULL的空间

> 用途：初始化指针变量
>
> 注意：空指针指向的内存空间是不可以访问的

**野指针：**指针变量指向非法（或系统未授权）的内存的空间

> 注意：野指针指向的内存空间没有权限访问

**示例1：**空指针

```c++
	// 空指针
	// 指针变量指向内存地址编号为0的空间
	int* p = NULL;
	
	// 访问空指针变量报错
	// 内存编号0~255为系统占用内存，不允许用户访问
	cout << *p << endl;
```

**示例2：**野指针

```c++
    // 野指针
    // 指针变量p1指向内存地址编号为0x1100的空间
    int* p1 = (int*)0x1100;

    // 访问野指针变量报错，不允许访问未申请的地址
    cout << *p1 << endl;
```

> 总结：空指针和野指针都不是我们申请的空间，因此不能访问。
>



### const 修饰指针

const 是 constant 的缩写，本意是不变的意思

const 修饰指针有三种情况：

1. const修饰指针 -- 常量指针
2. const修饰常量 -- 指针常量
3. const及修饰指针，又修饰常量



**区分**常量指针和指针常量：

怎么快速的记住他们的区别，只需要按照命名的顺序来读，就可以很好地记忆：

- ```c++
  int* const p = &a;		// 指针常量
  ```

- 首先是一个指针`int*`，然后一个`const`常量，那么p就是`指针常量`

- ```c++
  const int* p = &a;		// 常量指针
  ```

- 首先是一个`const`常量，然后一个指针`int*`，那么p就是`常量指针`



**指针常量**

**特点：**不可以修改**指针的指向**，指向内存地址的值可以修改，在定义时必须初始化

```c++
int a = 20;  int b = 20;
int* const p = &a;	// 定义指针常量p，指向 a的地址

*p = 10;	// 正确，指向的内存地址中的数据可以修改
p = &b;		// 错误，指向的地址不能修改
```

**常量指针**

**特点：**不能修改指针指向内存**地址的数据**，指向的内存地址可以修改

```c++
int a = 20;  int b = 20;
const int* p = &a;	// 定义常量指针p，指向 a的地址

p = &b;			// 正确，指向的地址可以修改
*p = 20;		// 错误，指向的内存地址中的数据不能修改
```

扩展：

```c++
int a, b, * p1 = &a, * p2;
/*
&*p1 的含义：
&和*都是自右向左运算符，因此先看p1是指针，*p1即为p1指向的对象，
因此*p1等价于a,因此a 的前面加一个&,表示的就是 a 的地址
因此：&*p1 ,p1 ,&a 三者等价
*&a 的含义：a的地址前加*表示的就是a本身，指针就是用来放地址的，地址前面加*表示的就是这个对象
因此： *&a ,a ,*p 三者等价 */
```



### 指针和数组

作用：利用指针访问数组中元素

示例1：

```c++
// 指针和数组1
int main()
{
    int arr[] = {1,2,3,4,5,6,7,8,9,10};
    int * p = arr;	//指向数组首地址
    
    cout << "通过指针访问数组第一个元素：" << *p << endl;
    p++;	//指针所存地址+1*指针引用的数据类型大小，也得到了第二个元素的地址
    cout << "通过指针访问数组第二个元素：" << *p << endl;
    p--;
    cout << "通过指针访问数组第一个元素：" << *p << endl;
    
    // 通过for循环遍历数组
    for(int i=0;i<10;i++){
        cout << *p << endl;
        p++;
    }
    return 0;
}
```

示例2：

```c++
// 指针和数组2
int main()
{
    int arr[] = {1,2,3,4,5,6,7,8,9,10};
    int * p = arr;	//指向数组首地址
    
    // 通过for循环遍历数组
    for(int i=0;i<10;i++){
        cout << p[i] << endl;
    }
    return 0;
}
```

> 【总结】如果一个指针变量指向一个数组，那么该指针变量就可以使用索引下标来读取和修改数组中的元素。因为指针变量和数组名本质上都是指向数组中元素的地址。



### 指针和函数

作用：利用指针来做函数的参数，可以**修改实参的值**

示例：

```c++
// 指针和函数
int swap01(int a,int b)
{
	int temp = a;
	a = b;
	b = temp;
	cout << "swap01 a= " << a << endl;
    cout << "swap01 b= " << b << endl;
}
int swap02(int *p1,int *p2)
{
    int temp = *p1;
	*p1 = *p2;
	*p2 = temp;
	cout << "swap02 a= " << *p1 << endl;
    cout << "swap02 b= " << *p2 << endl;
}
int main()
{
    // 1、值传递	不会改变实参的值
    int a = 15;
    int b = 25;
    swap01(a,b);
    cout << "a= " << a << endl;
    cout << "b= " << b << endl;
    
    // 2、地址传递	可以改变实参的值
    swap02(&a,&b);		// 地址传递，可以修饰实参
    cout << "a= " << a << endl;
    cout << "b= " << b << endl;
    return 0;
}
```



### 指针、数组、函数

**案例描述：**封装一个函数，利用冒泡排序，实现对整型数组的升序排序

例如数组：int arr[10] = { 4,3,6,9,1,2,10,8,7,5 };

示例：

```c++
// 冒泡排序功能
void bubblingSort(int * arr,int len)		// 2、创建实现冒泡排序的函数
{
    for(int i=0;i<len-1;i++){
        for(int j=0;j<len-1-i;j++){
            if(arr[j] > arr[j+1]){
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
}
int main()
{
    int arr[10] = { 4,3,6,9,1,2,10,8,7,5 };		// 1、创建数组
    int len = sizeof(arr) / sizeof(arr[0]);
    bubblingSort(arr,len);
	// 3、打印排序好的数组
    for(int i=0;i<len;i++){
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
```



## 8、结构体

结构体属于用户自定义的数据类型，允许用户存储不同的数据类型



### 结构体的定义和使用

语法：`struct 结构体名 {结构体成员列表 };`

通过结构体创建实例化对象的方式有三种：

- struct 结构体名 变量名;
- struct 结构体名 变量名 = { 成员1，成员2... };
- 定义结构体时顺便创建变量;

示例：

```c++
// 结构体定义
struct Student		//定义一个学生的结构体
{
    // 成员列表
    string name;	// 姓名
    int age;		// 年龄
    double scort;	// 分数
}s3;				// 顺便创建结构体变量 >.<
int main()
{
    // 方法一：struct 结构体名 变量名;
    // 结构体创建实例化对象时，struct关键字可以省略
    struct Student s1;
    s1.name = "肖明";
    s1.age = 18;
    s1.scort = 100;
    cout << s1.name << " " << s1.age << " " << s1.scort << endl;

    // 方法二： struct 结构体名 变量名 = { 成员1，成员2... };
    struct Student s2 = { "丽丝",19,99.5 };
    cout << s2.name << " " << s2.age << " " << s2.scort << endl;

    // 方法三： 定义结构体时顺便创建变量：请看上面标记处 >.< 
    s3.name = "汪伍";
    s3.age = 20;
    s3.scort = 99;
    cout << s3.name << " " << s3.age << " " << s3.scort << endl;
    return 0;
}
```

> 总结1：创建结构体实例化对象时，关键字struct可以省略
>
> 总结2：结构体实例化对象利用操作符"."访问结构体成员



### 结构体数组

作用：将自定义的结构体放入到数组中方便维护

语法：`struct 结构体名 数组名{元素个数} = { {},{}, ...{} }`

示例：

```c++
// 结构体数组
struct Xuesheng     //1、创建结构体
{
    // 成员列表
    string name;	//姓名
    int age;		//年龄
    double score;	//分数
};
int main()
{
    // 2、创建结构体对象数组
    struct Xuesheng xueArr[3] = {
        {"张三",18,100},
        {"李四",19,99},
        {"王五",20,98}
    };
    // 3、修改结构体对象数组中的元素
    xueArr[2].age = 88;
    xueArr[2].score = 60;
    xueArr[2].name = "赵六";
    // 4、遍历修改后结构体中对象的信息
    for(int i=0;i<3;i++){
        cout << " 姓名：" << xueArr[i].name 
             << " 年龄：" << xueArr[i].age 
             << " 分数：" << xueArr[i].score << endl;
    }    
    return 0;
}
```





### 结构体指针

作用：通过指针访问结构体中的成员

- 利用操作符`->`，可以通过结构体指针访问结构体属性



示例：

```c++
// 结构体指针
struct Student
{
    // 成员列表
    string name;	//姓名
    int age;		//年龄
    double score;	//分数
};
int main()
{
    // 1、创建学生结构体变量
    struct Student s = {"钱七",88,90};
    
    // 2、通过指针指向结构体变量
    struct Student *p = &s;
    
    // 3、通过指针访问结构体变量中的数据，需要使用"->"
    cout << " 姓名：" << p->name		//指针通过 -> 访问结构体成员
         << " 年龄：" << p->age 
         << " 分数：" << p->score << endl;
    return 0;
}
```

> 总结：结构体指针可以通过 -> 操作符，来访问结构体中的成员
>



### 结构体嵌套结构体

作用：结构体中的成员可以是另一个结构体

例如：每个老师辅导一个学员，那么老师的结构体中，就包含了一个学生的结构体

示例：

```c++
//结构体嵌套结构体
struct Student  //学生结构体
{	//成员列表
    string name;
    int age;
    int score;
};
struct Teacher  //老师结构体
{	//成员列表
    string name;
    int age;
    int id;
    struct Student stu;
};
int main()
{
    struct Teacher t = { "罗翔",28,1314,{"张三",18,95} };
    cout << "老师名字：" << t.name << " 老师编号：" << t.id << " 老师年龄：" << t.age 
         << "\n老师辅导的学生姓名：" << t.stu.name << " 学生年龄：" << t.stu.age 
         << " 学生分数：" << t.stu.score << endl;
    return 0;
}
```

> 总结：在结构体中可以定义另一个结构体作为成员。
>
> 注意：内部结构体要定义在外部结构体的上面。



### 结构体做函数参数

作用：将结构体作为参数向函数中传递

传递方式有两种：

- 值传递
- 地址传递

示例：

```c++
// 结构体做函数参数
struct Student
{
    string name;
    int age;
    int score;
};
void printS1(struct Student s)
{
    s.name = "李四";
    s.age = 17;
    s.score = 99;
    
    cout << "姓名：" << s.name<< " 年龄：" << s.age << " 分数：" << s.score << endl;
}
void printS2(struct Student * p)
{
    p->name = "张五";
    p->age = 18;
    p->score = 100;
    
    cout << "姓名：" << p->name<< " 年龄：" << p->age << " 分数：" << p->score << endl;
}
int main()
{
    struct Student s;
    // printS1(s);
    printS2(&s);
    cout << "姓名：" << s.name<< " 年龄：" << s.age << " 分数：" << s.score << endl;
    return 0;
}
```

> 总结：如果不想修改主函数中的数据，用值传递，反之用地址传递
>



### 结构体 const 使用场景

作用：用 const 来防止误操作

示例：

```c++
struct Student
{
    string name;
    int age;
    int score;
};
// const使用场景
// 将函数中形参改为地址传递，可以减少内存空间占用，不会复制出新的副本
void printS(const Student * p)
{
    //p->age = 50;  //操作失败，因为加了const 常量指针(不能修改指针指向内存地址的数据)
    cout << "姓名：" << p->name<< " 年龄：" << p->age << " 分数：" << p->score << endl;
}
    int main()
{
    Student s = { "小张",18,88 };
    printS(&s);
}
```



### 结构体案例

#### 案例1 老师和学生

**案例描述：**
学校正在做毕设项目，每名老师带领5个学生，总共有3名老师，需求如下：
设计学生和老师的结构体，其中在老师的结构体中，有老师姓名和一个存放5名学生的数组作为成员。学生的成员有姓名、考试分数，创建数组存放3名老师，通过函数给每个老师及所带的学生赋值最终打印出老师数据以及老师所带的学生数据。



示例：

```c++
// 结构体案例 1
#include <ctime>
struct Student      //学生结构体
{
    string name;
    int score;
};
struct Teracher     //老师结构体
{
    string name;
    struct Student s1[5];
};
void allocateSpace(struct Teracher t[],int len)     //给老师和学生赋值
{
    string nameSeed = "ABCDE";
    // 给老师赋值
    for(int i=0;i<len;i++){
        t[i].name = "Teacher_";
        t[i].name += nameSeed[i];
        // 给学生赋值
        for(int j=0;j<5;j++){
            t[i].s1[j].name = "Student_";
            t[i].s1[j].name += nameSeed[j];
            // 系统生成 40~100 的随机数赋给成绩
            int random = rand()% 61 + 40;
            t[i].s1[j].score = random;
        }
    }
}
void printTS(struct Teracher *p,int len)    //打印函数
{
    for(int i=0;i<len;i++){
        cout << "指导老师：" << p[i].name << endl;
        for(int j=0;j<5;j++){
            cout << "学生：" << p[i].s1[j].name << " 分数：" << p[i].s1[j].score << endl;
        }
    }
}
int main()
{
    srand((unsigned int)time(NULL));    //添加随机数种子 利用当前时间生成随机数
    
    Teracher t[3];      //创建老师的数组
    int len = sizeof(t)/sizeof(t[0]);       //统计老师的数组长度
    allocateSpace(t,len);
    printTS(t,len);

    return 0;
}
```



#### 案例2 英雄

**案例描述：**

设计一个英雄的结构体，包括成员姓名、年龄、性别；创建结构体数组，数组中存放5名英雄。
通过冒泡排序的算法，将数组中的英雄按照年龄进行升序排序，并打印最终排序的结果。

五名英雄信息如下：

```c++
	{"赵云",20,"男"},
	{"刘备",23,"男"},
	{"张飞",21,"男"},
	{"貂蝉",19,"女"},
	{"关羽",22,"男"}
```



示例：

```c++
struct Hero
{
    string name;    // 姓名
    int age;        // 年龄
    string sex;     // 性别
};
void sort(struct Hero h[],int len)
{
    for(int i=0;i<len-1;i++){
        for(int j=0;j<len-1-i;j++){
            if(h[j].age > h[j+1].age){
                struct Hero temp = h[j];
                h[j] = h[j+1];
                h[j+1] = temp;
            }
        }
    }
}
int main()
{
    struct Hero h[5] = {
        {"赵云",20,"男"},
        {"刘备",23,"男"},
        {"张飞",21,"男"},
        {"貂蝉",19,"女"},
        {"关羽",22,"男"}
    };
    int len = sizeof(h)/sizeof(h[0]);
    // 冒泡排序函数
    sort(h,len);
    // 打印排序后结果
    for(int i=0;i<len;i++){
        cout << h[i].name << " " << h[i].age << " " << h[i].sex << endl;
    }
    return 0;
}
```



## 9、案例：通讯管理系统

**系统需求：**

通讯录是一个可以记录亲人、好友信息的工具。

本教程主要利用C+＋来实现一个通讯录管理系统

系统中需要实现的功能如下：

- 添加联系人：向通讯录中添加新人，信息包括（姓名、性别、年龄、联系电话、家庭住址）

- 显示联系人：显示通讯录中所有联系人信息

- 删除联系人：按照姓名进行删除指定联系人．查找联系人：按照姓名查看指定联系人信息

- 修改联系人：按照姓名重新修改指定联系人

- 清空联系人：清空通讯录中所有信息

- 退出通讯录：退出当前使用的通讯录



示例：

```c++
#define MAX 1000    //最大人数

// 联系人结构体：姓名、性别、年龄、联系电话、家庭住址
struct Person
{
    string Name;    // 姓名
    int Sex;        // 性别 1男 2女
    int Age;        // 年龄
    string Phone;   // 电话
    string Addr;    // 地址
};
// 通讯录结构体
struct Addressbooks
{
    struct Person personArray[MAX];     //通讯录保存的联系人数组
    int Size;   //记录通讯录中人员个数
};

// 1、添加联系人
void addPerson(Addressbooks * abs)
{
    if(abs->Size >= MAX){
        cout << "通讯录已满，无法添加！" << endl;
        return;
    }
    else{
        // 姓名
        int zzjj = 0;
        string name;
        cout << "请输入联系人姓名：";
        cin >> name;
        for(int i=0;i<abs->Size;i++){
            if(name == abs->personArray[i].Name){
                cout << "此联系人已存在" << endl;
                zzjj = 1;   break;
            }
        }
        if(zzjj == 0){
            abs->personArray[abs->Size].Name = name;
            // 性别
            int sex;
            cout << "请输入联系人性别(1-男 2-女 )：";
            cin >> sex;
            abs->personArray[abs->Size].Sex = sex;
            // 年龄
            int age;
            cout << "请输入联系人年龄：";
            cin >> age;
            abs->personArray[abs->Size].Age = age;
            // 电话
            string phone;
            cout << "请输入联系人电话：";
            cin >> phone;
            abs->personArray[abs->Size].Phone = phone;
            // 地址
            string addr;
            cout << "请输入联系人地址：";
            cin >> addr;
            abs->personArray[abs->Size].Addr = addr;
            abs->Size++;
            cout << "添加成功！" << endl;
        }
    }
    system("pause");    // 按任意键继续
    system("cls");      // 清屏操作
}
// 2、显示联系人
void showPerson(Addressbooks abs)
{
    if(abs.Size == 0){
        cout << "您的通讯录为空，赶快去交朋友吧！" << endl;
    }
    else{
        cout << "总人数：" << abs.Size << endl;
        for(int i=0;i<abs.Size;i++){
            cout << "姓名：" << abs.personArray[i].Name << "  性别：" << abs.personArray[i].Sex 
            << "  年龄：" << abs.personArray[i].Age << "  电话：" << abs.personArray[i].Phone 
            << "  地址：" << abs.personArray[i].Addr << endl;
        }
    }
    system("pause");    // 按任意键继续
    system("cls");      // 清屏操作
}
// 3.删除联系人
void delPerson(Addressbooks * abs)
{
    string delName;
    cout << "请输入要删除联系人姓名：";
    cin >> delName;
    for(int i=0;i<abs->Size;i++){
        if(delName == abs->personArray[i].Name){
            // 删除操作 后面数据前移一位，覆盖
            for(int j=i;j<abs->Size;j++){
                abs->personArray[j] = abs->personArray[j+1];
            }
            // personArray[]
            abs->Size--;
            cout << "删除成功~" << endl;    break;
        }
        else{
            if(i == abs->Size-1){
                cout << "搞错啦！查无此人" << endl;
            }
        }
    }
    system("pause");    // 按任意键继续
    system("cls");      // 清屏操作
}
// 4、查找联系人
void findPerson(Addressbooks abs)
{  
    string seekName;
    cout << "请输入查找姓名：";
    cin >> seekName;
    for(int i=0;i<abs.Size;i++){
        if(seekName == abs.personArray[i].Name){
            cout << "姓名：" << abs.personArray[i].Name << "  性别：" << abs.personArray[i].Sex 
            << "  年龄：" << abs.personArray[i].Age << "  电话：" << abs.personArray[i].Phone 
            << "  地址：" << abs.personArray[i].Addr << endl;
            break;
        }
        else {
            if(i == abs.Size-1){
                cout << "搞错啦！查无此人" << endl;
            }
        }
    }
    system("pause");    // 按任意键继续
    system("cls");      // 清屏操作
}
// 5、清空联系人
void cleanPerson(Addressbooks * abs)
{
    int choice;
    cout << "确认清空联系人吗？！\n\rYes--1  No--0" << endl;
    cin >> choice;
    if(choice == 1){
        abs->Size = 0;
        cout << "联系人已清空！" << endl;
    }
    else {
        cout << "已取消" << endl;
    }
    system("pause");    // 按任意键继续
    system("cls");      // 清屏操作
}
// 6、修改联系人

//菜单界面
void showMenu()
{
    cout << "********************\n"
        << "*** 1.添加联系人 ***\n"
        << "*** 2.显示联系人 ***\n"
        << "*** 3.删除联系人 ***\n"
        << "*** 4.查找联系人 ***\n"
        << "*** 5.清空联系人 ***\n"
        << "*** 6.修改联系人 ***\n"
        << "*** 0.退出通讯录 ***\n"
        << "********************\n"
        << "请操作：";
}
int main()
{
    Addressbooks abs;   // 创建通讯录结构体对象
    abs.Size = 0;   // 初始化通讯录人员个数

    int step = 1;   //选择操作
    while(step != 0)
    {
        // 菜单调用
        showMenu();
        cin >> step;

        switch(step)
        {
        case 1: //1.添加联系人
            addPerson(&abs);
            break;
        case 2: //2.显示联系人
            showPerson(abs);
            break;
        case 3: //3.删除联系人
            delPerson(&abs);
            break;
        case 4: //4.查找联系人
            findPerson(abs);
            break;
        case 5: //5.清空联系人
            cleanPerson(&abs);
            break;
        case 6: //6.修改联系人

            break;
        case 0: //0.退出通讯录
            cout << "欢迎下次使用!" << endl;
            break;
        default:
            break;
        }
    }
    return 0;
}
```



# 三、C++ 核心编程

主要针对C++面对对象编程技术做详细讲解，学习探讨C++中的核心精髓。



## 1、内存分区模型

C++程序在执行时，将内存大方向划分为**4个区域**

- 代码区：存放函数体的二进制代码，有操作系统进行管理
- 全局区：存放全局变量和静态变量以及常量
- 栈区：由编译器自动分配释放，存放函数的参数值，局部变量等
- 堆区：由程序员分配和释放，若程序员不释放，程序结束时由操作系统回收



**内存四区的意义：**

赋予不同功能数据不同的生命周期便于灵活编程



### 程序运行前

在程序编译后，生成了exe可执行程序，**未执行该程序前**分为两个区域

**代码区：**

​		存放CPU执行的机器指令

​		代码区是**共享**的，共享的目的是对于频繁被执行的程序，只需要在内存中有一份代码

​		代码区是**只读**的，使其只读的原因是防止程序意外修改了它的指令

**全局区：**

​		全局变量和静态变量存放此处

​		全局区还包含常量区，字符串常量和其他常量

​		***该区域的数据在程序结束后由操作系统释放***



### 程序运行后

**栈区：**

​		由编译器自动分配释放，存放函数的参数值、局部变量等

​		**注意事项：不要返回局部变量的地址**，因为局部变量存放在栈区，栈区开辟的数据执行                     	                       完会被编译器自动释放

示例：

```c++
int * func()
{
    int a = 11;
    return &a;
}
int main()
{
    int * p = func();	//调用完函数，内部的局部变量自动销毁
    cout << *p << endl;	//野指针，所以会引发异常
    return 0;
}
```



**堆区：**

​		由程序员分配释放，若程序员不释放，程序结束时由操作系统自动释放

​		在C++中主要利用**new**在堆区开辟内存

示例：

```c++
int * func()
{
    // 利用new关键字  可以将数据开辟到堆区
    // 指针 本质是局部变量，指针指向的数据是 保存在堆区上
    int * p = new int(10);
    return p;
}
int main()
{
    int *pp = func();
    cout << *pp << endl;
    return 0;
}
```

> 总结：堆区数据由程序员管理分配和释放，堆区数据利用**new**关键字来开辟内存



### new 操作符

C++中利用**new**操作符在堆区开辟的数据，由程序员手动开辟，手动释放，利用操作符**delete**关键字释放

**new**创建的数据，会返回该数据对应类型的指针

语法：`new 数据类型(初始值);`



示例1：基本语法

```c++
// new的基本语法
int * func()
{
    // 在堆区创建整型数据
    // new返回的是该数据类型的指针，需要用对应类型的指针去接收
    int *p = new int(15);
    return p;
}
void test1()
{
    int *p = func();
    cout << *p << endl;
    cout << *p << endl;
    delete p;
    cout << *p << endl;     //内存已经被释放，再次访问就是非法操作
}
```

示例2：开辟数组

```c++
// 堆区开辟数组
void test2()
{
    int *arr = new int[10]; //[10]代表10个元素

    for(int i=0;i<10;i++){
        arr[i] = i + 100;
        cout << &arr[i] << endl;
    }
    // 释放堆区数组 delete 后面加[]
    delete[] arr;
}
```



## 2、引用

### 引用的基本使用

作用：给变量起别名

语法：`数据类型 &别名 = 原变量名`

> int &b = a;

示例：

```c++
// 引用基本语法
int main()
{
    int a = 10;
    int &b = a;		// 引用一旦初始化，就不能改变
    
    cout << a << endl;
    cout << b << endl;
    b = 22;
    cout << a << endl;
    cout << b << endl;
    return 0;
}
```

注意事项：

- 引用必须初始化
- 引用在初始化后，不可以再更改引用对象



### 引用做函数参数

作用：函数传参时，可以利用引用的技术让形参修饰实参

优点：可以简化指针修改实参，不需要内存



示例：

```c++
// 1、值传递
void myswap01(int a,int b){
    int temp = a;
    a = b;
    b = temp;
    cout << "myswap01： a = " << a << "  b = " << b << endl;
}
// 2、地址传递
void myswap02(int *a,int *b){
    int temp = *a;
    *a = *b;
    *b = temp;
    cout << "myswap02： a = " << *a << "  b = " << *b << endl;
}
// 3、引用传递
void myswap03(int &a,int &b){
    int temp = a;
    a = b;
    b = temp;
    cout << "myswap03： a = " << a << "  b = " << b << endl;
}
int main(){
    int a = 10;
    int b = 20;
    myswap01(a,b);
    cout << "my      ： a = " << a << "  b = " << b << endl;
    a = 10; b = 20;
    myswap02(&a,&b);
    cout << "my      ： a = " << a << "  b = " << b << endl;
    a = 10; b = 20;
    myswap03(a,b);
    cout << "my      ： a = " << a << "  b = " << b << endl;
    return 0;
}
```

> 总结：通过引用参数产生的效果同按地址传递是一样的。引用的语法更清楚简单
>



### 引用做函数返回值

引用同样可以作为函数的返回值存在

**注意：不要返回局部变量引用**，因为栈区存放的数据会在函数执行完被编译器自动释放掉

用法：函数调用作为左值，例：`int& func()`

示例：

```c++
// 1、不要返回局部变量引用
int& test01(){
    int a = 10;  //局部变量 栈区
    return a;
}
// 2、函数的调用可以作为左值
int& test02(){
    static int a = 10;  //静态变量 全局区
    return a;
}
int main(){
    // int &ref = test01();   //返回局部变量会引发异常
    int &ref = test02();
    test02() = 10050;      //函数可作左值
    cout << ref << endl;
    return 0;
}
```



### 引用的本质

本质：引用的本质在c++内部实现是一个指针常量

讲解示例：

```c++
// 编译器发现是引用，转换为 int* const ref = &a;
void func(int& ref){
    ref = 100;	// ref是引用，转换为*ref = 100
}
int main(){
    int a = 10;
    // 自动转换为 int* const ref = &a;指针常量是指向不可改，也说明为什么引用不可改
    int& ref = a;
    ref = 20;	//内部发现ref是引用，自动帮我们转换为：*ref = 20;
    cout << "a：" << a << endl;
    cout << "ref：" << ref << endl;
    func(a);
    cout << "a：" << a << endl;		//   a=100;
    cout << "ref：" << ref << endl;	// ref=100;
    return 0;
}
```

> 结论：C++推荐引用技术，因为语法方便，引用本质是指针常量，只是指针操作编译器去做了
>



### 常量引用

作用：常量引用主要用来修饰形参，防止误操作

在函数形参列表中，可以加const修饰形参，防止形参改变实参

示例：

```c++
void printA(const int &val){
    // val = 2000;  //修改会抛出异常，防止误操作
    cout << "val = " << val << endl;
}
int main(){
    // 常量引用
    // 加上const后，编译器将代码改为int temp = 10;const int &ref = temp;
    const int &ref = 10;

    // 使用场景：用来修饰形参，防止误操作
    int a = 100;
    printA(a);
    return 0; 
}
```



## 3、类与对象

C++面对对象的三大特性为：封装、继承、多态

C++认为万事万物都皆为对象，对象上有其属性和行为



例如：

​		人可以作为对象，属性有姓名、年龄、身高、体重..，行为有走、跑、跳、吃饭、唱歌…

​		车也可以作为对象，属性有轮胎、方向盘、车灯….行为有载人、放音乐、放空调...

​		具有相同性质的**对象**，我们可以抽象称为**类**，人属于人类，车属于车类



### 封装

#### 封装的意义

封装是C++面向对象三大特性之一

##### **封装的意义一：**

- 将属性和行为作为一个整体，表现生活中的事物
- 将属性和行为加以权限控制

语法：`class 类名{ 访问权限:  属性 / 行为 };`



示例1：设计一个圆类，求圆的周长

示例1代码：

```c++
const double PI = 3.14;

class Circle
{
    //访问权限
public:
    //属性
    double radius;  //半径
    
    //行为
    double calculateZC(){   //计算周长
        return 2 * radius * PI;
    }
};
int main()
{
    //通过圆类实例化一个圆对象
    Circle cir;
    cir.radius = 10;	//用"."访问类的属性和行为
    cout << "圆周长：" << cir.calculateZC() << endl;
    return 0;
}
```



示例2：设计一个学生类，属性有姓名和学号，可以给姓名和学号赋值，可以显示学生的姓名和学号

示例2代码：

```c++
//学生类
class Student{
    //权限
public:
    //类中的属性和行为 我们统一称为成员
    //属性  成员属性 成员变量
    string name;
    string id;
    //方法  成员方法 成员函数
    void Write(string n,string i){
        name = n;
        id = i;
    }
    void Read(){
        cout << "姓名：" << name << "  ";
        cout << "ID：" << id << endl;
    }
};
int main()
{
    Student s1;
    s1.Write("张三","1");
    s1.Read();
    Student s2;
    s2.Write("李四","2");
    s2.Read();
    return 0;
}
```



##### **封装的意义二**：

类在设计时，可以把属性和行为放在不同的权限下，加以控制

访问权限有三种：

1. **public**			 公共权限
2. **protected**      保护权限
3. **private**           私有权限



示例：

```c++
// 公共权限 public     成员 类内可访问  类外可访问
// 保护权限 protected  成员 类内可访问  类外不可访问  子类可访问
// 私有权限 private    成员 类内可访问  类内不可访问  子类不可访问
class Person{
public:		// 姓名 公共权限
    string m_Name;
protected:	// 汽车 保护权限
	string m_Car;
private:	// 密码 私有权限
    int m_Password;
public:
    void read(){	// 类内可以访问公开、保护和私有成员
        m_Name = "张三";
        m_Car = "小卡拉米";
        m_Password = 110011;
        cout << "Name：" << m_Name << endl;
        cout << "Car：" << m_Car << endl;
        cout << "Password：" << m_Password << endl;
    }
};
int main()
{
    // 创建实例化对象
    Person p1;
    // 类外可以访问公共成员
    p1.read();
    p1.m_Name = "李四";
    // 类外不能访问保护和私有成员
    // p1.m_Car = "电动三轮车";
    // p1.m_Password = 123321;
    return 0;
}
```



#### struct和class区别

在C++中 struct 和 class 唯一的区别就在于 **默认的访问权限不同**

- struct 默认权限 **公共 public**
- class   默认权限 **私有 private**



```c++
class C1{
    int A;	//class默认权限 私有
};
struct C2{
    int A;	//struct默认权限 公共
};
int main(){
    C1 c1;
    // c1.A;   //类外访问报错
    C2 c2;
    c2.A;
    return 0;
}
```



#### 成员属性设置为私有

**优点1：**将所有成员属性设置为私有，可以自己控制读写权限

**优点2：**对于写权限，我们可以检测数据的有效性

示例：

```c++
// 成员属性设置为私有
class Person{
public:
    void setName(string name){
        m_name = name;
    }
    string getName(){
        return m_name;
    }
private:
    string m_name;	//可读可写
    int m_age = 19;	//只读
    string m_idol;	//只写
};
```





































































































## 作用域









