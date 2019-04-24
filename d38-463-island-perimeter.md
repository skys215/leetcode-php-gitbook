# D38 463. Island Perimeter

## 题目链接

[463. Island Perimeter](https://leetcode.com/problems/island-perimeter/)

## 题目分析

给定一个二维数组，代表一个二维表格。  
里面包含`0`和`1`两种数字。

1代表有内容，0代表没有。

计算有内容的格子的周长。

## 思路

最简单的办法是，判断当前格子是否位1，且上下左右是否为0。

当任意一个方向有0时，那个方向计算有一个边长。

当都为0时，即当前位置是单独的一个格子，算上下左右共4条边。

## 最终代码

```php
<?php
class Solution {
    function islandPerimeter($grid) {
        $edges = 0;
        $width = count($grid[0]);
        $height = count($grid);
        foreach($grid as $y=>$row){
            foreach($row as $x=>$col){
                if($col==0){
                    continue;
                }
                if(!isset($grid[$y][$x+1])||$grid[$y][$x+1]==0){
                    $edges++;
                }
                if(!isset($grid[$y][$x-1])||$grid[$y][$x-1]==0){
                    $edges++;
                }
                if(!isset($grid[$y+1][$x])||$grid[$y+1][$x]==0){
                    $edges++;
                }
                if(!isset($grid[$y-1][$x])||$grid[$y-1][$x]==0){
                    $edges++;
                }
            }
        }
        return $edges;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

