---
title: "使用Hugo搭建自己的博客"
date: 2017-09-01T15:03:01+08:00
draft: false
image : "/images/bg.jpg"
---

作为一名程序猿，觉得还是需要一个属于自己的博客，一来可以当做是一个笔记，用于知识积累，必要的时候还可以翻看翻看；二来，也可以拿出来装装逼，给自己加点筹码。接下来我就简单阐述下如何用[Hugo](https://gohugo.io/)搭建个人博客。</br>
![Hugo Logo](/images/hugoLogo.png)
#### **为什么选用Hugo**

现在主流的搭建博客工具有[Wordpress](https://wordpress.org/)、[Ghost](https://github.com/TryGhost)、[Hexo](https://hexo.io/zh-cn/index.html)...之所以选择Hugo,就两个字**简单**！正如官网所说，Hugo是世界上最快的建站框架，是最受欢迎的开源静态站点生成器之一。哪怕你是一个程序小白，也能玩起来，这就是它受欢迎的原因！</br>

#### **如何使用Hugo**
服务器搭建啥的此处就不赘述了，直入主题:</br>
##### **Step 1: 安装**

因为各种系统的安装方式不同，所以大家可以在该链接下具体查看[https://gohugo.io/getting-started/installing](https://gohugo.io/getting-started/installing)

##### **Step 2: 创建新站点**

```
hugo new site **_blog
```

##### **Step 3: 添加主题**

在themes文件夹下安装主题,以vienna为例
```
$ cd themes
$ git clone https://github.com/keichi/vienna
```
主题下面有相应的配置项，具体在哪儿用后面再讲


##### **Step 4: 配置Hugo**
步骤2创建的站点目录下有个config.toml文件，建议用代码编辑器打开它，（这里有个小坑，最好不要用笔记本啥的打开，因为保存编码会有问题，导致页面出现乱码），然后修改主题等配置

```
BaseUrl= "https://localhost:1313/"
LanguageCode= "en-us"
theme = "vienna"
Title= "Damon Lv"
paginate = 10


[params]
    smartToc = true
    katex = true
    github = "lvjunjie"
    avatar = "/images/about_header.jpg"
    contact = "mailto:532711255@qq.com"
    subtitle = "吕俊杰的博客"
    image = "/images/cover_polenord.jpg"
```

##### **Step 5:写博客**
做完以上工作后，就可以开始写自己的博客了，首先需要添加一篇文章
```
hugo new posts/my-first-post.md
```
打开新增的md文件，文章需要用markdown格式书写（H5代码部分也能生效，但不建议使用）

```
+++
author = ""
date = "2017-08-16T17:00:14+08:00"
draft = true
title = "使用Hugo"
tags = []
image = "/images/bg.jpg"
comments = true     # set false to hide Disqus comments
share = false        # set false to share buttons
menu = ""           # set "main" to add this content to the main menu
+++

    ---以下是内容----
    使用Hugo搭建博客
```

##### **Step 6:生成博客**
```
$ hugo server -D
```
如果一切正常的话，地址栏内访问 http://localhost:1313 就能看到自己的博客了

##### **Step 7:服务器发布**

```
hugo --theme=vienna --baseUrl="域名地址"
```
所有静态页面都会生成到 public 目录下。

#### **结语**

平时写博客可以在本地写，完成后再同步到服务器上去。
![金鸡湖](/images/jinjihu.jpg)