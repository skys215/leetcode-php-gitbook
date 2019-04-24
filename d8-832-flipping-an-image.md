# D8 832. Flipping an Image

## 题目链接

[832. Flipping an Image](https://leetcode.com/problems/flipping-an-image/)

## 题目分析

题目要求把一个只有0和1的二维数组中的0和1取反变为1和0。即1变0，0变1。

且需要把每行数据倒序过来。

## 思路

今天我尝试换一种方法描述思路。

输入是一个二维数组，那么我们需要先降为一维。这个可以用`foreach`完成。

接下来需要完成替换。我本来想用取反操作符完成的，但是如果开头为1的话，需要补0。

我懒得补0，所以我用`implode`先转换成字符串了。

```php
str_replace(['0','1','2'],['2','0','1'],implode('',$row));
```

这里我先把0换成2，1换成0，再把2换成1的。

如果直接把0替换成1，1替换成0的话，最后会全0。因为他是先完成第一个替换对，再重新遍历字符串替换第二个替换对的。

再用`str_split`把字符串变会数组。

最后，用`array_reverse`把数组顺序倒转过来即可。

当然，也可以先用`strrev`先反转字符串，再`str_split`。

这样就完成了每一行的处理。

## 最终代码

```php
<?php
class Solution {
    function flipAndInvertImage($A) {
        $flipped = [];
        foreach($A as $row){
            $flipped[] = array_reverse(str_split(str_replace(['0','1','2'],['2','0','1'],implode('',$row))));
        }
        return $flipped;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

