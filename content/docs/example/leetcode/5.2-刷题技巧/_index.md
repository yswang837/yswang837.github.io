---
weight: 1
title: 5.2 刷题技巧
---

## 1. 双指针秒杀数组问题

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

### 167.两数之和 II - 输入有序数组

### 27.移除元素

### 283.移动零

### 344.反转字符串

&emsp;&emsp;反转数组一个意思。

### 例：回文串判断

### 5.最长回文子串

## 2. 双指针秒杀链表问题

### 83.删除排序链表中的重复元素
