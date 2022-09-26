---
title: hexo的使用
date: 2022-09-22 20:42:27
tags: hexo
cover: https://images.alphacoders.com/846/84631.jpg
---

# 安装node.js

# 安装git环境

由于之前在做项目的过程中已经安装过node.js和git，故此处不再演示，可以参考网上其他教程

# 安装hexo

此时已经安装好了node.js和git，下面开始hexo的安装

首先在某一磁盘目录下创建文件夹，我选择的是F盘，文件夹名为 Blog
进入Blog文件夹，右键鼠标->选择Git Bash Here
输入 `npm install -g hexo-cli` ，并耐心等待一段时间
输入 `npm install hexo -save`，也耐心等待一段时间
此时我们可以发现，在Blog文件夹中多了许多内容
在Blog文件夹中新建文件夹，命名为hexo
关闭当前Git Bash，进入hexo文件夹，右键鼠标->选择Git Bash Here，或者直接在当前的Git Bash中输入 cd hexo
输入`hexo init`，初始化hexo环境，耐心等待一段时间
输入`npm install`，安装npm依赖包，耐心等待一段时间
输入`hexo generate`或者是`hexo g`，生成静态页面，耐心等待一段时间
输入`hexo server`或者是`hexo s`，生成本地服务。我们每次写完博客后，可以先在本地预览一下看看有没有什么问题，然后再发布到网上。
接着，我们在浏览器中访问http://localhost:4000/，这就是在本地生成的一个博客。
在Git Bash中按下Ctrl+C，关闭当前端口服务。
到这里，我们的本地博客就已经搭建完成了。下面将介绍如何与Github连接，将博客上传Internet

# 新建Github仓库

登录到自己的Github中，新建一个仓库，命名为username.github.io，其中的username是你的用户名，勾选Initialiaze this repository with a README，创建仓库
我们可以访问自己的username.github.io
返回username.github.io的仓库中，复制Git地址

# 本地操作

我们在/Blog/hexo/文件夹中，找到_config.yml文件，用文本编辑器打开它
将最下面的deploy改为下图所示的内容，其中repo的地址就是刚才我们复制的Git地址，修改好后保存退出 【注】修改内容中的:和后面的字母之间要有一个空格，否则后续内容会报错
接下来，我们暂且不考虑新建文章，在Git Bash中执行npm install hexo-deployer-git --save命令，耐心等待一段时间
最后执行 hexo deploy或者hexo d【注】这一步需要保证Github上拥有本机的公钥，可以自行查找解决办法
最后，成功部署

# 上传博客

## 新建文章

在Git Bash中输入hexo new title，其中，title就是我们这篇文章的名字。我们可以看到，在\Blog\hexo\source_posts\ 文件夹中新建了一个名称为Test1.md的文件
我们去编辑一下这个文件，此处需要Linux的部分知识，可以自行上网查找
编辑结束后，保存退出
上传
使用hexo g，生成静态文件
使用hexo d来将文档部署到Github上
最后我们访问username.github.io，发现刚才编辑的文档已经成功发布到了Internet上面