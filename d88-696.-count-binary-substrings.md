# D88 696. Count Binary Substrings

## 题目链接

[696. Count Binary Substrings](https://leetcode.com/problems/count-binary-substrings/)

## 题目分析

给定一个01字符串，返回仅用连续的0和1串所能组成的二进制字符串个数。

例如，`00110011`，就包含`0011`，`01`，`1100`，`10`，`0011`，`01`共6个。`001100`则不算，因为两个00被11分割开了，不是连续的。

## 思路

#### 思路1:

生成01，0011，000111和10，1100，111000字符串，再用substr\_count函数去计算个数的。但是会超时。

```php
function countBinarySubstrings($s) {
    $totalLength = strlen($s);
    $total = 0;
    for($i=0;$i<=$totalLength/2; $i++){
        //01 0011 000111
        $boz = str_repeat('0',$i).str_repeat('1',$i);
        //10 1100 111000
        $bzo = strrev($boz);
        $total += substr_count($s, $boz);
        $total += substr_count($s, $bzo);
    }
    return $total;
}
```



#### 思路2

用栈的思想。先把数字压入栈内，遇到不同数字时出栈。出完栈时，把后面出现的数字顶上，作为下一个出栈的栈。然而写起来略嫌麻烦。写了个Wrong Answer出来就放弃了。于是又换了个思路。



#### 思路3

只记录前一组是0还是1，以及出现的次数。

先取字符串的第一个字符作为第一组的字符。  
从第二个字符开始判断。  
判断是否与第一组出现的字符相同。相同，则判断是否与前一个字符相同。这里需要注意的是，前一组的字符不一定等于前一个字符。所以需要分开判断。  
如果与前一个字符相同，则给前一组字符出现个数（或者叫长度）+1。如果与前一个字符不同，则说明两个相同的字符夹住了不同的字符（例如010或者101）。那么此时需要抛弃前一组的所有内容。因为前一组已经没有内容可以和下一组匹配了。所以需要把当前组作为前一组，把当前字符作为下一组。

如果当前字符与前一组的字符不同，则说明配对成功。  
前一组未配对字符数量减1，当前组未配对数量+1。这里是因为，当前在变成前一组的时候，会与其后面的字符匹配，到时候会减去对应数量。因此这里需要+1。

当前一组未配对字符数量达到0时，说明前一组已经没有可以匹配的字符。故把当前组替换未前一组。

如此循环即可。

## 最终代码

```php
<?php
class Solution {
    /**
     * @param String $s
     * @return Integer
     */
    function countBinarySubstrings($s) {
        $total = 0;
        $s = str_split($s);
        $stack1 = array_shift($s);
        $stack1Amount = 1;
        $stack2 = null;
        $stack2Amount = 0;
        $prev = $stack1;
        foreach($s as $key => $val){
            if($stack1 == $val){
                if($val == $prev){
                    $stack1Amount++;
                }
                else{
                    $stack1 = $stack2;
                    $stack1Amount = $stack2Amount;
                    $stack2Amount = 0;
                    $stack2 = null;
                }
            }
            if($stack1 != $val){
                $stack2 = $val;
                $stack2Amount++;
                $stack1Amount--;
                $total++;
            }
            if($stack1Amount == 0){
                $stack1 = $stack2;
                $stack1Amount = $stack2Amount;
                $stack2 = null;
                $stack2Amount = 0;
            }
            $prev = $val;
        }
        return $total;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

