---
title:      "Iterator Design"
subtitle:   "Java Design-pattern Iterator implementation"
excerpt: ""
date:       2022-04-28 12:58:00
author:     "Boyu Cai"
image: ""
published: true
tags:
    - Java
URL: "/2022/04/28/java-Design-pattern-Iterator/"
categories: [ "Tech" ]
---

# 迭代器模式

## 核心思想

* 提供外部访问接口，而不暴露内部对象
* 可扩展的遍历方式
* 可遍历不同种类的对象

## 类图设计

<center>迭代器模式结构图（Iterator）</center>

![迭代器模式.drawio](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/typroa/3046/%E8%BF%AD%E4%BB%A3%E5%99%A8%E6%A8%A1%E5%BC%8F.drawio.png)



* `Aggregate`：聚集的抽象类
* `ConcreteAggregate`：具体的聚集类对象，来扩展**遍历方式**
* `Iterator`：迭代器对象接口
* `Concretelterator`：实现迭代器接口

代码见仓库：https://github.com/dmucby/Design-pattern/tree/master/src/Iterator

## Java 中迭代器设计

### `Iterator` 源码

![image-20220428124329520](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/typroa/3046/image-20220428124329520.png)

接口约定：

* `HasNext`
* `Next`
* `remove`

### `ListIterator`接口

```java
public interface ListIterator<E> extends Iterator<E> {
    E next();
    boolean hasNext();
    boolean hasPrevious();
    E previous();
    int nextIndex();
    int previousIndex();
    void remove();
    void set(E e);
    void add(E e);
}
```

> `Iterator` 进一步封装~

* 提供向前遍历，获取前对象
* 增加获取`Index`方法
* 增添`set` `add`来授予更多权限