---
title: 快速入门系列（一）——Git简介及安装教程
date: 2022-09-22 15:30:00 +0800
categories: [快速入门]
tags: [Git,快速入门系列,安装教程]
pin: true
author: 剑封余华

toc: true
comments: true
typora-root-url: ../../fap8235.github.io
math: false
mermaid: true



---

# 什么是Git？

举个例子：

- 第一天，甲方让你做了一个**方案A**。

- 第二天，甲方让你改**方案A**为**方案B**。

- 第三天，甲方让你找回**方案A**。



如果你直接在方案A的文件上改内容并保存，那么等你需要找回方案A的时候，就会发现找不到了，这时候就很绝望QAQ

![](/assets/blog_res/8f9d64d22334815d3755b7243d0e2bb4.jpeg)



而如果你将**方案A改后的内容**另存为**方案B**，你又需要多建一个文件，多保存一份，慢慢的随着方案的增多，你就会发现，电脑存储空间不够了啊啊啊！！！

![](/assets/blog_res/29381f30e924b8996ce719b16c061d950b7bf664.jpg)



于是，发明了Linux的带佬Linus，便用了==一周==时间，写出了**Git**！！！

它让我们可以方便的找回方案A，并且只保存方案B中和方案A**不同的**部分，**节省**我们的存储空间！！！



***同样的，Git适用于我们对项目进行更改，因为我们的软件项目，可能随时需要我们更改代码***



# 那么，Git怎么用呢？

我们先要下载Git：

下载链接：https://git-scm.com/

打开网址后点红框里的**Download for Windows**：

![](/assets/blog_res/屏幕截图 2022-09-22 145057-1663829640512-4.png)



跟着红框点就好啦：

![](/assets/blog_res/屏幕截图 2022-09-22 145549.png)



等待下载，下载结束后，我们打开这个exe文件，进行安装。然后，接下来的步骤，如果我没有明确说的，点next就好了。（顺带一提，这里引用了CSDN的博主mukes的文章图片，需要的话可以查看他的Git安装教程）

[原文链接]: https://blog.csdn.net/mukes/article/details/115693833



这里建议不要存在C盘，一般我们存储在D、E盘哈，点击"Browse..."更改路径：

![](/assets/blog_res/2d94424e09494c5790d0cfef5336d428.png)



这里的话有需要勾上就好了，没需要的话就不用勾了：

![](/assets/blog_res/cd76ed04785e48f7aefd1248e3a53758.png)



勾上左下角的“Don't create a Start Menu folder”：

![](/assets/blog_res/6414569159a044d1944bd0a1a023bbfa.png)

其他的就点“Next”，“Install”和“Finish”就好啦。



