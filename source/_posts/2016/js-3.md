---
author: liqimore
categories:
  - 编程
comments: true
date: 2016-04-10 23:59:00+00:00
link: http://blog.codefog.com/js-3.html
slug: js-3
title: Javascript笔记（三）–Math对象
---


Math对象，提供对数据的数学计算。  

使用 Math 的属性和方法，代码如下：




<script type="text/javascript">  

var mypi=Math.PI;  

var myabs=Math.abs(-15);  

document.write(mypi);  

document.write(myabs);  

</script>  

运行结果:




3.141592653589793  

15  

注意：Math 对象是一个固有的对象，无需创建它，直接把 Math 作为对象使用就可以调用其所有属性和方法。这是它与Date,String对象的区别。




Math 对象属性




Math 对象方法




以向上取整ceil()为例：  

ceil() 方法可对一个数进行向上取整。




语法:




Math.ceil(x)  

参数说明:




注意：它返回的是大于或等于x，并且与x最接近的整数。




我们将把 ceil() 方法运用到不同的数字上，代码如下：




<script type="text/javascript">  

document.write(Math.ceil(0.8) + "<br />")  

document.write(Math.ceil(6.3) + "<br />")  

document.write(Math.ceil(5) + "<br />")  

document.write(Math.ceil(3.5) + "<br />")  

document.write(Math.ceil(-5.1) + "<br />")  

document.write(Math.ceil(-5.9))  

</script>




运行结果：




1  

7  

5  

4  

-5  

-5  




