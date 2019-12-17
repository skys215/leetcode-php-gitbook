# D30 728. Self Dividing Numbers

## 题目链接

[728. Self Dividing Numbers](https://leetcode.com/problems/self-dividing-numbers/)

## 题目分析

如果一个数字能被其中的每一位整除，那么这个数字被称为自整除数。

例如，数字`128`。`128%1==0`、`128%2==0`、`128%8==0`。均能整除。

自整除数不能包含数字0（毕竟0不能作为被除数）。

## 思路

首先，小于10的数都能被每一位整除。因为只有1位，自己能整除自己。

大于10的就用str\_split拆分每一位数字，再逐个尝试整除。

若在遍历每一位数字时，遇到0，则直接跳过当前数字。

若不能整除，也跳过当前数字。

能整除的数字就直接存入一个数组当中，用于返回。

## 最终代码

```php
<?php
class Solution {
    function selfDividingNumbers($left, $right) {
        $nums = range($left,$right+1);
        $result = [];
        foreach($nums as $num){
            if($num<10){
                $result[] = $num;
                continue;
            }
            if($num%10 == 0){
                continue;
            }
            $ds = array_unique(str_split($num));
            $stopFlag = false;
            foreach($ds as $d){
                if($d == 0){
                    $stopFlag = true;
                    break;
                }
                if($num%$d!=0){
                    $stopFlag = true;
                    break;
                }
            }
            if(!$stopFlag){
                $result[] = $num;
            }
        }
        return $result;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

