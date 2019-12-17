# D37 682. Baseball Game

## 题目链接

[682. Baseball Game](https://leetcode.com/problems/baseball-game/)

## 题目分析

给定一个字符串数组，每一个字符串有以下形式：

* 数字。直接计算得分。
* `+`。代表本轮分数为上一轮和上上一轮分数之和。
* `D`。代表本轮分数为上一轮分数的两倍。
* `C`。代表上一轮分数无效。

返回最终得分。

## 思路

这题没什么好说的了。用switch...case区分各种情况，进行相应处理即可。

## 最终代码

```php
<?php
class Solution {
    function calPoints($ops) {
        $points = [];
        foreach($ops as $op){
            $max = count($points);
            switch($op){
                case '+':
                    $p = 0;
                    if(isset($points[$max-1])){
                        $p += $points[$max-1];
                    }
                    if(isset($points[$max-2])){
                        $p += $points[$max-2];
                    }
                    $points[] = $p;
                    break;
                case 'D':
                    $points[] = isset($points[$max-1])?$points[$max-1]*2:0;
                    break;
                case 'C':
                    array_pop($points);
                    break;
                default:
                    $points[] = (int)$op;
                    break;
            }
        }
        return array_sum($points);
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

