---
author: liqimore
categories:
  - 编程
comments: true
date: 2016-04-11 17:59:00+00:00
link: http://blog.codefog.com/js-4.html
slug: js-4
title: Javascript笔记（四）–Array 数组对象
---


数组对象是一个对象的集合，里边的对象可以是不同类型的。数组的每一个成员对象都有一个“下标”，用来表示它在数组中的位置，是从零开始的




数组定义的方法：






  1. 定义了一个空数组:  

var  数组名= new Array();


  2. 定义时指定有n个空元素的数组：  

var 数组名 =new Array(n);  

3.定义数组的时候，直接初始化数据：  

var  数组名 = [<元素1>, <元素2>, <元素3>...];  

我们定义myArray数组，并赋值，代码如下：




var myArray = [2, 8, 6];  

说明：定义了一个数组 myArray，里边的元素是：myArray[




数组元素使用：  

数组名[下标] = 值;  

注意: 数组的下标用方括号括起来，从0开始。  

数组属性：  

length 用法：<数组对象>.length；返回：数组的长度，即数组里有多少个元素。它等于数组里最后一个元素的下标加一。




数组方法：




例子代码如下：




<script type="text/javascript">  

var myarr = new Array(3);  

myarr[




I,love,JavaScript  

我们将使用分隔符来分隔数组中的元素，代码如下：




<script type="text/javascript">  

var myarr = new Array(3)  

myarr[




运行结果：




I.love.JavaScript


