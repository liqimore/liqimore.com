---
author: liqimore
categories:
  - 编程
comments: true
date: 2017-07-23 15:22:52+00:00
excerpt: 1.函数参数与等效实参的等价关系
link: http://blog.codefog.com/day04-dive-in-c.html
slug: day04-dive-in-c
tags:
  - C语言强化
title: day04- Dive in C
---


1.函数参数与等效实参的等价关系

![](https://static.codefog.com/qiniu/old/2017/07/ee46559d3df289da5a7bd7132817027c.png)

2. ![](https://static.codefog.com/qiniu/old/2017/07/c7c1a81ce06b4263baa0c45764d7f18a.png)

![](https://static.codefog.com/qiniu/old/2017/07/02f91d77afaece2673abb5df7feeba16.png)

结构体定义一个含有如上项目的数据类型Teracher

可以用typedef给这个结构体类型Teacher定一个别名Teacher

![](https://static.codefog.com/qiniu/old/2017/07/51bdf0189309dc0bc76b07d74814adb9.png)

3.定义类型的同时定义了s1,s2两个变量

![](https://static.codefog.com/qiniu/old/2017/07/851357e03c8891b6181c459221fb452d.png)

4.直接创建一个类型的结构体变量而不为这个结构体起名字

![](https://static.codefog.com/qiniu/old/2017/07/4ba71f52a354026883da7af45de26506.png)

5.初始化结构体变量的三种方法

![](https://static.codefog.com/qiniu/old/2017/07/6359abaea28e4a9c29476f551c6c32fa.png)

6.![](https://static.codefog.com/qiniu/old/2017/07/70a305d77945ea5a752199af978fa47f.png)

这个".",是寻址操作,计算age这个变量相当于t1这个大块内存的偏移量

另外,可以通过指针来操作

![](https://static.codefog.com/qiniu/old/2017/07/2bf9f0c360ca34f9ad88d5cf556fc550.png)

7.结构体做函数参数时候,如果需要修改结构体内的值,需要用指针指向结构体才可以

![](https://static.codefog.com/qiniu/old/2017/07/ba865876df309025a6664e15d74ff453.png)

8.为结构题分配内存,

![](https://static.codefog.com/qiniu/old/2017/07/520fba1a2206d215e9a885114f536384.png)

释放结构所占用的内存,

![](https://static.codefog.com/qiniu/old/2017/07/2a4d24d4be8034778558b2eaba2d4e35.png)