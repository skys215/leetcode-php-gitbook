# D4 961. N-Repeated Element in Size 2N Array

## 961. N-Repeated Element in Size 2N Array

## 题目链接

[961. N-Repeated Element in Size 2N Array](https://leetcode.com/problems/n-repeated-element-in-size-2n-array/)

### 题目分析

在长度为`2N`的数组`A`中，有`N+1`个元素。其中恰好有一个元素重复了`N`遍。\
返回这个元素。

一般算法题用数学上的定义方法去描述问题，所以理解起来可能费劲一些。

我们来简化一下问题：

返回数组A中重复了N遍的元素。\
\=> 返回数组A中出现了N次的元素。\
其中，数字N为数组A的长度的一半。

这就好理解了吧？

### 思路

输入：

* 数组A

需要：

* 数字N\
  数字N的求法：数组A的长度除以2。
* 求元素出现次数\
  `array_count_values`函数。

输出：

* 用`array_search`函数，从`array_count_values`函数的返回中，查找数字N。

### 最终代码

```php
<?php
class Solution {
    function repeatedNTimes($A) {
        $countValues = array_count_values($A);
        $N = count($A)/2;
        return array_search($N,$countValues);
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。
