# D5 804. Unique Morse Code Words

## 题目链接

[804. Unique Morse Code Words](https://leetcode.com/problems/unique-morse-code-words/)

## 题目分析

这个题目要求算出把给定数组中的字符串转换成摩尔斯码后，有多少个不同的摩尔斯码。

## 思路

第一步需要把字符串转换成摩尔斯码。

```php
$morse = [
    ".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--",
    "-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."
];
$replaced = [];
foreach($words as $word){
    $chars = str_split($word);
    $string = '';
    foreach($chars as $char){
        $string .= $morse[ord($char)-ord('a')];
    }
}
```

转换完成后存进数组内，再用array\_unique函数排除。再count排除结果即可。

## 最终代码

```php
<?php
class Solution {
    function uniqueMorseRepresentations($words) {
        $morse = [".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."];
        $replaced = [];
        foreach($words as $word){
            $chars = str_split($word);
            $string = '';
            foreach($chars as $char){
                $string .= $morse[ord($char)-ord('a')];
            }
            $replaced[] = $string;
        }
        return count(array_unique($replaced));
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

## 优化方案

* 直接存为数组的键则可以省去用array\_unique去重的步骤。

