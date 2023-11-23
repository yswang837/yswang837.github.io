---
weight: 1
title: 5.5 二叉树
---

### 104.二叉树的最大深度

[传送门](https://leetcode.cn/problems/maximum-depth-of-binary-tree/description/)

```go
// 递归划分子问题的思想，采用了后续遍历，这是动态规划的思想，未借助额外的遍历函数，充分利用函数maxDepth本身返回的值。
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
// 递归地遍历一遍树(并未划分子问题)，得到问题答案，这是回溯算法的思想，借助了traverse函数，记录了额外的遍历值，如res和depth，不需要有返回值，给该函数传递指针就行
func maxDepth(root *TreeNode) int {
	res, depth := 0, 0
	traverse(root, &res, &depth)
	return res
}

func traverse(root *TreeNode, res, depth *int) {
	if root == nil {
		return
	}
	*depth++
	if root.Left == nil && root.Right == nil {
		*res = maxInt(*res, *depth)
	}
	traverse(root.Left, res, depth)
	traverse(root.Right, res, depth)
	*depth--
}

func maxInt(i, j int) int {
	if i >= j {
		return i
	}
	return j
}
```

### 543.二叉树的直径

[传送门](https://leetcode.cn/problems/diameter-of-binary-tree/description/)

```go
// 动态规划算法，需要通过maxDepth函数求出子树的最大深度，需要返回值。遇到子树问题，首先想到的是给函数设置返回值，然后在后序位置做文章。
// 问题分解：一棵树的直径 = max(左子树的最大深度+右子树的最大深度)
func diameterOfBinaryTree(root *TreeNode) int {
    maxDiameter := 0 
    maxDepth(root, &maxDiameter)
    return maxDiameter
}

func maxDepth(root *TreeNode, maxDiameter *int) int {
    if root == nil {
        return 0
    }
    leftDepth := maxDepth(root.Left, maxDiameter)
    rightDepth := maxDepth(root.Right, maxDiameter)
    curDepth := leftDepth + rightDepth
    if curDepth > *maxDiameter {
        *maxDiameter = curDepth
    }
    if leftDepth >= rightDepth {
        return leftDepth + 1
    }else {
        return rightDepth + 1
    }
}
```

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

[传送门](https://leetcode.cn/problems/invert-binary-tree/description/)

```go
// 动态规划，充分利用遍历函数invertTree的返回值
func invertTree(root *TreeNode) *TreeNode {
    if root == nil {
        return nil
    }
    left := invertTree(root.Left)
    right := invertTree(root.Right)
    root.Left = right
    root.Right = left
    return root
}
```

### 144.翻转二叉树(剑指Offer)

[传送门](https://leetcode.cn/problems/er-cha-shu-de-jing-xiang-lcof/description/)

```go
// 回溯算法，定义无返回值的traverse
func mirrorTree(root *TreeNode) *TreeNode {
    if root == nil {
        return nil
    }
    traverse(root)
    return root
}
func traverse(root *TreeNode) {
    if root == nil {
        return 
    }
    root.Left, root.Right = root.Right, root.Left
    traverse(root.Left)
    traverse(root.Right)

    return 
}
```

