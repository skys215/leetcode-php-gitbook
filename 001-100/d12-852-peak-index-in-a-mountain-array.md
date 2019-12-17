# D12 852. Peak Index in a Mountain Array

## 题目链接

[852. Peak Index in a Mountain Array](https://leetcode.com/problems/peak-index-in-a-mountain-array/)

## 题目分析

这个题目比较简单。要求返回数组中最大值的索引。

## 思路

先用`max`找到最大值，再用`array_keys`获取最大值的索引。

## 最终代码

```php
<?php
class Solution {
    function peakIndexInMountainArray($A) {
        $maxValue = max($A);
        $maxIndex = array_keys($A,$maxValue);
        return $maxIndex[0];
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

