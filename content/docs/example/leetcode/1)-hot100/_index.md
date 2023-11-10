# hot100

&emsp;&emsp;用golang1.19.4实现，将每题的函数粘贴到leetcode中即可一键运行，题目编号沿用leetcode的编号。项目代码：https://github.com/yswang837/golang-leetcode

## 哈希

&emsp;&emsp;map是典型的用空间换取时间的数据结构。

### 1.两数之和

- 地址：[传送门](https://leetcode.cn/problems/two-sum/description/?envType=study-plan-v2&envId=top-100-liked)
- 思路1：双重循环暴力破解，时间复杂度为O(n^2)
- 思路2：一次遍历，一边遍历，一边维护map，把num作为map的key，index作为map的value，可以O(n)时间复杂度解题。本题代码用思路2。

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
```

### 49.字母异位词分组

- 地址：[传送门](https://leetcode.cn/problems/group-anagrams/description/?envType=study-plan-v2&envId=top-100-liked)
- 思路：对strs的每个元素str进行排序，将排序的结果记录到map里面，其中，map的key为排序后的str，map的value为字母异位词的str的切片，最后返还一个由value为元素的二维切片就行。
```go
func groupAnagrams(strs []string) [][]string {
	var ret [][]string
	if len(strs) == 0 {
		return ret
	}
	if len(strs) == 1 {
		ret = append(ret, strs)
		return ret
	}
	m := map[string][]string{}
	var b []byte
	for _, str := range strs {
		b = []byte(str)
		sort.Slice(b, func(i, j int) bool {
			return b[i] < b[j]
		})
		key := string(b)
		m[key] = append(m[key], str) // m[key]在不在都是将新的str append到对应的切片上。

	}
	for _, val := range m {
		ret = append(ret, val)
	}
	return ret
}
```

### 128.最长连续序列

- 地址：[传送门](https://leetcode.cn/problems/longest-consecutive-sequence/?envType=study-plan-v2&envId=top-100-liked)
- 思路：首先将nums装入map[int]bool中(方便取到的值能直接当做bool用)，找到map中，每个连续段key的起始值，向后循环，求出每段的长度，和当前长度就max，循环结束，当前的max就是最大的max。
- 例子：m[1:true,2:true,3:true,4:true,100:true,200:true],

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

