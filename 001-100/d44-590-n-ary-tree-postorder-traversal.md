# D44 590. N-ary Tree Postorder Traversal

## 题目链接

[590. N-ary Tree Postorder Traversal](https://leetcode.com/problems/n-ary-tree-postorder-traversal/)

## 题目分析

后序遍历，这题也是比较基础的题目了。

## 思路

先遍历子节点，再遍历根节点。

## 最终代码

```text
<?php
/*
// Definition for a Node.
class Node {
    public $val;
    public $children;

    @param Integer $val 
    @param list<Node> $children 
    function __construct($val, $children) {
        $this->val = $val;
        $this->children = $children;
    }
}
*/
class Solution {
    public $val = [];
    /**
     * @param Node $root
     * @return Integer[]
     */
    function postorder($root) {
        if(!$root){
            return $this->val;
        }
        foreach($root->children as $child){
            $this->postorder($child);
        }
        $this->val[] = $root->val;
        return $this->val;
    }
}
```

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

