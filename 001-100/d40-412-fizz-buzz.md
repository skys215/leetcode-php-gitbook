# D40 412. Fizz Buzz

## 题目链接

[412. Fizz Buzz](https://leetcode.com/problems/fizz-buzz/)

## 题目分析

这个题目也很简单。

从1逐个输出到给定数组，但逢3输出Fizz，逢5输出Buzz，逢15输出FizzBuzz。

## 思路

没什么好说的了。用`%`整除判断能否被3、5分别整除或同时整除。然后替换要输出的内容即可。

## 最终代码

```php
<?php
class Solution {
    function fizzBuzz($n) {
        $fb = [];
        $a = range(1,$n);
        foreach($a as $val){
            if($val%3==0&&$val%5==0){
                $fb[] = 'FizzBuzz';
                continue;
            }
            if($val%3==0){
                $fb[] = 'Fizz';
                continue;
            } 
            if($val%5==0){
                $fb[] = 'Buzz';
                continue;
            }
            $fb[] = (string)$val;
        };
        return $fb;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

