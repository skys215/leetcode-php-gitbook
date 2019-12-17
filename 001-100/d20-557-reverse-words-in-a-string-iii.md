# D20 557. Reverse Words in a String III

## 题目链接

[557. Reverse Words in a String III](https://leetcode.com/problems/reverse-words-in-a-string-iii/)

## 题目分析

题目要求把句子中的每个单词都倒转过来。

## 思路

这个很简单，用空格把句子分割，再用`strrev`把字符串倒转过来，拼接起来就可以了。

## 最终代码

```php
<?php
class Solution {
    function reverseWords($s) {
        $words = explode(' ', $s);
        foreach($words as &$word){
            $word = strrev($word);
        }
        return implode(' ',$words);
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

