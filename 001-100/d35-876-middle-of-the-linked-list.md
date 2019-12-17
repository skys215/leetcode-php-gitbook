# D35 876. Middle of the Linked List

## 题目链接

[876. Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)

## 题目分析

返回一个链表中最中间的元素。

## 思路

先全部塞入数组，再根据长度/2得到中间元素的下标，再返回。

## 最终代码

```php
<?php
/**
 * Definition for a singly-linked list.
 * class ListNode {
 *     public $val = 0;
 *     public $next = null;
 *     function __construct($val) { $this->val = $val; }
 * }
 */
class Solution {
    function middleNode($head) {
        $items = [$head];
        while($head){
            $items[] = $head;
            $head = $head->next;
        };
        return $items[ceil(count($items)/2)];
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

