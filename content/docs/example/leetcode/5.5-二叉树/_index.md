---
weight: 1
title: 5.5 二叉树
---

### 104.二叉树的最大深度

[传送门](https://leetcode.cn/problems/maximum-depth-of-binary-tree/description/)

```go
func maxDepth(root *TreeNode) int {
    if root == nil {
        return 0
    }
    left := maxDepth(root.Left)
    right := maxDepth(root.Right)
    if left >= right {
        return left + 1
    }else {
        return right + 1
    }
}
```
