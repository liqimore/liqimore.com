---
author: liqimore
categories:
  - 编程
comments: true
date: 2016-04-12 01:17:00+00:00
link: http://blog.codefog.com/js-7.html
slug: js-7
title: Javascript笔记（七）–Location Navigator screen 对象
---


Location对象




location用于获取或设置窗体的URL，并且可以用于解析URL。




语法:  

location.[属性|方法]  

location对象属性图示:




location 对象属性：




location 对象方法:




  

Navigator对象




Navigator 对象包含有关浏览器的信息，通常用于检测浏览器与操作系统的版本。




对象属性:




查看浏览器的名称和版本，代码如下:  

<script type="text/javascript">  

var browser=navigator.appName;  

var b_version=navigator.appVersion;  

document.write("Browser name"+browser);  

document.write("<br>");  

document.write("Browser version"+b_version);  

</script>




screen对象




screen对象用于获取用户的屏幕信息。




语法：  

window.screen.属性  

对象属性:





