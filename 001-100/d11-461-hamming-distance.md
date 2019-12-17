# D11 461. Hamming Distance

## 题目链接

[461. Hamming Distance](https://leetcode.com/problems/hamming-distance/)

## 题目分析

本题要求计算汉明距离。

> 汉明距离是使用在数据传输差错控制编码里面的，汉明距离是一个概念，它表示两个（相同长度）字对应位不同的数量，我们以d（x,y）表示两个字x,y之间的汉明距离。对两个字符串进行异或运算，并统计结果为1的个数，那么这个数就是汉明距离。

--来自 [百度百科](https://baike.baidu.com/item/汉明距离/475174)

在百科里已经描述得很清楚了：进行异或运算，并统计结果为1的个数即得汉明距离。

## 思路

异或就不用说了。用`^`运算符。

统计1的个数也是挺简单的，用`substr_count`就可以了。

## 最终代码

```php
<?php
class Solution {
    function hammingDistance($x, $y) {
        $bin = decbin($x^$y);
        return substr_count($bin,'1');
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

