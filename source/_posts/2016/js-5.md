---
author: liqimore
categories:
  - 编程
comments: true
date: 2016-04-11 20:30:00+00:00
link: http://blog.codefog.com/js-5.html
slug: js-5
title: Javascript笔记（五）–window 对象 [重点]
---


window对象




window对象是BOM的核心，window对象指当前的浏览器窗口。




window对象方法:




计时器setInterval()  

语法:  

setInterval(代码,交互时间);  

参数说明：






  1. 代码：要调用的函数或要执行的代码串。



  2. 交互时间：周期性执行或调用表达式之间的时间间隔，以毫秒计（1s=1000ms）。





返回值:




一个可以传递给 clearInterval() 从而取消对"代码"的周期性执行的值。




调用函数格式(假设有一个clock()函数):  

setInterval("clock()",1000)  

或  

setInterval(clock,1000)  

我们设置一个计时器，每隔100毫秒调用clock()函数，并将时间显示出来，代码如下:  

<!DOCTYPE HTML>  

<html>  

<head>  

<meta http-equiv="Content-Type" content="text/html; charset=utf-8">  

<title>计时器</title>  

<script type="text/javascript">  

var int=setInterval(clock, 100)  

function clock(){  

var time=new Date();  

document.getElementById("clock").value = time;  

}  

</script>  

</head>  

<body>  

<form>  

<input type="text" id="clock" size="50"  />  

</form>  

</body>  

</html>




取消计时器clearInterval()




clearInterval() 方法可取消由 setInterval() 设置的交互时间。  

语法：




clearInterval(id_of_setInterval)  

参数说明:  

id_of_setInterval：由 setInterval() 返回的 ID 值。




每隔 100 毫秒调用 clock() 函数,并显示时间。当点击按钮时，停止时间,代码如下:  

<!DOCTYPE HTML>  

<html>  

<head>  

<meta http-equiv="Content-Type" content="text/html; charset=utf-8">  

<title>计时器</title>  

<script type="text/javascript">  

function clock(){  

var time=new Date();  

document.getElementById("clock").value = time;  

}  

// 每隔100毫秒调用clock函数，并将返回值赋值给i  

var i=setInterval("clock()",100);  

</script>  

</head>  

<body>  

<form>  

<input type="text" id="clock" size="50"  />  

<input type="button" value="Stop" onclick="clearInterval(i)"  />  

</form>  

</body>  

</html>




计时器setTimeout()




setTimeout()计时器，在载入后延迟指定时间后,去执行一次表达式,仅执行一次。  

语法:




setTimeout(代码,延迟时间);  

参数说明：






  1. 要调用的函数或要执行的代码串。


  2. 延时时间：在执行代码前需等待的时间，以毫秒为单位（1s=1000ms)。




取消计时器clearTimeout()




setTimeout()和clearTimeout()一起使用，停止计时器。  

语法:




clearTimeout(id_of_setTimeout)  

参数说明:  

id_of_setTimeout：由 setTimeout() 返回的 ID 值。该值标识要取消的延迟执行代码块。


