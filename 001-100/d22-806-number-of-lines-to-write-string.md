# D22 806. Number of Lines To Write String

## 题目链接

[806. Number of Lines To Write String](https://github.com/skys215/leetcode-php/commit/584e609b6be14ca5212e4ac682a875762c1532f3)

## 题目分析

每行只能容纳100个字符，给定每个字符所占宽度；

计算给定的字符串需要占多少行，最后一行占多少个字符。

## 思路

首先第一行，直接添加即可。  
当到达100时，当前单词要写到下一行。那么行数增加，当且单词长度直接作为下一行的末尾坐标。

返回行数和最后一行的末尾坐标即可。

## 最终代码

```php
<?php
class Solution {
    function numberOfLines($widths, $S) {
        $S = str_split($S);
        $rows = 1;
        $cols = 0;
        foreach($S as $s){
            $width = $widths[ord($s)-ord('a')];
            $cols += $width;
            if($cols>100){
                $rows++;
                $cols = $width;
            }
        }
        return [$rows,$cols];
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

