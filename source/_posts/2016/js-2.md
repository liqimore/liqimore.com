---
author: liqimore
categories:
  - 编程
comments: true
date: 2016-04-10 23:55:00+00:00
link: http://blog.codefog.com/js-2.html
slug: js-2
title: Javascript笔记（二）–String 字符串对象
---


定义字符串的方法就是直接赋值。比如：  

var mystr = "I love JavaScript!"  

定义mystr字符串后，我们就可以访问它的属性和方法。




访问字符串对象的属性length:  

stringObject.length; 返回该字符串的长度。




var mystr="Hello World!";  

var myl=mystr.length;  

以上代码执行后，myl 的值将是：12







访问字符串对象的方法：




使用 String 对象的 toUpperCase() 方法来将字符串小写字母转换为大写：




var mystr="Hello world!";  

var mynum=mystr.toUpperCase();




以上代码执行后，mynum 的值是：HELLO WORLD!




注： toLowerCase() 转化为小写




返回指定位置的字符




charAt() 方法可返回指定位置的字符。返回的字符是长度为 1 的字符串。  

语法:




stringObject.charAt(index)




参数说明：




注意：1.字符串中第一个字符的下标是 0。最后一个字符的下标为字符串长度减一（string.length-1）。  

2.如果参数 index 不在 0 与 string.length-1 之间，该方法将返回一个空字符串。  

如:在字符串 "I love JavaScript!" 中，返回位置2的字符：




<script type="text/javascript">  

var mystr="I love JavaScript!"  

document.write(mystr.charAt(2));  

</script>  

注意：一个空格也算一个字符。  

以上代码的运行结果：




l




返回指定的字符串首次出现的位置




indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。  

语法




stringObject.indexOf(substring, startpos)




参数说明：




说明：  

1.该方法将从头到尾地检索字符串 stringObject，看它是否含有子串 substring。  

2.可选参数，从stringObject的startpos位置开始查找substring，如果没有此参数将从stringObject的开始位置查找。  

3.如果找到一个 substring，则返回 substring 的第一次出现的位置。stringObject 中的字符位置是从 0 开始的。  

注意：1.indexOf() 方法区分大小写。  

2.如果要检索的字符串值没有出现，则该方法返回 -1。  

例如: 对 "I love JavaScript!" 字符串内进行不同的检索：




<script type="text/javascript">  

var str="I love JavaScript!"  

document.write(str.indexOf("I") + "<br />");  

document.write(str.indexOf("v") + "<br />");  

document.write(str.indexOf("v",8));  

</script>  

以上代码的输出：







字符串分割split()




知识讲解：




split() 方法将字符串分割为字符串数组，并返回此数组。  

语法：




stringObject.split(separator,limit)  

参数说明:




  

提取字符串substring()




substring() 方法用于提取字符串中介于两个指定下标之间的字符。




语法:  

stringObject.substring(starPos,stopPos)  

参数说明:




提取指定数目的字符substr()




substr() 方法从字符串中提取从 startPos位置开始的指定数目的字符串。




语法:  

stringObject.substr(startPos,length)




参数说明:




大部分摘自慕课网，发在这里方便自己查询


