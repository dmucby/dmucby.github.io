---
title:       "RTMP"
subtitle:    "RTMP推流简单介绍与部署"
description: "将视频信息推流与图像传输部署在服务器上用于硬件服务"
date:        2022-06-16
author:      蔡博宇
image:       "/img/programming/Nginx/post-bg-coffee.jpeg"
published: true
tags:
    - Nginx
URL: "/2022/6/16/Nginx/RTMP"
categories:  ["Tech" ]
---

# RTMP

> Real Time Messaging Protocol（实时消息传输协议）

## 协议基础

### 特点：

* 依赖TCP
  * 通过握手建立安全连接
  * 建立网络流
  * 播放

![img](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/36f5ff95ce46485d8619e3fa71ea1da4tplv-k3u1fbpfcp-zoom-in-crop-mark1304000.webp)

### RTMP vs TCP

* RTMP 将数据格式格式化
* RTMP 将 message 分成多个Chunk每个Chunk通过ID进行区分，接收端会把Chunk合并



### RTMP 握手

RTMP 三次握手认定

![img](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/fa8f93c741cf43dbbf86c43dca93f6cdtplv-k3u1fbpfcp-zoom-in-crop-mark1304000.webp)

> C 标识客户端      S 表示服务器

1. c 发出信息 c0 表示版本号，不用立即回复，立即发出c1，c1包含时间戳
2. 服务器收到 c0 时，发出 s0 表示自身版本号（版本号不匹配直接断开连接）
3. 服务器发送 s0 后发送自己的时间戳 s1 
4. 客户端收到 s1 后发送时间戳 ack c2 表明收到了 s1
5. 服务器收到 c1 也需要发送一个 ack s1



## 搭建 RTMP 服务

1. 搭建 Nginx 服务器
2. 为Nginx添加RTMP服务
3. 利用OBS推流和拉流

实时效果：

![image-20220616175502538](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/image-20220616175502538.png)



## 参考文章：

* https://juejin.cn/post/6956240080214327303

