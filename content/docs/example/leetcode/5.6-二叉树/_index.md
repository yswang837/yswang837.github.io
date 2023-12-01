---
weight: 1
title: 5.6 二叉树
---

&emsp;&emsp;递归函数有返回值通常认为是动态规划；而回溯算法通常是递归函数没有返回值，通过传入指针的方式来处理。

### 104.二叉树的最大深度

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#104-%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E6%9C%80%E5%A4%A7%E6%B7%B1%E5%BA%A6)

### 543.二叉树的直径

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#543-%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E7%9B%B4%E5%BE%84)

### 144.二叉树的前序遍历

[传送门](https://leetcode.cn/problems/binary-tree-preorder-traversal/description/)

```go
// 动态规划，问题分解：一棵树的前序遍历=根节点+左子树+右子树
// 定义：传递一棵树，返回该树的前序遍历
func preorderTraversal(root *TreeNode) []int {
    if root == nil {
        return nil
    }
    var ret []int
    ret = append(ret, root.Val)
    left := preorderTraversal(root.Left)
    right := preorderTraversal(root.Right)
    return append(append(ret, left...), right...)
}
```

### 175.计算二叉树的深度(剑指Offer)

[传送门](https://leetcode.cn/problems/er-cha-shu-de-shen-du-lcof/description/)

```go
 // 动态规划，问题分解，输入一棵树，返回这棵树的深度
func calculateDepth(root *TreeNode) int {
    if root == nil {
        return 0
    }
    left := calculateDepth(root.Left)
    right := calculateDepth(root.Right)
    if left >= right {
        return left + 1
    }else {
        return right + 1
    }
}
```

### 226.翻转二叉树

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#226-%E7%BF%BB%E8%BD%AC%E4%BA%8C%E5%8F%89%E6%A0%91)

### 114.二叉树展开为链表

[传送门](https://leetcode.cn/problems/flatten-binary-tree-to-linked-list/)

```go

```
