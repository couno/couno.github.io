---
title: redis安装与使用
date: 2022-10-04 12:11:25
tags: Redis
cover: https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004121447971.png
---

![image-20221004121447971](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004121447971.png)

# redis安装与使用

> 之前了解过redis，但是没有具体的了解什么是redis,干什么用的。接下来我会逐步的去深入redis，了解它的机制与原理

## 1.安装redis

### 下载

一般来说，redis会安装在Linux上，几乎不会安装在windows上。所以我们需要去GitHub上找`redis for windows`，下面是链接地址（for windows）

> https://github.com/tporadowski/redis/releases

### 解压

解压下载的文件夹到本地（下面是我存放的地址)

![image-20221004122433945](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004122433945.png)

看到`redis-server`了没，没错！！！双击它

![image-20221004122817213](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004122817213.png)

**安装完成**！！！！

是不是很简单，这样就成功了

那么接下来，对redis进行测试和更加深入的使用

## 2.redis初使用

### 配置环境变量

在进行使用之前，我们需要给它配置**环境变量**

> 环境变量，允许你在cmd中快速找到文件目录地址，实现命令快速启动

找到高级系统配置

![image-20221004123231647](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004123231647.png)

![image-20221004123313358](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221004123313358.png)

点击环境变量

![image-20221004123438577](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004123438577.png)

- 用户环境路径：要是不清楚环境配置，建议配置在用户环境配置。以免造成系统其他路径损坏

在这两个地方**其中一个**加入你redis的文件目录地址，放入其中就OK了

![image-20221004123730892](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004123730892.png)

确定。完成系统路径配置

那么接下来你就可以使用cmd命令框进行redis操作

---

### 初次使用

打开cmd窗口，输入命令

#### **启动redis**

```
redis-server
```

启动成功后，不要关闭这个窗口，再打开一个窗口去链接它。（因为redis一般部署在服务器，会持续的运行，所以一般不会关闭，也不能关闭，关闭有可能导致严重损失)

#### **连接redis**

```
redis-cli
```

![image-20221004124643558](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004124643558.png)

这样就完成了连接，接下来我们进行简单的数据读写

#### **数据读写**

![image-20221004125027774](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004125027774.png)

至此，我们就拥有了一个**高性能的 key-value 数据库**

---

## 3.redis配置

> 接下来我们对redis的配置文件作讲解

Redis 的配置文件位于 Redis 安装目录下，文件名为 **redis.conf**(Windows 名为 redis.windows.conf)

首先我们可以输入下面命令获取所有配置信息

```
config get *  //查看所有配置信息
```

![image-20221004125625929](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004125625929.png)

当然，你也可以打开你的配置文件来修改这些配置信息。

如果你知道你需要修改的是什么，那么使用命令会更快

### 语法

```
> CONFIG SET CONFIG_SETTING_NAME NEW_CONFIG_VALUE
```

**实例**

![实例](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221004130802273.png)

😁
