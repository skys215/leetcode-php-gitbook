# D1 771. Jewels and Stones

由于是按难易度排序的，因此本题是第一题。

## 题目链接

[771. Jewels and Stones](https://leetcode.com/problems/jewels-and-stones/)

## 题目分析

从第二个参数`S`中找第一个参数`J` 中出现的字符，返回找到的字符个数。

也就是说，第一个参数`J`是一个需要找的字符的列表。只是拼接成字符串了。  
而第二个参数`S`是被查找的字符串。  
简单地说就是要在`S`里找`J`。

先把问题简化为`J`中只有一个字符的情形，因为字符串可以看作是一个字符数组。  
首先想到的是用[array\_filter](http://php.net/manual/en/function.array-filter.php)。可能很多人没听说过这个函数。  
这个函数的作用就是，根据闭包函数，过滤数组元素。  
简单地说就是删除不需要的元素。

要注意`$S`是字符串，需要先转换成数组才行。  
我们可以写出这样的代码：

```php
$values = array_filter(str_split($S), function($val) use ($J){
    return $val == $J;
});
```

此时再延伸一下判断条件：

```php
$values = array_filter(str_split($S),function($var) use ($J){
    if(in_array($var, str_split($J))){
        return $var;
    }
});
```

最后返回`count($values)`即可。

## 最终代码

```php
<?php
class Solution {
    function numJewelsInStones($J, $S) {
        $keys = array_filter(str_split($S),function($var) use ($J){
            if(in_array($var,str_split($J))){
                return $var;
            }
        });
        return count($keys);
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

