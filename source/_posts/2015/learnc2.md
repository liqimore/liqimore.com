---
author: liqimore
categories:
  - 编程
comments: true
date: 2015-10-30 01:27:35+00:00
link: http://blog.codefog.com/learnc2.html
slug: learnc2
title: c语言学习心得（二）
---


学习章节：2.4.0——3.4.3

关于多个函数：首先定义的新函数可以放在开头中间末尾（不在main中），如果要引用，直接 new_fun();语句即可。例子：

    
    #include<stdio.h>
    void new_fun(void)
    {
    	printf("我是新函数！n");
    }
    int main(void)
    {
    	printf("我是输出函数！n");
    	new_fun();
    	printf("我是另一个输出函数！n");
    	new_fun();
    	return 0;
    }


输出结果显而易见，新定义的函数就相当于那个printf函数。

<!--more-->

关于八进制和十六进制数的打印（输出）：

它们如果要显示0和0x前缀，在说明符必须加入＃号，而且使用printf输出时用％0代表八进制，％x代表十六进制。

例如：

    
    printf("dec = %d; octa1 = %o; hex = %xn",x,x,x);
    printf("dec = %d; octa1 = %#xn; hex = %#n",x,x,x);


c的变量十分丰富，不知道后面全都经常用还是只需要熟练定义运用一部分就可以。

