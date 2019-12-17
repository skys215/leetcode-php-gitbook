# D34 977. Squares of a Sorted Array

## 题目链接

[977. Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/)

## 题目分析

本题比较简单。对给定数组的每一个数字的平方。并对结果进行排序。

## 思路

遍历每一个元素，相乘自身。塞入新数组。

再用sort函数排序。

## 最终代码

```php
<?php
class Solution {
    function sortedSquares($A) {
        $z = [];
        foreach($A as $b){
            $z[] = $b*$b;
        }
        sort($z);
        return $z;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

