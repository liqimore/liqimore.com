---
categories:
  - job
comments: true
date: 2021-09-13 20:22:02
description: 23. Merge k Sorted Lists
tags:
  - leetcode
  - job
  - list
title: 23. Merge k Sorted Lists
---


## Problem

<https://leetcode-cn.com/problems/merge-k-sorted-lists/>

## Solutions

### 暴力解决

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
    public ListNode mergeKLists(ListNode[] lists) {
        
        if(lists.length ==  0) {
            return null;
        }
        // if(lists.length == 1) {
        //     return lists[0];
        // }


        for(int i = 1; i < lists.length; i++) {
            lists[i] = merge2Lists(lists[i-1], lists[i]);
        }

        return lists[lists.length - 1];

    }

    public ListNode merge2Lists(ListNode l1, ListNode l2) {
        ListNode newList = new ListNode();
        ListNode curr = newList;


        while(l1 != null && l2 != null) {
            if(l1.val < l2.val) {
                curr.next = l1;
                l1 = l1.next;
            } else {
                curr.next = l2;
                l2 = l2.next;
            }
            curr = curr.next;
        }

        if(l1 == null) {
            curr.next = l2;
        }
        if(l2 == null) {
            curr.next = l1;
        }

        return newList.next;
    }
}
```

1. 解决合并2个顺序链表
2. 循环调用直到合并完成整个list的有序链表

## Reference
