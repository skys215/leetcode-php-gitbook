# D13 627. Swap Salary

## 题目链接

[627. Swap Salary](https://leetcode.com/problems/swap-salary/)

## 题目分析

本题是一个SQL题。

题目要求对调用户性别。

## 思路

用`CASE...WHEN...THEN...ELSE...END`即可。

## 最终代码

```sql
# Write your MySQL query statement below
UPDATE salary SET sex=(CASE sex WHEN 'm' THEN 'f' ELSE 'm' END);
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

