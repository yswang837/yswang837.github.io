---
weight: 1
title: 5.5 二叉树
---

### 104.二叉树的最大深度

[传送门](https://leetcode.cn/problems/maximum-depth-of-binary-tree/description/)

```go
// 递归划分子问题的思想，采用了后续遍历，这是动态规划的思想
// 定义：给我一棵树，我就能返回这棵树的最大深度
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

```go
// 递归地遍历一遍树(并未划分子问题)，得到问题答案，这是回溯算法的思想
// 定义这个结构体就是为了避免将res和depth定义为全局遍历(全局变量会让两个测试用例的结果相互影响)
type record struct {
	res   int
	depth int
}

func maxDepth(root *TreeNode) int {
	r := &record{}
	traverse(root, r)
	return r.res
}

func traverse(root *TreeNode, r *record) {
	if root == nil {
		return
	}
	r.depth++
	if root.Left == nil && root.Right == nil {
		r.res = maxA(r.res, r.depth)
	}
	traverse(root.Left, r)
	traverse(root.Right, r)
	r.depth--
}

func maxA(i, j int) int {
	if i > j {
		return i
	}
	return j
}
```
