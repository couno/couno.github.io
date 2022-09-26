---
title: butterfly优化页面(一)
date: 2022-09-23 08:56:18
tags: butterfly
cover: https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/butterfly.png
---

# butterfly网页优化

## 背景

在配置文件_config.butterfly.yml中找到theme_color

对其中进行修改，这里是纯色背景

### **图片背景**

将自己喜欢的图片放入 *theme/butterfly/source/img* 中

在 *_config.butterfly.yml* 下找到 background ：

```text
background: url(/blog/img/bg.jpg)
```

按上述代码写好即可

### **使用css注入更换背景**

需要在 *theme/butterfly/source/css* 中新建一个 css 文件，文件名自取

之后在 *_config.butterfly.yml* 下找到 inject ：

```yaml
# Inject
# 插入代码到头部 </head> 之前 和 底部 </body> 之前
inject:
  head:
    - <link rel="stylesheet" href="/css/mycss.css">
    # - <link rel="stylesheet" href="/xxx.css">
  bottom:
    # - <script src="xxxx"></script>
```

在 head 中插入  `- <link rel="stylesheet" href="/css/mycss.css">` 

- 这里需要注意href的地址是否正确

#### 小清新背景实例：

```css
#web_bg {
  background: -webkit-linear-gradient(
    0deg,
    rgba(247, 149, 51, 0.1) 0,
    rgba(243, 112, 85, 0.1) 15%,
    rgba(239, 78, 123, 0.1) 30%,
    rgba(161, 102, 171, 0.1) 44%,
    rgba(80, 115, 184, 0.1) 58%,
    rgba(16, 152, 173, 0.1) 72%,
    rgba(7, 179, 155, 0.1) 86%,
    rgba(109, 186, 130, 0.1) 100%
  );
  background: -moz-linear-gradient(
    0deg,
    rgba(247, 149, 51, 0.1) 0,
    rgba(243, 112, 85, 0.1) 15%,
    rgba(239, 78, 123, 0.1) 30%,
    rgba(161, 102, 171, 0.1) 44%,
    rgba(80, 115, 184, 0.1) 58%,
    rgba(16, 152, 173, 0.1) 72%,
    rgba(7, 179, 155, 0.1) 86%,
    rgba(109, 186, 130, 0.1) 100%
  );
  background: -o-linear-gradient(
    0deg,
    rgba(247, 149, 51, 0.1) 0,
    rgba(243, 112, 85, 0.1) 15%,
    rgba(239, 78, 123, 0.1) 30%,
    rgba(161, 102, 171, 0.1) 44%,
    rgba(80, 115, 184, 0.1) 58%,
    rgba(16, 152, 173, 0.1) 72%,
    rgba(7, 179, 155, 0.1) 86%,
    rgba(109, 186, 130, 0.1) 100%
  );
  background: -ms-linear-gradient(
    0deg,
    rgba(247, 149, 51, 0.1) 0,
    rgba(243, 112, 85, 0.1) 15%,
    rgba(239, 78, 123, 0.1) 30%,
    rgba(161, 102, 171, 0.1) 44%,
    rgba(80, 115, 184, 0.1) 58%,
    rgba(16, 152, 173, 0.1) 72%,
    rgba(7, 179, 155, 0.1) 86%,
    rgba(109, 186, 130, 0.1) 100%
  );
  background: linear-gradient(
    90deg,
    rgba(247, 149, 51, 0.1) 0,
    rgba(243, 112, 85, 0.1) 15%,
    rgba(239, 78, 123, 0.1) 30%,
    rgba(161, 102, 171, 0.1) 44%,
    rgba(80, 115, 184, 0.1) 58%,
    rgba(16, 152, 173, 0.1) 72%,
    rgba(7, 179, 155, 0.1) 86%,
    rgba(109, 186, 130, 0.1) 100%
  );
}
```

```css
#web_bg {
    background: linear-gradient(102.7deg,#fddaff 8.2%,#dfadfc 19.6%,#adcdfc 36.8%,#adfcf4 73.2%,#caf8d0 90.9%);
}
```



## **添加搜索功能**

1. 需要安装 `hexo-generator-search`，使用命令`npm install hexo-generator-search --save`去安装

2. 修改配置文件

3. > local_search:
	>   enable: false #是否开启搜索功能
	>   preload: false	#是否开启预搜索
	>   CDN: #搜索文件的 CDN 地址（默认使用的本地链接）

注意：记得运行`hexo clean`命令



## footer背景

```yaml
# footer是否显示图片背景(与top_img一致)
footer_bg: true
```

想要设置渐变色：渐变色 - linear-gradient( 135deg, #E2B0FF 10%, #9F44D3 100%)



## **字数统计**

要为Butterfly配上字数统计特性, 你需要如下几个步骤:

1. 打开 hexo 工作目录

2. npm install hexo-wordcount --save or yarn add hexo-wordcount

3. 修改 主题配置文件:

4. > wordcount:
	>   enable: true #是否开启字数统计
	>   post_wordcount: true #文字字数统计
	>   min2read: true #阅读人数
	>   total_wordcount: true #总计文字字数



**文章参考**：

- http://t.csdn.cn/UIquL
- http://t.csdn.cn/Ypuap 子文章配置页面