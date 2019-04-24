# D28 884. Uncommon Words from Two Sentences

## 题目链接

[884. Uncommon Words from Two Sentences](https://leetcode.com/problems/uncommon-words-from-two-sentences/)

## 题目分析

返回给定的两个句子中唯一不同的单词。

## 思路

先把两个句子分别按空格分割成数组，再计算两个数组的差集，即可得知两个句子的差异。

测试后发现没通过`apple apple`和`banana`这个测试组合。系统提示应当返回`banana`。

那么我们计算一下这个差集中单词出现的次数，只返回出现次数为1的。

因为用了array count values函数，因此键为单词，值为出现次数。

我们需要用array\_keys返回键部分即可。

## 最终代码

```php
<?php
class Solution {
    function uncommonFromSentences($A, $B) {
        $d = array_merge(array_diff(explode(' ', $A), explode(' ', $B)),array_diff(explode(' ', $B), explode(' ', $A)));
        return array_keys(array_filter(array_count_values($d),function($val){
            return $val==1;
        }));
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

