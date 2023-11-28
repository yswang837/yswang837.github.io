---
weight: 1
title: 5.4 差分数组
---

&emsp;&emsp;差分数组的主要适用场景是频繁对原始数组的某个区间的元素进行增减。

### 1094.拼车

[传送门](https://leetcode.cn/problems/car-pooling/description/)

```go
type Difference struct {
    diff []int
}

func NewDifference(nums []int) *Difference {
    diff := make([]int, len(nums))
    diff[0] = nums[0]
    for i:=1; i<len(nums); i++ {
        diff[i] = nums[i] - nums[i-1]
    }
    return &Difference{diff: diff}
}

func (d *Difference) Increment(i, j, val int) {
    d.diff[i] += val
    if j+1 < len(d.diff) {
        d.diff[j+1] -= val
    }
}

func (d *Difference) Result() []int {
    res := make([]int, len(d.diff))
    res[0] = d.diff[0]
    for i:=1; i<len(d.diff); i++ {
        res[i] = res[i-1] + d.diff[i]
    }
    return res
}

func carPooling(trips [][]int, capacity int) bool {
    nums := make([]int, 1001)
    df := NewDifference(nums)
    for _, trip := range trips {
        val := trip[0]
        i := trip[1]
        j := trip[2] - 1
        df.Increment(i, j, val)
    }
    res := df.Result()
    for i := 0; i < len(res); i++ {
        for capacity < res[i] {
            return false
        }
    }
    return true
}


```

### 1109.航班预定统计

[传送门](https://leetcode.cn/problems/corporate-flight-bookings/)

```go

```
