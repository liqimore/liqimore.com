---
author: liqimore
categories:
  - 编程
comments: true
date: 2016-08-13 18:33:00+00:00
link: http://blog.codefog.com/aa.html
slug: aa
title: markdown测试
---


这是一个段代码`ddd` , 如果去掉``,则显示为加粗


<blockquote>大段落 引</blockquote>


[c]
#include 
#include 
using namespace std;
const int MaxValue = 10000;//初始设定的权值最大值
const int MaxBit = 4;//初始设定的最大编码位数
const int MaxN = 10;//初始设定的最大结点个数
struct HaffNode//哈夫曼树的结点结构
{
    int weight;//权值
    int flag;//标记
    int parent;//双亲结点下标
    int leftChild;//左孩子下标
    int rightChild;//右孩子下标
};
struct Code//存放哈夫曼编码的数据元素结构
{
    int bit[MaxBit];//数组
    int start;//编码的起始下标
    int weight;//字符的权值
};
void Haffman(int weight[], int n, HaffNode haffTree[])
//建立叶结点个数为n权值为weight的哈夫曼树haffTree
{
    int j, m1, m2, x1, x2;
    //哈夫曼树haffTree初始化。n个叶结点的哈夫曼树共有2n-1个结点
    for (int i = 0; istart] = 1;//右孩子结点编码1
                                      //cd->start--;
            cd->start++;//改成编码自增--morgan
            child = parent;
            parent = haffTree[child].parent;
        }
        //保存叶结点的编码和不等长编码的起始位
        //for(intj=cd->start+1;jstart - 1; j >= 0; j--)//重新修改编码，从根节点开始计数--morgan
            haffCode[i].bit[cd->start - j - 1] = cd->bit[j];
 
        haffCode[i].start = cd->start;
        haffCode[i].weight = cd->weight;//保存编码对应的权值
    }
}
int main()
{
    int i, j, n = 4, m = 0;
    int weight[] = { 2,4,5,7 };
    HaffNode*myHaffTree = new HaffNode[2 * n - 1];
    Code*myHaffCode = new Code[n];
    if (n>MaxN)
    {
        cout 
[/c]