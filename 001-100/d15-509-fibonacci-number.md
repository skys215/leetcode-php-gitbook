# D15 509. Fibonacci Number

## 题目链接

[509. Fibonacci Number](https://leetcode.com/problems/fibonacci-number/)

## 题目分析

斐波那契数列应该不用我多说了吧？  
是个经典的递归问题。

递归有两个条件。  
一个是终止条件。要不然会无限递归下去。  
另一个是自己调自己。这才叫递归。

## 思路

因为该数列中，当前数字为前两项之和，所以要计算前一项的“前两项之和”和前前一项的“前两项之和”。

但，当当前为第1项或第2项时，没有前一项或前前一项。此时第1项返回0，第2项返回1即可。

## 最终代码

```php
<?php
class Solution {
    function fib($N) {
        if($N == 0){
            return 0;
        }
        if($N == 1){
            return 1;
        }
        return $this->fib($N-1) + $this->fib($N-2);
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

