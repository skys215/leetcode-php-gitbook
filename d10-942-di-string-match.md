# D10 942. DI String Match

## 题目链接

[942. DI String Match](https://leetcode.com/problems/di-string-match/)

## 题目分析

给定一个只含`I`和`D`的字符串`S`，返回一个数组。  
这个数组满足以下条件：  
当`S[i]`为`I`时，`A[i]<A[i+1]`。既后面的数字比前面的大。  
当`S[i]`为`D`时，`A[i]>A[i+1]`。既前面的数字比后面的大。

## 思路

循环遍历给定的字符串，  
当遇到`I`时，直接在数组后面塞当前字母的下标。  
当遇到`D`时，在数组的当前下标位置前插入当前下标。

## 最终代码

```php
<?php
class Solution {
    function diStringMatch($S) {
        $S = str_split($S);
        $n = range(0,count($S));
        $nums = [array_shift($n)];
        $currentPosition = 0;
        foreach($S as $s){
            if($s == 'I'){
                $nums[] = array_shift($n);
            }
            else{
                $left = ($currentPosition>=0 ?array_slice($nums,0,$currentPosition):[]);
                $right = ($currentPosition<count($nums)?array_slice($nums,$currentPosition):[]);
                $middle = [array_pop($n)];
                $nums = array_merge($left,$middle,$right);
            }
            $currentPosition++;
        }
       return $nums;
    }
}
```

个人认为这题不是很好描述。有空会尝试描述清楚这个问题。

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

