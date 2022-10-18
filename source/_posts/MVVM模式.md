---
title: MVVM模式
date: 2022-10-12 10:02:38
tags: MVVM
---

# 什么是MVVM

MVVM，是Model-View-ViewModel的简写，是M-V-VM三部分组成。它本质上就是MVC 的改进版。

MVVM 就是将其中的View 的状态和行为抽象化，其中ViewModel将视图 UI 和业务逻辑分开，它可以取出 Model 的数据同时帮忙处理 View 中由于需要展示内容而涉及的业务逻辑。

MVVM采用**双向数据绑定**，这里在学习Vue的时候经常使用

view中数据变化将自动反映到viewmodel上，反之，model中数据变化也将会自动展示在页面上。把Model和View关联起来的就是ViewModel。ViewModel负责把Model的数据同步到View显示出来，还负责把View的修改同步回Model。

MVVM核心思想，是关注model的变化，让MVVM框架利用自己的机制自动更新DOM，也就是所谓的数据-视图分离，数据不会影响视图。

# 优点

## 1、Controller简洁清晰

 ViewModel分离出来大部分的Controller代码，更加清晰和容易维护。

## 2、方便测试

大部分Bug来自于逻辑处理，由于ViewModel把逻辑分离出来，可对ViewModel构造单元测试。

## 3、开发解耦

1）一位开发者负责逻辑实现，另一位开发者负责UI实现

2）敏捷开发中，并非等后端借口提供后再开发，提供前可完成Controller和View的开发工作。

## 4、缺点

1、代码量比MVC多。

2、需对每个Controller实现绑定，这是分离不可避免的工作量。
