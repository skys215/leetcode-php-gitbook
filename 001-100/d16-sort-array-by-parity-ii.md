# D16 922. Sort Array By Parity II

## 题目链接

[922. Sort Array By Parity II](https://leetcode.com/problems/sort-array-by-parity-ii/)

## 题目分析

给定一个整数数组`A`，使数组中偶数位的值为偶数，奇数位的值为奇数。

例如，`A[0]`，0是偶数，所以`A[0]`要为偶数。`A[1]`，1是奇数，所以`A[1]`要为奇数。

## 思路

用`array_filter` 拆分数组中的偶数和奇数，再轮流塞进新数组中。

## 最终代码

```php
<?php
class Solution {
    function sortArrayByParityII($A) {
        $odd = array_filter($A, function($val){
            return ($val&1); 
        });
        $odd = array_values($odd);
        $even = array_filter($A, function($val){
            return (!($val&1)); 
        });
        $even = array_values($even);
        $a = [];
        foreach($odd as $key => $o){
            $a[] = $even[$key];
            $a[] = $o;
        }
        return $a;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

