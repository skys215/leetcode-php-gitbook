# D27 620. Not Boring Movies

## 题目链接

[620. Not Boring Movies](https://leetcode.com/problems/not-boring-movies)

## 题目分析

前面铺垫了那么多，要求就在这：

> movies with an odd numbered ID and a description that is not 'boring'. Order the result by rating.

返回id为偶数、description不是boring的结果，并且按rating排序。

## 思路

返回偶数id的结果，这个比较简单，除以2去余就好了：`id%2=1`；

`description`不能是`boring`，也很简单`description not like 'boring'`；

根据`rating`排序：`order by rating`。

## 最终代码

```sql
# Write your MySQL query statement below
SELECT * FROM cinema WHERE id%2=1 AND description NOT LIKE 'boring' ORDER BY rating DESC;
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

