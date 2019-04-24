# D6 595. Big Countries

## 595. Big Countries

## 题目链接

[595. Big Countries](https://leetcode.com/problems/big-countries/)

## 题目分析

这道题是个SQL题。

要求返回国土面积大于300万平方公里或者人口多于2500万人的国家的名称、人口、面积。

## 思路

国土面积大于300万平方公里：`area>3000000`

人口多于2500万人：`population>25000000`

返回名称、人口、面积：`select name, population, area`

## 最终代码

```sql
# Write your MySQL query statement below
select name, population,area from world
where area>3000000 or population>25000000;
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

