---
title: butterfly访问优化
date: 2022-09-23 10:40:27
tags: butterfly优化
cover: https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/butterfly.png
---

# Butterfly访问优化

## Instantpage优化

当鼠标悬停到链接上超过 65 毫秒时，Instantpage 会对该链接进行预加载，可以提升访问速度。

修改配置文件

```yaml
# https://instant.page/
# prefetch (预加载)
instantpage: true
```



## Pjax优化

当用户点击链接，通过ajax更新页面需要变化的部分，然后使用HTML5的pushState修改浏览器的URL地址。

这样可以不用重复加载相同的资源（css/js）， 从而提升网页的加载速度。

```yaml
# Pjax [Beta]
# It may contain bugs and unstable, give feedback when you find the bugs.
# https://github.com/MoOx/pjax
pjax: 
  enable: true
  exclude:
    - /music/
    - /no-pjax/
```

注意：

1. 这个优化暂时还是有很多bug的，可能会出现不可预知的结果
2. 对于一些第三方插件，有些并不支持 pjax 。
    你可以把网页加入到 exclude 里，这个网页会被 pjax 排除在外。
    点击该网页会重新加载网站
3. 使用pjax后，一些自己DIY的js可能会无效，跳转页面时需要重新调用，请参考Pjax文档
4. 使用pjax后，一些个别页面加载的js/css，将会改为所有页面都加载

