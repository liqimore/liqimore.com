---
author: liqimore
categories:
  - 编程
comments: true
date: 2017-07-24 03:31:21+00:00
excerpt: 1.结构体中套一级指针需要为每一个节点都手动分配内存空间,如链表的每一个节点
link: http://blog.codefog.com/day05-dive-in-c.html
slug: day05-dive-in-c
tags:
  - C语言强化
title: day05- Dive in C
---


1.结构体中套一级指针需要为每一个节点都手动分配内存空间,如链表的每一个节点

![](https://static.codefog.com/qiniu/old/2017/07/245fc477735f5193cb68cf9d923d6d00.png)

2.在结构体中套二级指针的含义相当于一个结构体中的二维数组,通过一个二级指针,指向一级指针,再用一级指针指向不同的节点,相当于行和列.





  1. 浅拷贝,就是说在拷贝变量的内容的时候,只会对指针的地址进行拷贝,相当于当时有两个指针指向同一个内存空间



![](https://static.codefog.com/qiniu/old/2017/07/a57c9a075fb43a1763ffe785506b7ce7.png)

4.如果需要进行深拷贝,就需要手动的显示分配内存,如图所示,

![](https://static.codefog.com/qiniu/old/2017/07/34225d3eba7fff536ee7dd7dc587605c.png)

5.结构体中的相对偏移量就是说每个结构体元素在这个结构体中内存的相对位置, 基址+偏移量就是这个元素的具体位置

求解相对偏移量的方法,

![](https://static.codefog.com/qiniu/old/2017/07/f0505c93fa6ce2d9221ee890932c39a2.png)

6.偏移量的作用

![](https://static.codefog.com/qiniu/old/2017/07/10e8a2667cd53a2f6125b0255090873a.png)

7.c中打开文件的方式

![](https://static.codefog.com/qiniu/old/2017/07/03b5fad00a87e4c422ec09690c03b111.png)





  1. **跳过文件配置读写和加解密,本次回顾c语言只作为知识点的复习,为C++做准备**

