---
categories:
  - job
comments: true
date: 2021-09-03
description: 21. Merge Two Sorted Lists
tags:
  - leetcode
  - job
  - list
title: 21. Merge Two Sorted Lists
---


* table of contents
{:toc .toc}

## Problem

<https://leetcode-cn.com/problems/merge-two-sorted-lists/>

## Solutions

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode newList = new ListNode();
        ListNode curr = newList;

        while(list1 != null && list2 != null) {
            if(list1.val <= list2.val) {
                curr.next = list1;
                list1 = list1.next;
            } else {
                curr.next = list2;
                list2 = list2.next;
            }
            curr = curr.next;
        }

        if(list1 == null) {
            curr.next = list2;
        }
        if(list2 == null) {
            curr.next = list1;
        }

        

        return newList.next;

    }
}
```

1. 输入两个有序链表
2. 循环遍历直到两个链表均指向null
3. 比较list1和list2的当前值，把curr指针指向小的那一个list
4. list和curr指针均向后移动
5. 循环直到其中一个list为null
6. 由于另一个非null的list还有元素，所以需要把它附加到curr上，同时解决输入其中一个list直接为空的情况（list1为空，则curr.net = list2）

## Reference
