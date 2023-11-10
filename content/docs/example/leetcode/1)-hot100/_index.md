# hot100

&emsp;&emsp;用golang1.19.4实现，将每题的函数粘贴到leetcode中即可一键运行。项目代码：https://github.com/yswang837/golang-leetcode

## 哈希

### 1.两数之和

- 地址：[传送门](https://leetcode.cn/problems/two-sum/description/?envType=study-plan-v2&envId=top-100-liked)
- 思路1：双重循环暴力破解，时间复杂度为O(n^2)
- 思路2：一次遍历，把num作为map的key，index作为map的value，可以O(n)时间复杂度解题，map是典型的用空间换取时间的数据结构。本题代码用思路2。

```go
func twoSum(nums []int, target int) []int {
	ret := []int{-1, -1}
	if len(nums) == 0 {
		return ret
	}
	m := map[int]int{}
	for i, val := range nums {
		tmp := target - val
		if i2, ok := m[tmp]; ok {
			return []int{i, i2}
		}
		m[val] = i
	}
	return ret
}
``````

## 双指针

## 滑动窗口

## 子串

## 普通数组

## 矩阵

## 链表

## 二叉树

## 图论

## 回溯

## 二分查找

## 栈

## 堆

## 贪心算法

## 动态规划

## 多维动态规划

## 技巧

