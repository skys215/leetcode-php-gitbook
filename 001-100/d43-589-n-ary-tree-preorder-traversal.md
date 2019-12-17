# D43 589. N-ary Tree Preorder Traversal

## 题目链接

[589. N-ary Tree Preorder Traversal](https://leetcode.com/problems/n-ary-tree-preorder-traversal/)

## 题目分析

N维数组的先序遍历。

这题也不想多说什么了。是比较基础的题目了。

先序就是先根后子而已。没什么难的。

## 思路

在遍历子节点之前，先保存当前节点的信息。

## 最终代码

```text
<?php
class Solution {
    public $val = [];
    function preorder($root) {
        if(!$root){
            return $this->val;
        }
        $this->val[] = $root->val;
        foreach($root->children as $child){
            $this->preorder($child);
        }
        return $this->val;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

