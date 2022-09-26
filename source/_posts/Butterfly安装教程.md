---
title: butterfly安装教程
date: 2022-09-23 10:40:27
tags: butterfly安装
cover: https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/butterfly.png
---

# 主题安装教程

## 第一步：执行命令

在你的 Hexo 根目录里，执行指令：

> git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly

## 第二步：修改配置

修改 Hexo 根目录下的 _config.yml，把主题改为butterfly

> theme: butterfly

## 第三步：安装插件

如果你没有 pug 以及 stylus 的渲染器，请下载安装：

> npm install hexo-renderer-pug hexo-renderer-stylus --save

为了减少升级主题后带来的不便，请使用以下方法（建议，可以不做）。

> 在 hexo 的根目录创建一个文件 _config.butterfly.yml，并把主题目录的 _config.yml 内容复製到 _config.butterfly.yml 去。( 注意: 复製的是主题的 _config.yml ,而不是 hexo 的 _config.yml)