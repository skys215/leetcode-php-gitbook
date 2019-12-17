# D19 867. Transpose Matrix

## 题目链接

[867. Transpose Matrix](https://leetcode.com/problems/transpose-matrix/)

## 题目分析

这个题目比较简单，就是矩阵转置。

就是把第0行变成第0列，第1行变成第1列。

## 思路

用`array_column`方法获取每一列，塞入数组末尾作为一行即可。

## 最终代码

```php
<?php
class Solution {
    function transpose($A) {
        $t = [];
        foreach($A[0] as $key => $val){
            $t[] = array_column($A,$key);
        }
        return $t;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

