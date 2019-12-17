# D31 965. Univalued Binary Tree

## 题目链接

[965. Univalued Binary Tree](https://leetcode.com/problems/univalued-binary-tree/)

## 题目分析

如果二叉树中所有节点的值都相同，那么该二叉树被称为单值二叉树。

当给定的二叉树是单值二叉树时返回`true`，否则返回`false`。

## 思路

思路比较简单，把值存入全局变量数组中，再对数组的值去重。判断该数组长度是否为1即可。

## 最终代码

```php
<?php
/*
//Definition for a binary tree node.
class TreeNode {
    public $val = null;
    public $left = null;
    public $right = null;
    function __construct($value) { $this->val = $value; }
}
*/
class Solution {
    private $vals = [];
    function isUnivalTree($root) {
        $this->getVal($root);
        return count(array_count_values(array_filter($this->val,function($v){
            return !is_null($v);
        })))==1;
    }

    function getVal($root){
        $this->val[] = $root->val;
        if($root->left){
            $this->getVal($root->left);
        }
        if($root->right){
            $this->getVal($root->right);
        }
    }
}
```

## 优化方案

把值作为数组的键则可以省去去重步骤。

在存入之前就可以判断值是否与前面的值相同。若不同则直接退出即可。

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

