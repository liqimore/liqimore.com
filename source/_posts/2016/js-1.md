---
author: liqimore
categories:
  - 编程
comments: true
date: 2016-04-10 23:44:00+00:00
link: http://blog.codefog.com/js-1.html
slug: js-1
title: Javascript笔记（一）-- Date 日期对象
---


日期对象可以储存任意一个日期，并且可以精确到毫秒数（1/1000 秒）。




定义一个时间对象 :




var Udate=new Date();




注意:使用关键字new，Date()的首字母必须大写。  

使 Udate 成为日期对象，并且已有初始值：当前时间(当前电脑系统时间)。  

如果要自定义初始值，可以用以下方法：




var d = new Date(2012, 10, 1);  //2012年10月1日  

var d = new Date('Oct 1, 2012'); //2012年10月1日




我们最好使用下面介绍的“方法”来严格定义时间。  

访问方法语法：“<日期对象>.<方法>”  

Date对象中处理时间和日期的常用方法：




以第一个为例：




<!DOCTYPE html>  

<html>  

<head>  

<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />  

<title>获得年份 </title>  

<script type="text/javascript">  

var mydate=new Date();  

var myyear = mydate.getFullYear();  

document.write("年份:"+myyear);  

</script>  

</head>  

<body>  

</body>  

</html>  




