---
weight: 1
title: 5.3 前缀和数组
---

&emsp;&emsp;前缀和技巧适用于快速、频繁地计算一个索引区间内的元素之和。

### 303.区域和检索 - 数组不可变

[传送门](https://leetcode.cn/problems/range-sum-query-immutable/description/)

```go
type NumArray struct {
    preSum []int
}

// 在构造函数里面一次O(N)时间复杂度的初始化，之后每次调用SumRange都是O(1)的时间复杂度。
func Constructor(nums []int) NumArray {
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
