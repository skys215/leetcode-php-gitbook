# D32 617. Merge Two Binary Trees

## 题目链接

[617. Merge Two Binary Trees](https://leetcode.com/problems/merge-two-binary-trees/)

## 题目分析

给定两个二叉树，返回一个 将对应位置值相加后的二叉树。

例如，树A的顶点值为1，树B的顶点值为2，那么返回的二叉树的顶点值需要是3。

## 思路

顶点自然不用多说，直接相加就可以了。

按照习惯，先遍历左节点。如果树A和树B都有左节点，那么直接相加，再递归当前函数去判断左节点的左节点。

若树A和树B任意一棵树没有左节点时，直接把有左节点迁移过来即可。  
因为，如果没有左节点，不可能会有左节点的左节点，或左节点的右节点。  
因此，直接照搬过来就可以了。

若两颗树都没有左节点时，忽略，直接去算右节点，并遵从以上规则即可。

## 最终代码

```text
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
    function mergeTrees($t1, $t2) {
        if(is_null($t1->val)&&is_null($t2->val)){
            return;
        }
        $t1->val += $t2->val;
        if($t1->left&&$t2->left){
            $this->mergeTrees($t1->left, $t2->left);
        }
        if(!$t1->left&$t2->left){
            $t1->left = $t2->left;
        }
        if($t1->right && $t2->right){
            $this->mergeTrees($t1->right, $t2->right);
        }
        if(!$t1->right&&$t2->right){
            $t1->right = $t2->right;
        }
        return $t1;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

