# D29 973. K Closest Points to Origin

## 题目链接

[973. K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin)

## 题目分析

给一个坐标数组`points`，从中返回`K`个离`0,0`最近的坐标。

其中，用欧几里得距离计算。

## 思路

把距离作为数组的键，把对应坐标作为数组的值。

用ksort函数排序，再用array\_slice函数获取前K个即可。

## 最终代码

```php
<?php
class Solution {
    function kClosest($points, $K) {
        $dists = [];
        foreach($points as $point){
            $dists[(string)sqrt(pow($point[0],2)+pow($point[1],2))] = $point;
        }
        ksort($dists);
        return array_slice($dists,0,$K);
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

