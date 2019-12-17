# D25 500. Keyboard Row

## 题目链接

[500. Keyboard Row](https://leetcode.com/problems/keyboard-row/)

## 题目分析

给定一个字符串数组，返回那些所出现的字母在QWERTY键盘中同一行的字符串。

例如，单词`hello`中，字母`h`和`l`在键盘的第二行（或者中间那一行），剩余字母`e`和`o`在第一行。故排除之。  
再如，`Dalas`中，所有字母都在中间那一行，则返回它。

## 思路

我的思路是，把键盘中每一行出现的字母存进3个数组中（因为有3行），将每个字符串分割成数组，判断该数组与每一行字母数组是否有差集。如果分散在不同行，则必定会在与某一行有差。用array\_filter函数过滤这些有差的字符串即可。

## 最终代码

```php
<?php
class Solution {
    function findWords($words) {
        return array_filter($words, function($val){
            $val = array_unique(str_split(strtolower($val)));
            $q = ['q','w','e','r','t','y','u','i','o','p'];
            $a = ['a','s','d','f','g','h','j','k','l'];
            $z = ['z','x','c','v','b','n','m'];

            return !(array_diff($val,$q) && array_diff($val,$a)&&
                array_diff($val,$z));
        });
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

