# Python 依赖库

pip 是 Python 包管理工具，该工具提供了对Python 包的查找、下载、安装、卸载的功能。

目前如果你在 [python.org](https://www.python.org/) 下载最新版本的安装包，则是已经自带了该工具。

pip 官网：https://pypi.org/project/pip/

你可以通过以下命令来判断是否已安装：

```shell
pip --version     # Python2.x 版本命令
pip3 --version    # Python3.x 版本命令
```

如果你还未安装，则可以使用以下方法来安装：

```shell
sudo apt install python3-pip
```

---



#### 依赖安装

##### 1、OpenCV - Python

OpenCV-Python 是 OpenCV 的 Python API，它结合了 OpenCV C++ API 和 Python 语言的最佳特性。

​	OpenCV 支持多种编程语言，例如 C++、Python、Java 等，并且可在不同的平台上使用，包括 Windows、Linux、OS X、Android 和 iOS。基于 CUDA 和 OpenCL 的高速 GPU 操作接口也在积极开发中。

我们可以使用下面的指令来利用pip包管理器来安装OpenCV - Python：

```shell
sudo pip install opencv-python
```

> [!TIP]
>
> 受国内防火墙因素影响，国内使用pip安装依赖包时下载速度可能较为缓慢；我们可以使用国内镜像站来进行加速；只需要在安装指令后面增加一个参数 -i 加上镜像地址即可；
>
> 以使用中国科学技术大学镜像为例：

```shell
sudo pip install opencv-python -i https://mirrors.ustc.edu.cn/pypi/simple/
```



##### 2、Numpy

NumPy 是一个运行速度非常快的数学库，主要用于数组计算，我们可以指定需要安装的版本；

我们可以使用下面的指令来利用pip包管理器来安装NumPy：

```shell
sudo pip install numpy==1.24.3
```

使用中国科学技术大学镜像加速安装：

```shell
sudo pip install numpy==1.24.3 -i https://mirrors.ustc.edu.cn/pypi/simple/
```



##### 3、xxxx

xxxxxxxxxx；

我们可以使用下面的指令来利用pip包管理器来安装xxxx：

```shell
sudo pip install xxx
```

使用中国科学技术大学镜像加速安装：

```shell
sudo pip install xxxx -i https://mirrors.ustc.edu.cn/pypi/simple/
```



python3 -m venv my_mnn_venv

apt install python3.12-venv

source ./my_mnn_venv/bin/activate

---



### 其他国内镜像源

- 中国科学技术大学镜像源： https://mirrors.ustc.edu.cn/pypi/simple/
- 清华大学TUNA镜像源： https://pypi.tuna.tsinghua.edu.cn/simple
- 阿里云镜像源： http://mirrors.aliyun.com/pypi/simple/
- 华为云镜像源： https://repo.huaweicloud.com/repository/pypi/simple/
- 腾讯云镜像源：https://mirrors.cloud.tencent.com/pypi/simple/
- 上海交通大学：https://mirror.sjtu.edu.cn/pypi/web/simple/ 





[HOME](../入门.md)
