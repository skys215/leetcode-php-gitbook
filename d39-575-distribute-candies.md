# D39 575. Distribute Candies

## 题目链接

[575. Distribute Candies](https://leetcode.com/problems/distribute-candies)

## 题目分析

给定一个偶数长度的数组，不同数字代表不同类型的糖果。

这一把糖果需要均分给两个人。计算最多能拿到多少种糖果。

## 思路

最极端的情况，每一个都是不同的糖果。那么可以获得\(数组长度除以2\)种糖果。

若只有一种不同的糖果，那么最多能获得2种。此时，数组内不同元素的个数。

因此，只要从数组长度的一半和不同元素个数之间取最小值就好了。

## 最终代码

```php
<?php
class Solution {
    function distributeCandies($candies) {
        return min(count(array_unique($candies)),count($candies)/2);
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

