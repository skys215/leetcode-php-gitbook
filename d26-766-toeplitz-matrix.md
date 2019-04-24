# D26 766. Toeplitz Matrix

## 题目链接

[766. Toeplitz Matrix](https://leetcode.com/problems/toeplitz-matrix/)

## 题目分析

拓普利兹矩阵，应该不用多说了。

要求自己的右下和左上元素值相等。

## 思路

拿当前行的前0~n-1位，与下一行的1~n位对比即可。

把二维数组降维为一维，再取当前行的头n位和下一行的头n位（去掉第一个元素，因为在下一行会比较它）比较即可。

用这个方法会重复较多值，有优化空间。

## 最终代码

```php
<?php
class Solution {
    function isToeplitzMatrix($matrix) {
        $indicies = array_reduce(array_reverse($matrix), 'array_merge', []);
        $cols = count($matrix[0]);
        $rows = count($matrix);
        if($rows == 1 ){ 
            return true;
        }
        foreach(range(0,$rows-2) as $val){
            $left = array_slice($indicies, $val*$cols+1, $cols-1);
            $right = array_slice($indicies,($val+1)*$cols,$cols-1);
            if(implode($left)!=implode($right)){
                return false;
            }
        }
        return true;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

