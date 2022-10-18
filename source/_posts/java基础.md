---
title: java基础
date: 2022-10-10 16:36:27
tags: java
---

# Java

## java三个体系

- JavaSE（J2SE）（Java2 Platform Standard Edition，java平台标准版）
- JavaEE(J2EE)(Java 2 Platform,Enterprise Edition，java平台企业版)
- JavaME(J2ME)(Java 2 Platform Micro Edition，java平台微型版)。

## java的主要特性：

1. 面向对象
2. 它是分布式的
3. 是健壮的
4. 安全的
5. 可移植的
6. 简单的
7. 高性能的
8. 多线程的
9. 动态的

---



# Java 基础语法

- **对象**：对象是类的一个实例，有状态和行为。例如，一条狗是一个对象，它的状态有：颜色、名字、品种；行为有：摇尾巴、叫、吃等。

- **类**：类是一个模板，它描述一类对象的行为和状态。

- **方法**：方法就是行为，一个类可以有很多方法。逻辑运算、数据修改以及所有动作都是在方法中完成的。

- **实例变量**：每个对象都有独特的实例变量，对象的状态由这些实例变量的值决定。

![image-20221010164129210](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010164129210.png)

编写java程序时，应注意以下几点

- 大小写敏感
- 类名首字母大写
- 方法名使用驼峰命名规则
- 源文件名应与类名相同
- 主方法入口，需要有主方法入口方可执行

## Java标识符

Java 所有的组成部分都需要名字。类名、变量名以及方法名都被称为标识符。

关于 Java 标识符，有以下几点需要注意：

- 所有的标识符都应该以字母（A-Z 或者 a-z）,美元符（$）、或者下划线（_）开始
- 首字符之后可以是字母（A-Z 或者 a-z）,美元符（$）、下划线（_）或数字的任何字符组合
- 关键字不能用作标识符
- 标识符是大小写敏感的
- 合法标识符举例：age、$salary、_value、__1_value
- 非法标识符举例：123abc、-salary

## Java变量

Java 中主要有如下几种类型的变量

- 局部变量
- 类变量（静态变量）
- 成员变量（非静态变量）

> 三种变量类型

## Java数组（暂停）

## Java枚举

**举例**：

```java
class FreshJuice {
   enum FreshJuiceSize{ SMALL, MEDIUM , LARGE }
   FreshJuiceSize size;
}
 
public class FreshJuiceTest {
   public static void main(String[] args){
      FreshJuice juice = new FreshJuice();
      juice.size = FreshJuice.FreshJuiceSize.MEDIUM  ;
   }
}
```

## Java关键字

![image-20221010164916842](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010164916842.png)

![image-20221010164928000](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010164928000.png)

![image-20221010164938752](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010164938752.png)

![image-20221010164951283](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010164951283.png)

![image-20221010165001356](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010165001356.png)

![image-20221010165009684](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010165009684.png)

![image-20221010165019888](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010165019888.png)

![image-20221010165030281](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010165030281.png)

> 49个关键字

# 继承

在 Java 中，一个类可以由其他类派生。如果你要创建一个类，而且已经存在一个类具有你所需要的属性或方法，那么你可以将新创建的类继承该类。

利用继承的方法，可以重用已存在类的方法和属性，而不用重写这些代码。被继承的类称为超类（super class），派生类称为子类（sub class）。

# 接口

在 Java 中，接口可理解为对象间相互通信的协议。接口在继承中扮演着很重要的角色。

接口只定义派生要用到的方法，但是方法的具体实现完全取决于派生类。

# Java 源程序与编译型运行区别

![image-20221010165412235](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010165412235.png)