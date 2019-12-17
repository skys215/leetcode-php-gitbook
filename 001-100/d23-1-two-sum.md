# D23 1. Two Sum

## 题目链接

[1. Two Sum](https://leetcode.com/problems/two-sum/)

## 题目分析

给一个数组`A`和一个数字`n`，从数组中找到两个数字，这两个数字相加之后等于`n`。

## 思路

这个只有用蛮力法了吧。

先拿第一个数组作为加数1，然后逐个相加，判断是否等于`n`。  
相等的话可以直接返回。

## 最终代码

```text
<?php
class Solution {
    function twoSum($nums, $target) {
        foreach($nums as $key => $num){
            for($i = $key+1; $i<count($nums);$i++){
                if($nums[$key]+$nums[$i] == $target){
                    return [$key, $i];
                }
            }
        }
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

