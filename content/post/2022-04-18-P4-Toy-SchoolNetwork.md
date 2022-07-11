---
title:       "Improve the access speed of campus network"
subtitle:    "campus network"
description: "通过修改host文件来提升校园网访问速度"
date:        2022-04-18
author:		 Boyu Cai
image:       "/img/post-bg-coffee.jpeg"
published: true
tags:
    - Network
URL: "/2022/04/18/Toy/campus-network"
categories:  ["Toy" ]
---

# 提升校园网络访问速度

## 一、原理

### 请求服务器资源过程：

> 为了得到目标服务器的`ip`地址

1. 访问本机的hosts文件
2. 访问局域网内提供域名解析的`DNS`服务器

再得到服务器`ip`地址后，浏览器即可访问目标服务器



#### 改进空间：

* 一般hosts文件中并无域名
* 将教务选课系统域名和ip地址写入hosts文件可以提升访问速度



## 获取教务系统域名

### 教务系统：

[教务系统](jw.xpaas.dlmu.edu.cn)

![image-20220405114809288](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/image-20220405114809288.png)

**ping 获取域名**

![image-20220405114924634](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/image-20220405114924634.png)



#### 学校网址：

![image-20220405115726670](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/image-20220405115726670.png)

* [官网](https://hall.dlmu.edu.cn/)
* `ip`地址：202.118.86.24



## 写入hosts文件

`windows10`文件系统下:hosts文件路径

```
C:\Windows\System32\drivers\etc
```

**注意备份！ 备份！ 备份！**

![image-20220405121100093](https://personal-drawing-bed.oss-cn-beijing.aliyuncs.com/img/image-20220405121100093.png)

```bash
# DLMU 网站

202.118.86.130  jw.xpaas.dlmu.edu.cn
202.118.86.24    hall.dlmu.edu.cn
```
