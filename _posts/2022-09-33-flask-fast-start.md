---
title: 快速入门系列（四）——第一个Flask程序
date: 2022-09-23 14:00:00 +0800
categories: [快速入门]
tags: [Flask,快速入门系列,使用教程]
pin: true
author: 剑封余华

toc: true
comments: true
typora-root-url: ../../fap8235.github.io
math: false
mermaid: true



---

# Flask是什么？

如果你做过**Web开发**，并且知道什么是**框架**，那你只需要记住，Flask是一个非常**轻量级的Web应用开发框架**

如果你没有做过**Web开发**，但学过**数据库**、**高级编程语言**和**html+css+JavaScript**三剑客，那么你可以这样理解Flask：



***Flask是一门用Python开发的语言，你可以只用这门语言就完成一个软件的开发，包括这个软件的页面开发、数据库开发和服务器开发***



那么这篇文章我们将教大家如何写**第一个Flask程序**，按照计算机学习的传统艺能，我们第一个程序当然是教大家输出一个**Hello World**！！！嘿嘿嘿！！！



> **前方高能！！！请准备好一台电脑！！！跟着动手操作！！！**



# 软件准备

在开始我们的程序编写前，先根据以下安装几个软件：

1. Python（**必备**，下Python3.x系列版本的，自带**pip**）:https://www.python.org/downloads/

   > pip：Python的一个安装插件，用它可以下载别人写好的代码给自己用

2. Pycharm（Python的集成开发环境，类似于DevC++这些，可以不安装，如果需要可以安装）：https://www.jetbrains.com/pycharm/download/

3. Visual Studio Code（代码编辑器，和Pycharm一样有需要安装就行了）：

4. pipenv：在完成Python下载后，按下键盘**Windows键（长相是一个windows的图标）+R键**，在弹出的对话框中输入**cmd**，在对话框中输入：

   ```shell
   pip --version
   ```

   查看pip是否存在，然后输入：

   ```shell
   pip install pipenv
   ```

   等待下载完成



# 环境部署

以D盘为例，在D盘新建一个文件夹flaskstudy，并在其中创建文件夹helloworld。然后，不要打开helloworld，直接在空白处，点击鼠标右键，点击“**在终端中打开**”，在里面输入：

```shell
pipenv install
```

出现这样的内容就成功了：

![](assets/blog_res/屏幕截图 2022-09-23 143552.png)



接着输入：

```shell
pipenv shell
```

出现以下就成功了：

![](assets/blog_res/屏幕截图 2022-09-23 143722.png)



然后，我们安装Flask：
```shell
pipenv install flask
```

等待安装完毕就好了。



> 注意：pipenv是由python替你创建的虚拟环境，每次运行Flask程序前都要先在命令行输入：
>
> ```shell
> pipenv shell
> ```
>
> 
>
> Pycharm的安装及使用教程请看快速入门系列——Pycharm的安装及使用教程



# 代码编写

首先，**不要关闭命令行！！！**看向文件夹，打开helloworld，新建一个文本文档文件并打开，在里面输入：

```python
FLASK_ENV=development
```

> 记得等号前后别加空格

保存，并把文件名连同后缀名一起改成“**.flaskenv**”。这个文件是Flask环境的配置文件，简单来说，它告诉Flask现在是**开发环境**，Flask便会根据它去自动配置服务器的环境

> 什么是环境？
>
> 你可以理解为，它是一堆参数，用来告诉计算机，我要用什么打开我的文件，它应该怎么展示出来，我需要哪些系统的数据等等...



> 注意flaskenv前面是有点的。
>
> 可能会弹出窗口告诉你更改后会不可用，直接确定就行



再新建一个文本文档，在里面写上这样一段：

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
    return '<h1>hello world</h1>'
```

然后，保存，并把文件名连同后缀名一起改成“**app.py**”



最后，在命令行里输入：

```shell
cd helloworld
```

然后输入：

```shell
flask run
```

出现这个界面就成功了：

![](assets/blog_res/屏幕截图 2022-09-23 150203.png)

可以看到这样一句话：

```shell
Running on http://127.0.0.1:5000
```

这就是告诉你，你的代码已经生成了一个网页，我们将**http://127.0.0.1:5000**复制到浏览器的“**输入网址**”中，就可以看到我们的成果了：

<img src="assets/blog_res/屏幕截图 2022-09-23 150436.png" style="zoom: 33%;" />

这是怎么实现的呢？我们回过来先解读下代码：
```python
from flask import Flask
```

这是Python引入包的方式，和Java的<code>import</code>，C/C++的<code>#include</code>是一样的，意思就是引入Flask包里的flask对象



```python
app = Flask(__name__) # __name__：如果你的代码名为hello.py，那么这里__name__的值就是hello
```

这里你可以理解为，我们将app.py这个代码改造为了一个名为app的Web应用程序。



```python
@app.route('/')
```

为app这个Web应用程序设置一个路由（也就是为它设置一个网址），默认为127.0.0.1，端口号为5000。

- 如果括号里的值改为('/home')，那么我们在访问的时候就需要在浏览器中输入http://127.0.0.1:5000/home

- 端口号就相当于：我们给别人提供一个访问这个网址的大门，这个大门有很多，比如：8080



```python
def index():
    return '<h1>hello world</h1>'
```

这里一般称为视图函数，需要紧接着@app.route()这个函数。简单来说，这个函数的返回值会直接显示到上面设置的网址上。

- 如果@app.route()里面的参数是**'/'**，那这个视图函数一般要把函数名，命名为**index**，这是一种默认的规则。在浏览器中，比如你打开百度（www.baidu.com），它的html文件的命名一般是**index.html**
- 如果你学过html基础，又刚好知道html的**body**标签，那么我可以告诉你，如果返回的不是网页文件，那么返回值一般会插入到**body**标签内



# 退出程序

我们看到结果后，回到命令行窗口，按下**Ctrl+C**，再输入**exit**，然后关闭我们的命令行窗口即可。



***好啦，以上就是第一个Flask程序的编写，关于Flask后续的教学，我会一一跟进***
