---
author: liqimore
categories:
  - 编程
comments: true
date: 2016-02-13 21:24:57+00:00
link: http://blog.codefog.com/learnc4.html
slug: learnc4
title: c语言学习心得（四） -- 按照字典顺序排序的分析
---


冒泡算法简单，就不说了，这里来说一下按照字典顺序排序。

首先，需要了解一下string.h库中的strcmp()函数，[点击此处](http://timelovelife.com/csucha/string/strcmp.html)查看详细信息。我这里主要利用该函数的返回值：


<blockquote>（1）字符串1=字符串2，返回0（2）字符串1>字符串2，返回一个正整数（3）字符串1<字符串2，返回一个负整数。</blockquote>


通过以上返回值即可通过临时变量交换把拥有较大的ASCIII码值的字符串输出来。定义新函数：

    
    #include <string.h>
    //输入一个字符串数组，按照字典顺序输出该数组中的所有元素
    int ZiDianPaiXu(const char *arr[] , int n){
    int i,j,k;
        for(i=0;i<n;i++){
            for(k=i,j=k+1;j<n;j++)
                if(strcmp(s[k],s[j])>0)
                    k=j;
            if(i!=k){
                s[i]=(char *)((unsigned)s[i]^(unsigned)s[k]);//交换指针
                s[k]=(char *)((unsigned)s[k]^(unsigned)s[i]);
                s[i]=(char *)((unsigned)s[i]^(unsigned)s[k]);
            }
        }


n为数组长度，可以在之后main中输入具体的值。

<!--more-->

上次[转载的文章](http://timelovelife.com/c-dictionary-order.html)，使用了[strcpy函数](http://baike.baidu.com/view/1026861.htm)，这个函数的作用是复制字符串直到 /0 结束。


<blockquote>

> 
> 原型声明：char *strcpy(char* dest, const char *src);
> 
> 

> 
> 头文件：#include <string.h> 和 #include <stdio.h>
> 
> 

> 
> 功能：把从src地址开始且含有NULL结束符的字符串复制到以dest开始的地址空间
> 
> 

> 
> 说明：src和dest所指内存区域不可以重叠且dest必须有足够的空间来容纳src的字符串。
> 
> 

> 
> 返回指向dest的指针。
> 
> </blockquote>




代码如下：






    
    intj,k;
     
           for(j=0;j<8;j++)
     
           for(k=j+1;k<8;k++)
     
           {
     
                         if(strcmp(str[j],str[k])>0)
     
                         {//交换
     
                                strcpy(temp,str[j]);
     
                                strcpy(str[j],str[k]);
     
                                strcpy(str[k],temp); 
     
                         }
     
           }
     
                  for(i=0;i<8;i++)//输出
     
                         printf("%s\n",str[i]);


两种方法实现的结果都是差不多的，只是第二种易于理解。

另外找到他人写的一个排序代码，非常喜欢，在这里收藏下来。

    
    #include <stdio.h>
    #include <string.h>
      
    const int MAXLEN = 100;
    const int MAXSIZE = 10;
       
    void sort(char title[][MAXLEN],int n) {//排序
        int i,j,k;
        char tstr[MAXLEN];
        for(i = 0; i < n - 1; ++i) {
            k = i;
            for(j = i + 1; j < n; ++j) {
                if(strcmp(title[k],title[j]) > 0)
                    k = j;
            }
            if(k != i) {
                strcpy(tstr,title[k]);
                strcpy(title[k],title[i]);
                strcpy(title[i],tstr);
            }
        }
    }
      
    void show(char s[][MAXLEN],int n) {
        int i;
        for(i = 0; i < n; ++i)
            printf("%s",s[i]);
        puts(" ");
    }
       
    int main(void) {
        char s[MAXSIZE][MAXLEN];
        int i;
        for(i = 0; i < MAXSIZE; ++i) {
            printf("string(%02d/%d):",i + 1,MAXSIZE);
            fgets(s[i],MAXLEN,stdin);
        }
        printf("排序前:\n");
        show(s,MAXSIZE);
        sort(s,MAXSIZE);
        printf("排序后:\n");
        show(s,MAXSIZE);
        return 0;
    }




