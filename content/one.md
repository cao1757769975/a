---
title: "使用Hugo搭建静态站点"
date: 2020-04-03T14:28:28+08:00
---

### 一、安装Hugo

Hugo托管在github.com上，因此获取Hugo很方面，目前有至少两种方法可以安装Hugo。


#### 1、安装包
对于普通用户（无git、无开发经验）而言，直接下载安装包是最简单的方式。我们可以下载Hugo的Release版，截至目前为止最新版本是v0.14，可以在这里下载你的平台(支持linux, windows, darwin, netbsd, freebsd和arm等)对应的版本。不过我发现0.14版本似乎有Bug，在我的MacOsX上生成Hugo Docs站点总是panic。

#### 2、源码编译
对于开发者而言，源码编译是最Geek的方式:

```
go get -u -v github.com/spf13/hugo
go build -o hugo main.go
mv hugo $GOPATH/bin

```

在命令行下执行hugo命令，如果得到类似下面结果，则说明你已经成功安装了Hugo：
```
$hugo version
Hugo Static Site Generator v0.15-DEV BuildDate: 2015-09-20T23:53:39+08:00
```

### 二、生成静态站点
#### 1、创建静态站点
我们来创建一个名为”tonybai.com”的静态站点：
```
$hugo new site tonybai.com
$tree
.
└── tonybai.com
    ├── archetypes
    ├── config.toml
    ├── content
    ├── data
    ├── layouts
    └── static
```

我们看到，通过hugo new site命令，我们建立了tonybai.com站点的后台目录结构。但细心的你会发现：这里的目录都是空的。除了config.toml中可怜的三行内容：

```
baseurl = "http://replace-this-with-your-hugo-site.com/"
languageCode = "en-us"
title = "My New Hugo Site"
```
不过即便目录为空，这也是一个完整的静态站点源文件，我们可以基于这些文件生成我们的站点。 可以启动一下服务'hugo server'

```
$cd tonybai.com
$hugo server

0 draft content
0 future content
0 pages created
0 paginator pages created
0 tags created
0 categories created
in 6 ms
Serving pages from /Users/tony/test/hugotest/tonybai.com/public
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

之后Hugo启动了一个server作为该Site的Web Server。通过浏览器访问http://localhost:1313，你将看到一个完全空白的站点首页。

#### 2、添加Theme
添加了Theme后的站点才有血有肉，丰富多彩。

添加Theme的步骤如下，我们以Hyde Theme为例：

首先创建themes目录，并下载Hyde Theme文件：

```
$ mkdir themes
$ cd themes
$ git clone https://github.com/spf13/hyde.git
```
接下来，我们需要对Site进行一些配置，tonybai.com/config.toml是Site的顶层配置文件，配置后的config.toml文件如下：
```
baseurl = "http://tonybai.com/"
languageCode = "en-us"
title = "Tony Bai"
theme = "hyde"

[params]
    description = "这里是我的个人博客"
    themeColor = "theme-base-08" # for hyde theme
```
其中：
theme = “hyde” 指定站点使用Hyde主题；
themeColor = “theme-base-08″ 指定了站点的主题颜色（默认是黑色的，这里改成一种红色）

在tonybai.com目录下重新执行hugo server，并打开浏览器查看站点首页，你会发现视野里有内容了：

![展示图](/hugoblog/boke.jpg)

#### 3、第一个Post
结构和样式有了，我们还没有内容。我们来创建站点的第一个Post：

```
$hugo new welcome.md
/Users/tony/Test/hugotest/tonybai.com/content/welcome.md created
```
hugo在content下创建welcome.md文件，我们编写一些文件内容：

```
+++
Categories = ["Development", "GoLang"]
Description = ""
Tags = ["Development", "golang"]
date = "2015-09-23T16:30:37+08:00"
menu = "main"
title = "你好，Hugo"

+++

这是使用Hugo创建的站点中的第一篇文章。
```
保存后，重新执行hugo server命令，打开浏览器，你将看到下面的情形：

![展示图](/hugoblog/lct.jpg)