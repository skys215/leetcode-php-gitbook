# D9 657. Robot Return to Origin

## 题目链接

[657. Robot Return to Origin](https://leetcode.com/problems/robot-return-to-origin/)

## 题目分析

输入一串指令操作机器人，判断执行完指令后，能否回到原点。

## 思路

判断向上移动的次数是否等于向下移动的次数，且向左次数是否等于向右次数。

先用`array_count_values`计算元素个数。  
再直接`U`个数和`D`个数是否相等，`L`个数和`R`个数是否相等即可。

但是，如果在指令中没有出现所有4种方向的话，在判断时会获取不到数值。  
因此还要和给定默认的UDLR出现次数。用`array_merge`即可。

## 最终代码

```php
<?php
class Solution {
    function judgeCircle($moves) {
        $moves = array_count_values(str_split($moves));
        $moves = array_merge(['U'=>0,'L'=>0,'R'=>0,'D'=>0],$moves);
        return ($moves['U']==$moves['D'])&&($moves['L']==$moves['R']);
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

