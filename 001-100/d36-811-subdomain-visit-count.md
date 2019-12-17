# D36 811. Subdomain Visit Count

## 题目链接

[811. Subdomain Visit Count](https://leetcode.com/problems/subdomain-visit-count/)

## 题目分析

题目给定一个字符串数组，每个字符串分两部分，以空格分割。  
第一部分为访问次数，第二部分为域名。  
要求按同样的格式，分别返回顶级域名、二级域名、三级域名…的访问次数。

例如，字符串`"9001 discuss.leetcode.com"`。

`discuss.leetcode.com`算一个域名；

`leetcode.com`算另一个；

`com`也是一个。

因此要返回`["9001 discuss.leetcode.com", "9001 leetcode.com", "9001 com"]`

## 思路

先把域名用`explode`函数拆分，再按层级把访问次数加到每个层级去。

## 最终代码

```text
<?php
class Solution {
        function subdomainVisits($cpdomains) {
        $visits = [];
        foreach($cpdomains as $cpdomain){
            $item = explode(' ',$cpdomain);
            $domain = explode('.',$item[1]);
            $max = count($domain);
            for($i=$max-1; $i>=0;$i--){
                $d = implode('.', array_slice($domain, $i));
                if(!isset($visits[$d])){
                    $visits[$d] = 0;
                }
                $visits[$d] += $item[0];
            }
        }
        $v = [];
        foreach($visits as $domain => $visit){
            $v[] = $visit.' '.$domain;
        }
        return $v;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

