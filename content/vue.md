---
title: "如何快速创建 Vue"
date: 2020-04-22T15:35:30+08:00
---

## vue创建项目（npm安装→初始化项目）
### 第一步npm安装
首先：先从nodejs.org中下载nodejs
![图1](/hugoblog/1.jpg)
双击安装，在安装界面一直Next
![图2](/hugoblog/2.jpg)
![图3](/hugoblog/3.jpg)
![图4](/hugoblog/4.jpg)
直到Finish完成安装。

打开控制命令行程序（CMD）,检查是否正常
![图5](/hugoblog/5.jpg)

使用淘宝NPM 镜像
大家都知道国内直接使用npm 的官方镜像是非常慢的，这里推荐使用淘宝 NPM 镜像。
```
$  npm  install  -g  cnpm  --registry=https://registry.npm.taobao.org
```
这样就可以使用cnpm 命令来安装模块了：

### 第二步项目初始化
##### 1.第一步：安装vue-cli

cnpm install vue-cli -g      //全局安装 vue-cli

![图6](/hugoblog/6.jpg)
查看vue-cli是否成功，不能检查vue-cli,需要检查vue

![图7](/hugoblog/7.jpg)

选定路径，新建vue项目，这里我是在桌面上新建了sun文件夹，cd目录路径

下面我一项目名为sell新建vue项目

vue init webpack  ”项目名称“
![图8](/hugoblog/8.jpg)

现在已经创建好了，那就让项目先安装下依赖再运行一下，会出现下面的页面，操作指令是：
```
cnpm install

cnpm run dev
```
注意 这里要在sell下进行安装和运行哦!!!

![图9](/hugoblog/9.jpg)
进入网址，如下图：
![图10](/hugoblog/10.jpg)
恭喜安装成功了哦！！！

利用vue-cil初始化构建vue项目，我们会获得一个初始化的文件夹结构，如下：
![图11](/hugoblog/11.jpg)
下面开始进入你的vue之旅吧！！