---
author: liqimore
categories:
  - 编程
comments: true
date: 2017-07-22 11:06:33+00:00
excerpt: 1.传智播客扫地僧的视频课程总体来说还是非常棒的.但是!只能当做一个参考!参考!!适合自己查漏补缺,回忆之前的知识点.如果需要深度学习的话,还是要配合书籍以及在实际项目中的实践.
link: http://blog.codefog.com/day03-dive-in-c.html
slug: day03-dive-in-c
tags:
  - C语言强化
title: day03- Dive in C
---


**1.传智播客扫地僧的视频课程总体来说还是非常棒的.但是!只能当做一个参考!参考!!适合自己查漏补缺,回忆之前的知识点.如果需要深度学习的话,还是要配合书籍以及在实际项目中的实践.**

2.C中被const所修饰的变量可以被指针通过他的地址修改

3.指针分配内存方式的不同

![](https://static.codefog.com/qiniu/old/2017/07/8ff54f6b38cd235b813e31400196dff0.png)

4.二级指针的模型

指针数组,![](https://static.codefog.com/qiniu/old/2017/07/3ec51994cfd09876abc62ef5b5b6e7f7.png)

二维数组,

![](https://static.codefog.com/qiniu/old/2017/07/5de559fdbd7757bc402b2497cc664164.png)

动态大小的数组,

![](https://static.codefog.com/qiniu/old/2017/07/f80ef811a01c4a5ecdfacd45d39237dc.png)

 为每一行元素分配内存空间.

![](https://static.codefog.com/qiniu/old/2017/07/df86c94182253f0dbf2fc4e54ef03f68.png)

总共分为三种,分别如下图:

![](https://static.codefog.com/qiniu/old/2017/07/db4e6a83bdf099f007c64e14d3eeba96.png)

5.以上三种分配方式的内存模型:

![](https://static.codefog.com/qiniu/old/2017/07/396a81c04d5daf89003782bb745c13d1.png)

6.在写函数的时候,用N级指针的形参,去改变N-1级指针的实参

7.为数组初始化内存

![](https://static.codefog.com/qiniu/old/2017/07/3c1d9fea674be67ba3908c2498dfeb1b.png)

注意:memset()





  1. 可以通过typedef来自定义一个数组类型的数据结构别名



![](https://static.codefog.com/qiniu/old/2017/07/548799f80fc2caafdd216f4434f382d7.png)

9.数组指针 指向一个数组的指针

![](https://static.codefog.com/qiniu/old/2017/07/0f379f307b71bb5bf2b6fd895a96e82f.png)

创建一个数组类型的指针变量pArray,把这个变量指向一个数组的地址,就可以通过这个变量来操作这个数组了

![](https://static.codefog.com/qiniu/old/2017/07/407a460d324ea2713c451f201e928066.png)

10.直接typedef一个数组指针类型,就可以直接定义出一个指针类型

![](https://static.codefog.com/qiniu/old/2017/07/a9564221dd6f999d57718426359f20ee.png)

11.多维数组的名字,就相当于指针,它经过加一,就会跳到下一行

![](https://static.codefog.com/qiniu/old/2017/07/0c5a7a3daeb131355bcac40367980b7b.png)

三种表示形式:

![](https://static.codefog.com/qiniu/old/2017/07/a40a87874e62182f196c2fe69d497584.png)