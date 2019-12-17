# D3 709. To Lower Case

## 题目链接

[709. To Lower Case](https://leetcode.com/problems/to-lower-case)

## 题目分析

这个题目要求返回所传字符串的全小写形式。

## 思路

按照C语言的思路，遍历每个字符，判断是不是大写。是大写则转换成小写。

具体转换方法是对这个大写字符减去`A`再加`a`。

在PHP中这么做也是可以的。但是，要记住PHP是用C写的。用内置函数/原生函数的效率比自己写PHP函数效率要高得多。

因此，我们用原生函数[strtolower](http://php.net/strtolower)来实现。

## 最终代码

```php
<?php
class Solution {
    function toLowerCase($str) {
        return strtolower($str);
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

