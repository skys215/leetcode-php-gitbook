# D41 104. Maximum Depth of Binary Tree

## 题目链接

[104. Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree)

## 题目分析

返回给定的二叉树有多少层。

## 思路

每下一级，层树+1，并记录到类属性level中。并判断是否大于已知最深层树。

## 最终代码

```php
<?php
/**
 * Definition for a binary tree node.
 * class TreeNode {
 *     public $val = null;
 *     public $left = null;
 *     public $right = null;
 *     function __construct($value) { $this->val = $value; }
 * }
 */
class Solution {
    public $max = 0;
    public $level = 0;
    /**
     * @param TreeNode $root
     * @return Integer
     */
    function maxDepth($root) {
        if($root){
            $this->level++;
        }
        if($this->level>=$this->max){
            $this->max = $this->level;
        }
        if($root->left){
            $this->maxDepth($root->left);
        }
        if($root->right){
            $this->maxDepth($root->right);
        }
        $this->level--;
        return $this->max;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

