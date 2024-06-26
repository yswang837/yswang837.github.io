---
weight: 1
title: 5.2 双指针秒杀数组问题
---

## 双指针秒杀数组问题

&emsp;&emsp;在数组中，下标就可以认为是指针。双指针主要分为：左右指针，快慢指针。

&emsp;&emsp;左右指针：从数组的两个端点向中间移动，比如说二分查找及其相关的变种题；从字符串中间向两边移动，如最长回文子串。

&emsp;&emsp;快慢指针：都从数组的起点开始，快指针负责探路，慢指针跟快指针配合完成题目要求，比如说去掉有序数组的重复元素，并返回新数组长度。

&emsp;&emsp;没有序号的，不是leetcode题目，例题如下：

### 例：二分查找

&emsp;&emsp;二分查找是典型的左右指针，针对的场景是一切有序数组，时间复杂度为O(logN)。

```go
func binarySearch(nums []int, target int) int {
	if len(nums) == 0 {
		return -1
	}
	left, middle, right := 0, 0, len(nums)-1
	for left <= right {
		middle = (left + right) / 2
		if nums[middle] == target {
			return middle
		} else if nums[middle] > target {
			right = middle - 1
		} else {
			left = middle + 1
		}
	}
	return -2
}
```

### 26.删除有序数组中的重复项

[传送门](https://leetcode.cn/problems/remove-duplicates-from-sorted-array/)

```go
func removeDuplicates(nums []int) int {
    if len(nums) == 0 {
        return 0
    }
    slow, fast := 0, 0
    for fast < len(nums) {
        if nums[slow] == nums[fast] {
            fast++
        }else {
            slow++
            nums[slow] = nums[fast]
        }
    }
    return slow+1
}
//                    f
// [0,0,1,1,1,2,2,3,3,4]
//          s
// [0,1,1,1,1,2,2,3,3,4]
// [0,1,2,1,1,2,2,3,3,4]
// [0,1,2,3,1,2,2,3,3,4]
// [0,1,2,3,4,2,2,3,3,4]
```

### 167.两数之和 II - 输入有序数组

[传送门](https://leetcode.cn/problems/two-sum-ii-input-array-is-sorted/)

```go
func twoSum(numbers []int, target int) []int {
    if len(numbers) == 0 {
        return numbers
    }
    left, right := 0, len(numbers) - 1
    sum := 0
    for left <= right {
        sum = numbers[left] + numbers[right]
        if sum == target {
            return []int{left+1,right+1}
        }else if sum > target {
            right--
        }else {
            left++
        }
    }
    return []int{-1,-1}
}
```

### 27.移除元素

[传送门](https://leetcode.com/problems/remove-element/)

```go
func removeElement(nums []int, val int) int {
    if len(nums) == 0 {
        return -1
    }
    slow, fast := 0, 0
    for fast < len(nums) {
        if nums[fast] != var {
            nums[slow] = nums[fast]
            slow++
        }
        fast++
    }
}
//            f
//        s
// [0,1,2,2,3,0,4,2] 2

// [0,1,2,2,3,0,4,2] 2
// [0,1,3,2,3,0,4,2] 2
// [0,1,3,0,3,0,4,2] 2

```

### 283.移动零

[传送门](http://localhost:1313/docs/example/leetcode/5.1-hot100/#283%E7%A7%BB%E5%8A%A8%E9%9B%B6)

### 344.反转字符串

&emsp;&emsp;反转数组一个意思。[传送门](https://leetcode.cn/problems/reverse-string/)

```go
func reverseString(s []byte)  {
    if len(s) == 0 {
        return
    }
    left, right := 0, len(s) - 1
    for left <= right {
        s[left], s[right] = s[right], s[left]
        left++
        right--
    }
    return
}
```

### 5.最长回文子串

[传送门](http://localhost:1313/docs/example/leetcode/5.1-hot100/#5-%E6%9C%80%E9%95%BF%E5%9B%9E%E6%96%87%E5%AD%90%E4%B8%B2)

### 179.查找总价格为目标值的两个商品(剑指Offer)

[传送门](https://leetcode.cn/problems/he-wei-sde-liang-ge-shu-zi-lcof/description/)

```go
func twoSum(price []int, target int) []int {
    if len(price) == 0 {
        return nil
    }
    left, right := 0, len(price) - 1
    sum := 0
    leftVal,rightVal := 0, 0
    for left <= right {
        leftVal,rightVal = price[left], price[right]
        sum = leftVal + rightVal
        if sum == target {
            return []int{leftVal,rightVal}
        }else if sum > target {
            right--
        }else {
            left++
        }
    }
    return nil
}
```

### 6. 两数之和II-输入有序数组(剑指Offer)

[传送门](https://leetcode.cn/problems/kLl5u1/description/)

```go
func twoSum(numbers []int, target int) []int {
    if len(numbers) == 0 {
        return nil
    }
    left, right := 0, len(numbers) - 1
    sum := 0
    for left <= right {
        sum = numbers[left] + numbers[right]
        if sum == target {
            return []int{left,right}
        }else if sum > target {
            right--
        }else {
            left++
        }
    }
    return nil
}
```
