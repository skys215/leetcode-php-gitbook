# D7 905. Sort Array By Parity

## 题目链接

[905. Sort Array By Parity](https://leetcode.com/problems/sort-array-by-parity/)

## 题目分析

这个题目非常简单。要求把数组重新排序成偶数在前，奇数在后。

## 思路

把数组拆分成奇偶两组，再拼接即可。

## 最终代码

```php
<?php
class Solution {
    function sortArrayByParity($A) {
        $odd = array_filter($A,function($var){return ($var & 1);});
        $even = array_filter($A,function($var){return (!($var & 1));});
        return $even + $odd;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

