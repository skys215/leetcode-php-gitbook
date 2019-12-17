# D24 476. Number Complement

## 题目链接

[476. Number Complement](https://leetcode.com/problems/number-complement/)

## 题目分析

给定一个数字，将他转换成二进制后，将0和1对调过来，把对调后的二进制再转换成十进制。返回该数字即可。

## 思路

题目描述得已经很清楚了。

先用`decbin`转换成二进制，用str\_replace把0和1对调过来。

要注意对调的时候，不能直接对调。需要先把0换成除1之外的其他字符，最后再把他替换过来。  
因为str\_replace会按顺序逐个替换。如果先把0替换成1，那么它在替换1的时候，会全替换成0。你就会得到全0的字符串。

替换完成之后，在用`bindec`转换成十进制即可。

## 最终代码

```php
<?php
class Solution {
    function findComplement($num) {
        return bindec(str_replace([0,1,2],[2,0,1],decbin($num)));
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

