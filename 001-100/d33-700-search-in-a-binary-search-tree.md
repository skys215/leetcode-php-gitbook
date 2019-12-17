# D33 700. Search in a Binary Search Tree

## 题目链接

[700. Search in a Binary Search Tree](https://leetcode.com/problems/search-in-a-binary-search-tree/)

## 题目分析

从给定的二叉树中，查找指定值及其子节点。

## 思路

这个好像不用多说什么了吧…按先序遍历搜索，找到则返回。

没有则返回NULL。

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
    function searchBST($root, $val) {
        if($root->val == $val){
            return $root;
        }
        $a = NULL;
        $b = NULL;
        if($root->left){
            $a = $this->searchBST($root->left, $val);
            if($a){
                return $a;
            }
        }
        if($root->right){
            $b = $this->searchBST($root->right, $val);
            if($b){
                return $b;
            }
        }
        return NULL;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

