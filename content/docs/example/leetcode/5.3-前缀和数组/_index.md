---
weight: 1
title: 5.3 前缀和数组
---

&emsp;&emsp;前缀和技巧适用于快速、频繁地计算一个索引区间内的元素之和。

### 303.区域和检索 - 数组不可变

[传送门](https://leetcode.cn/problems/range-sum-query-immutable/description/)

```go
type NumArray struct {
    preSum []int //该数组当前值=nums当前值的下标及之前的所有元素的和
}

// 在构造函数里面一次O(N)时间复杂度的初始化，之后每次调用SumRange都是O(1)的时间复杂度。
func Constructor(nums []int) NumArray {
    if len(nums) == 0 {
        return NumArray{}
    }
    preSum := make([]int, len(nums)+1)
    for i:=1; i<=len(nums); i++ {
        preSum[i] = preSum[i-1] + nums[i-1]
    }
    return NumArray{preSum: preSum}
}

func (this *NumArray) SumRange(left int, right int) int {
    return this.preSum[right+1] - this.preSum[left]
}
```

### 304.二维区域和检索 - 矩阵不可变

[传送门](https://leetcode.cn/problems/range-sum-query-2d-immutable/description/)

```go
type NumMatrix struct {
    preSum [][]int // preSum[i][j] 记录 matrix 中子矩阵 [0, 0, i-1, j-1] 的元素和，就可以用几次加减运算算出任何一个子矩阵的元素和。
}


func Constructor(matrix [][]int) NumMatrix {
    m, n := len(matrix), len(matrix[0])
    if m == 0 || n == 0 {
        return NumMatrix{}
    }

    preSum := make([][]int, m+1)
    for i:=0; i<=m; i++ {
        preSum[i] = make([]int, n+1)
    }
    for i:=1; i<=m; i++ {
        for j:=1; j<=n; j++ {
            preSum[i][j] = preSum[i-1][j] + preSum[i][j-1] + matrix[i-1][j-1] - preSum[i-1][j-1]
        }
    }
    return NumMatrix{preSum: preSum}
}


func (this *NumMatrix) SumRegion(row1 int, col1 int, row2 int, col2 int) int {
    return this.preSum[row2+1][col2+1] - this.preSum[row1][col2+1] - this.preSum[row2+1][col1] + this.preSum[row1][col1]
}
```
