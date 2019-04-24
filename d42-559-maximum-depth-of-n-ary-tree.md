# D42 559. Maximum Depth of N-ary Tree

## 题目链接

[559. Maximum Depth of N-ary Tree](https://leetcode.com/problems/maximum-depth-of-n-ary-tree/)

## 题目分析

此题和上一题思路一样。只是不是二叉树。而是正常的树。

## 思路

略

## 最终代码

```php
<?php
class Solution {
    public $max = 0;
    public $level = 0;
    function maxDepth($root) {
        if($root){
            $this->level++;
            if($this->level>=$this->max){
                $this->max = $this->level;
            }
        }
        if($root->children){
            foreach($root->children as $child){
                $this->maxDepth($child);    
            }
        }
        if($root){
            $this->level--;
        }
        return $this->max;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

