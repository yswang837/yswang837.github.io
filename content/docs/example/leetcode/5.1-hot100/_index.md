---
weight: 1
title: 5.1 hot100
---

&emsp;&emsp;用golang1.19.4实现，将每题的函数粘贴到leetcode中即可一键运行，题目编号沿用leetcode的编号。项目代码：https://github.com/yswang837/golang-leetcode

## \*哈希

&emsp;&emsp;map是典型的用空间换取时间的数据结构。

### 1.两数之和

- 地址：[传送门](https://leetcode.cn/problems/two-sum/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：O(N)时间复杂度
- 思路1：双重循环暴力破解，时间复杂度为O(n^2)
- 思路2：一次遍历，一边遍历，一边维护map，把num作为map的key，index作为map的value，可以O(N)时间复杂度解题。本题代码用思路2。

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
- 要求：O(N)时间复杂度
- 思路：首先将nums装入map[int]bool中(方便取到的值能直接当做bool用)，找到map中，每个连续段key的起始值，向后循环，求出每段的长度，和当前长度就max，循环结束，当前的max就是最大的max。这是O(N)时间复杂度，注意n个O(1)也是O(1),所以即使是嵌套循环，也不是O(N^2)
- 例子：m[1:true,2:true,3:true,4:true,100:true,200:true]，每段的长度是4,1,1,两两求max就是4

```go
func longestConsecutive(nums []int) int {
		if len(nums) == 0 {
			return 0
		}
		m := map[int]bool{}
		for _,val := range nums {
			m[val] = true
		}
		ret := 0
		for key := range m {
			if ok := m[key-1]; ok {
				continue
			}
			currentLength := 1
			flag := key
			for {
				if ok := m[flag+1];ok {
					flag++
					currentLength++
				}else {
					break
				}
			}
			ret = maxInt(currentLength,ret)
		}
		return ret

}

func maxInt(i,j int) int {
		if i>j {
			return i
		}
		return j
}
```

## \*双指针

### 283.移动零

- 地址：[传送门](https://leetcode.cn/problems/move-zeroes/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：原位操作，且尽量减少操作次数
- 思路：原位操作意味着只能通过交换元素来实现，初始的快慢指针都是0，当快指针小于len时循环，很巧妙，操作次数也很少
- 例子：[0,1,0,3,12], [1,0,0,3,12], [1,3,0,0,12], [1,3,12,0,0]
  
```go
func moveZeroes(nums []int) {
	slow, fast, length := 0, 0, len(nums)
	for fast < length {
		if nums[fast] != 0 {
			nums[slow], nums[fast] = nums[fast], nums[slow]
			slow++
		}
		fast++
	}
}
```

### 11.盛最多水的容器

- 地址：[传送门](https://leetcode.cn/problems/container-with-most-water/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：不能倾斜容器
- 思路：双指针，一个在左，一个在右，两两求面积最大的矩形即可。

```go
func maxArea(height []int) int {
    if len(height) == 0 || len(height) == 1 {
        return 0
    }
    left, right := 0, len(height)-1
    maxarea := 0
    for left < right {
        h,flag := subabs(height[left], height[right])
        w := right - left
        maxarea = maxInt(h*w,maxarea)
        if flag {
            right--
        }else {
            left++
        }
    }
    return maxarea
}

func maxInt(i,j int) int {
    if i>j {
        return i
    }
    return j
}

func subabs(i,j int) (int,bool) {
    //左是否大于右
    if i-j < 0 {
        return i, false
    }
    return j, true
}
```

### 15.三数之和

- 地址：[传送门](https://leetcode.cn/problems/3sum/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：答案中不可以包含重复的三元组。
- 思路：

### 42.接雨水

- 地址：[传送门](https://leetcode.cn/problems/trapping-rain-water/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*滑动窗口

### 3.无重复字符的最长子串

- 地址：[传送门](https://leetcode.cn/problems/longest-substring-without-repeating-characters/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 438.找到字符串中所有字母异位词

- 地址：[传送门](https://leetcode.cn/problems/find-all-anagrams-in-a-string/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*子串

### 560.和为K的子数组

- 地址：[传送门](https://leetcode.cn/problems/subarray-sum-equals-k/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 239.滑动窗口最大值

- 地址：[传送门](https://leetcode.cn/problems/sliding-window-maximum/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 76.最小覆盖子串

- 地址：[传送门](https://leetcode.cn/problems/minimum-window-substring/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*普通数组

### 53.最大子数组和

- 地址：[传送门](https://leetcode.cn/problems/maximum-subarray/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 56.合并区间

- 地址：[传送门](https://leetcode.cn/problems/merge-intervals/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 189.轮转数组

- 地址：[传送门](https://leetcode.cn/problems/rotate-array/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 238.除自身以外数组的乘积

- 地址：[传送门](https://leetcode.cn/problems/product-of-array-except-self/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 41.缺失的第一个正数

- 地址：[传送门](https://leetcode.cn/problems/first-missing-positive/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*矩阵

### 73.矩阵置零

- 地址：[传送门](https://leetcode.cn/problems/set-matrix-zeroes/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 54.螺旋矩阵

- 地址：[传送门](https://leetcode.cn/problems/spiral-matrix/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 48.旋转图像

- 地址：[传送门](https://leetcode.cn/problems/rotate-image/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 240.搜索二维矩阵II

- 地址：[传送门](https://leetcode.cn/problems/search-a-2d-matrix-ii/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*链表

### 160. 相交链表

- 地址：[传送门](https://leetcode.cn/problems/intersection-of-two-linked-lists/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：返回的依旧是个链表
- 思路：难点在于两个链表的长度不一定相等，导致不知道什么时候会相交，链表A+链表B的长度肯定相等，那么两个链表的值第一次相等的时候，就是相交节点的位置。

```go
func getIntersectionNode(headA, headB *ListNode) *ListNode {
    if headA == nil || headB == nil {
        return nil
    }
    curA, curB := headA, headB
    for curA != curB {
        if curA == nil {
            curA = headB
        }else {
            curA = curA.Next
        }
        if curB == nil {
            curB = headA
        }else {
            curB = curB.Next
        }
    }
    return curA
}
```

### 206.反转链表

- 地址：[传送门](https://leetcode.cn/problems/reverse-linked-list/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：在遍历链表时，将当前节点的next指针改为指向前一个节点。由于节点没有引用其前一个节点，因此必须事先存储其前一个节点。在更改引用之前，还需要存储后一个节点。最后返回新的头引用。

```go
func reverseList(head *ListNode) *ListNode {
    if head == nil {
        return nil
    }
    var pre *ListNode
    cur := head
    for cur != nil {
        next := cur.Next
        cur.Next = pre
        pre = cur
        cur = next
    }
    return pre
}
```

### 146.LRU缓存

- 地址：[传送门](https://leetcode.cn/problems/lru-cache/)
- 要求：get和put操作必须以O(1)的时间复杂度
- 思路：假设缓存容量是length=5，则ABCDBEFG最终会存成FGEBD，get操作需要O(1)时间复杂度，所以用map来查，put操作需要O(1)时间复杂度，并且要在头部插入，尾部删除，所以用双向链表来存，head <-> ... node ... <-> tail，PUT：元素要在头部插入，容量满了之后，在尾部删除。----> 双向链表，GET：在O(1)内查到元素，该元素从原位置删除，再插入头部 ----> map(key,node)

```go
type Node struct {
	key  int
	val  int
	prev *Node
	next *Node
}

// 一个LRU缓存是由map和双向链表构成
type LRUCache struct {
	capacity int
	hashMap  map[int]*Node
	head     *Node
	tail     *Node
}

func Constructor(capacity int) LRUCache {
	// 初始化头尾相互指向的双链表，初始化容量为capacity的map
	// head <-> tail
	head, tail := &Node{}, &Node{}
	head.next = tail
	tail.prev = head
	return LRUCache{
		capacity: capacity,
		hashMap:  map[int]*Node{},
		head:     head,
		tail:     tail,
	}
}

func (this *LRUCache) Get(key int) int {
	// 从LRU中查数据，
	// 1. 查不到直接返回-1
	// 2. 查到了返回对应值，并将该节点从当前位置删除，并在头结点位置插入
	node, ok := this.hashMap[key]
	if !ok {
		return -1
	}
	this.remove(node)
	this.insert(node)
	return node.val
}

func (this *LRUCache) Put(key int, value int) {
	// 将key value加入或更新到LRU中
	// 1. 如果在LRU中，则属于更新，更新不需要维护容量，将原有位置删除，并插入头部
	// 2. 如果不在LRU中，则属于新增，将新节点插入头部，新增需要维护容量，如果当前容量大于capacity，则删除最后一个节点
	node, ok := this.hashMap[key]
	if ok {
		this.remove(node)
		node.val = value
		this.insert(node)
	} else {
		newNode := &Node{key: key, val: value}
		this.insert(newNode)
        this.hashMap[key] = newNode
		if len(this.hashMap) > this.capacity {
			lastNode := this.tail.prev
			this.remove(lastNode)
			delete(this.hashMap, lastNode.key)
		}
	}
}

func (this *LRUCache) remove(node *Node) {
	// xxx <-> node <-> xxx
	node.prev.next = node.next
	node.next.prev = node.prev
	// xxx <-> xxx
}

func (this *LRUCache) insert(node *Node) {
	// head <-> xxx
	next := this.head.next
	this.head.next = node // head -> node
	node.prev = this.head // head <-> node
	node.next = next      // head <-> node -> xxx
	next.prev = node      // head <-> node <-> xxx
	// head <-> node <-> xxx
}

```

### 234. 回文链表

- 地址：[传送门](https://leetcode.cn/problems/palindrome-linked-list/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：能否用 O(n) 时间复杂度和 O(1) 空间复杂度解决此题
- 思路1：遍历一遍链表，将结果存到数组里面，双指针遍历该数组，都相等则是回文链表。
- 思路2：快慢指针，慢指针走一步，快指针走两步，在慢指针的位置断开链表，并将前半部分链表反转一下，在遍历两个链表，都相等则是回文链表。

```go
// 思路1
func isPalindrome(head *ListNode) bool {
    var ret []int
    for head != nil {
        ret = append(ret, head.Val)
        head = head.Next
    }
    left, right := 0, len(ret) - 1 
    for left < right {
        if ret[left] != ret[right] {
            return false
        }
        left++
        right--
    }
    return true
}

// 思路2

```

### 141. 环形链表

- 地址：[传送门](https://leetcode.cn/problems/linked-list-cycle/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：无
- 思路：快慢指针，同时走，快的一次走两步，慢的一次走一步，相等就有环

```go
func hasCycle(head *ListNode) bool {
    if head == nil {
        return false
    }
    slow, fast := head, head
    for fast != nil && fast.Next != nil {
        slow = slow.Next
        fast = fast.Next.Next
        if fast == slow {
            return true
        }
    }
    return false
}
```

### 142. 环形链表 II

- 地址：[传送门](https://leetcode.cn/problems/linked-list-cycle-ii/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：我们假设快慢指针相遇时，慢指针slow走了k步，那么快指针fast一定走了2k步，即fast一定比slow多走了k步，这多走的k步其实就是fast指针在环里转圈圈，所以k的值就是环长度的「整数倍」，假设相遇点距环的起点的距离为m，环的起点距头结点head的距离一定为k - m，也就是说如果从 head 前进 k - m 步就能到达环起点。巧的是，如果从相遇点继续前进 k - m 步，也恰好到达环起点。所以当它们以同样的速度再次相遇时，就是环的起点所在位置。

```go
func detectCycle(head *ListNode) *ListNode {
    if head == nil {
        return nil
    }
    slow, fast := head, head
    for fast != nil && fast.Next != nil {
        slow = slow.Next
        fast = fast.Next.Next
        if fast == slow {
            break
        }
    }
    // 执行到这里，可能是有环break了，可能没环退出循环了
    if fast == nil || fast.Next == nil {
        // 没环直接return
        return nil
    }
    // 执行到这里，必定有环
    slow = head
    for slow != fast {
        slow = slow.Next
        fast = fast.Next
    }
    return slow
}
```

### 21. 合并两个有序链表

- 地址：[传送门](https://leetcode.cn/problems/merge-two-sorted-lists/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：无
- 思路：用一个虚拟节点dummy方便处理。

```go
func mergeTwoLists(list1 *ListNode, list2 *ListNode) *ListNode {
    if list1 == nil {
        return list2
    }
    if list2 == nil {
        return list1
    }
    dummy := &ListNode{-1,nil}
    cur := dummy
    for list1 != nil && list2 != nil {
        if list1.Val > list2.Val {
            cur.Next = list2
            list2 = list2.Next
        }else {
            cur.Next = list1
            list1 = list1.Next
        }
        cur = cur.Next
    }
    if list1 != nil {
        cur.Next = list1
    }
    if list2 != nil {
        cur.Next = list2
    }
    return dummy.Next
}
// dummy,cur
// l1: 1->2->4
// l2: 1->3->4
//             cur
// l1: dummy -> 1 -> 2 -> 4
                    cur
// l2: dummy -> 1 -> 1 -> 3 -> 4
                         cur
// l1: dummy -> 1 -> 1 -> 2 -> 4
                              cur
// l2: dummy -> 1 -> 1 -> 2 -> 3 -> 4
                                   cur
// l1: dummy -> 1 -> 1 -> 2 -> 3 -> 4 // 循环终止
                                   cur
// l2: dummy -> 1 -> 1 -> 2 -> 3 -> 4 -> 4
```

### 2. 两数相加

- 地址：[传送门](https://leetcode.cn/problems/add-two-numbers/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 19. 删除链表的倒数第 N 个结点

- 地址：[传送门](https://leetcode.cn/problems/remove-nth-node-from-end-of-list/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：一次遍历
- 思路：快慢指针，fast先走N步，再和慢指针一起走，fast负责探路，slow负责处理。

```go
func removeNthFromEnd(head *ListNode, n int) *ListNode {
    if head == nil {
        return nil
    }
    dummy := &ListNode{-1,head}
    slow, fast := dummy, dummy
    for i:=0; i<=n; i++ { // 因为加了个虚拟节点dummy，所以需要等于，为什么要加dummy的原因在于：为了删除第一个节点的case
        fast = fast.Next
    }
    for fast != nil {
        fast = fast.Next
        slow = slow.Next
    }
    // 执行到这里fast已经是nil了
    slow.Next = slow.Next.Next
    return dummy.Next
}
//              f
//        s
// [a,1,2,3,4,5], n = 2

//      f
//  s
// [a,1], n = 1

//        f
//    s
// [a,1,2], n = 1
```

### 24. 两两交换链表中的节点

- 地址：[传送门](https://leetcode.cn/problems/swap-nodes-in-pairs/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 25. K 个一组翻转链表

- 地址：[传送门](https://leetcode.cn/problems/reverse-nodes-in-k-group/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 138. 随机链表的复制

- 地址：[传送门](https://leetcode.cn/problems/copy-list-with-random-pointer/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 148. 排序链表

- 地址：[传送门](https://leetcode.cn/problems/sort-list/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 23. 合并 K 个升序链表

- 地址：[传送门](https://leetcode.cn/problems/merge-k-sorted-lists/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路1：我们已经实现了合并两个有序链表的函数，合并k个有序链表，也就扩展下就行了，但时间复杂度有点高，不过还是通过了，代码如下：
- 思路2：使用优先级队列（二叉堆），这个代码后面再补充，https://labuladong.github.io/algo/di-ling-zh-bfe1b/shuang-zhi-0f7cc/

```go
func mergeKLists(lists []*ListNode) *ListNode {
    if len(lists) == 0 {
        return nil
    }
    var ret *ListNode
    for _, node := range lists {
        ret = mergeTwoLists(ret, node)
    }
    return ret
}

func mergeTwoLists(list1 *ListNode, list2 *ListNode) *ListNode {
    if list1 == nil {
        return list2
    }
    if list2 == nil {
        return list1
    }
    dummy := &ListNode{-1,nil}
    cur := dummy
    for list1 != nil && list2 != nil {
        if list1.Val > list2.Val {
            cur.Next = list2
            list2 = list2.Next
        }else {
            cur.Next = list1
            list1 = list1.Next
        }
        cur = cur.Next
    }
    if list1 != nil {
        cur.Next = list1
    }
    if list2 != nil {
        cur.Next = list2
    }
    return dummy.Next
}
```

## \*二叉树

&emsp;&emsp;树的递归遍历，又称为深度优先DFS，分为动态规划解法和回溯算法的解法。树当然还有迭代遍历/层序遍历，也称为广度优先BFS。我会在下面的代码中尽可能提供多种解法，遇到树的问题，优先考虑动态规划，充分利用递归函数的返回值，如果涉及到向递归函数传参，那可优先将递归函数写成闭包，这样闭包内部也可只用外部的变量，不用传递指针，看起来可能会好理解点。

### 94. 二叉树的中序遍历

- 地址：[传送门](https://leetcode.cn/problems/binary-tree-inorder-traversal/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：无
- 思路1：动态规划划分子问题。
- 思路2：回溯算法，写一个闭包作为遍历函数，闭包内可访问闭包外的ret

```go
// 思路1，充分利用递归函数的返回值，不需要传递额外的指针。
func inorderTraversal(root *TreeNode) []int {
    if root == nil {
        return nil
    }
    var ret []int
    ret = append(ret, inorderTraversal(root.Left)...)
    ret = append(ret, root.Val)
    ret = append(ret, inorderTraversal(root.Right)...)
    return ret
}

// 思路2，采用闭包，闭包可以访问外部的变量，不需要传递额外的指针，感觉更好理解
func inorderTraversal(root *TreeNode) []int {
    if root == nil {
        return nil
    }
    var ret []int
    var f func(root *TreeNode)
    f = func(root *TreeNode) {
        if root == nil {
            return
        }
        f(root.Left)
        ret = append(ret, root.Val)
        f(root.Right)
    }
    f(root)
    return ret
}
```

### 104. 二叉树的最大深度

- 地址：[传送门](https://leetcode.cn/problems/maximum-depth-of-binary-tree/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：无
- 思路1：动态规划划分子问题，从整体的角度来解题，它当然也能定义额外的遍历函数，这个遍历函数通常有返回值且不需要额外的指针
- 思路2：回溯算法，记录每次遍历到的数据，是从局部的角度来解决问题，通常需要额外的遍历函数，这个遍历函数通常没有返回值，一般通过参数传入指针的形式来解题

```go
// 思路1
// 递归划分子问题的思想，采用了后续遍历，这是动态规划的思想，未借助额外的遍历函数，充分利用遍历函数maxDepth的返回值。
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

// 思路2，用闭包，可以不用传参，闭包内部可以访问闭包外部的变量
func maxDepth(root *TreeNode) int {
    if root == nil {
        return 0
    }
    ret, depth := 0, 0
    var f func(root1 *TreeNode)
    f = func(root1 *TreeNode) {
        if root1 == nil {
            return
        }
        depth++
        if root1.Left == nil && root1.Right == nil {
            // 到叶节点了，更新最大深度
            ret = maxInt(ret, depth)
        }
        f(root1.Left)
        f(root1.Right)
        depth--
    }
    f(root)
    return ret
}

func maxInt(i, j int) int {
    if i >= j {
        return i
    }
    return j

}
```

### 226. 翻转二叉树

- 地址：[传送门](https://leetcode.cn/problems/invert-binary-tree/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：无
- 思路1：动态规划划分子问题，递归函数invertTree有返回值
- 思路2：回溯算法

```go
// 思路1：动态规划，充分利用遍历函数invertTree的返回值
// 定义：给我一棵树，我就能返回这棵树的翻转二叉树
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

// 思路2：回溯算法，定义无返回值的traverse。当然通常回溯算法需要传入额外的指针，回溯算法也能有返回值
func invertTree(root *TreeNode) *TreeNode {
    if root == nil {
        return nil
    }
    var f func(node *TreeNode)
    f = func(node *TreeNode) {
        if node == nil {
            return 
        }
        node.Left, node.Right = node.Right, node.Left
        f(node.Left)
        f(node.Right)
    }
    f(root)
    return root
}
```

### 101. 对称二叉树

- 地址：[传送门](https://leetcode.cn/problems/symmetric-tree/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：用递归，和迭代的思想解题
- 思路1：动态规划，定义有返回值的递归函数且不需要传入额外的指针，需要同时满足同一个根节点，左右子树对称就是对称二叉树。同一个根节点可向递归函数传递两个root即可。时空复杂度都是O(n)，空间复杂度指的是系统栈的调用
- 思路2：迭代，同样需要同时满足同一个根节点，左右子树对称就是对称二叉树。将递归程序改成迭代程序通常会用到一个队列，初始化时我们把根节点入队两次。每次提取两个结点并比较它们的值（队列中每两个连续的结点应该是相等的，而且它们的子树互为镜像），然后将两个结点的左右子结点按相反的顺序插入队列中。当队列为空时，或者我们检测到树不对称（即从队列中取出两个不相等的连续结点）时，该算法结束。可以发现思路1更优雅。

```go
// 思路1
func isSymmetric(root *TreeNode) bool {
    return traverse(root,root)
}

func traverse(root1, root2 *TreeNode) bool {
    if root1 == nil && root2 == nil {
        return true
    }
    if root1 == nil || root2 == nil {
        return false
    }
    return root1.Val == root2.Val && traverse(root1.Left, root2.Right) && traverse(root1.Right, root2.Left)
}

// 思路2
func isSymmetric(root *TreeNode) bool {
    // 这种写法包含了两个root都是空的情况
    queue := []*TreeNode{} // 借助一个队列
    p, q := root,root // 初始化两个节点，并将其放入队列
    queue = append(append(queue, p), q)
    for len(queue) > 0 {
        p, q = queue[0], queue[1]
        queue = queue[2:] // 出队两个元素
        if p == nil && q == nil {
            continue
        }
        if p == nil || q == nil {
            return false
        }
        if p.Val != q.Val {
            return false
        }
        queue = append(append(queue, p.Left), q.Right)
        queue = append(append(queue, p.Right), q.Left)
    }
    return true
}
```

### 543. 二叉树的直径

- 地址：[传送门](https://leetcode.cn/problems/diameter-of-binary-tree/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：回溯算法，需要通过maxDepth函数求出子树的最大深度，这个回溯需要返回值，需要传递额外的指针。遇到树问题，首先想到的是给函数设置返回值，然后在后序位置做文章。这个问题貌似也能看做是动态规划的问题，问题分解：一棵树的直径 = max(左子树的最大深度+右子树的最大深度)

```go
func diameterOfBinaryTree(root *TreeNode) int {
    maxDiameter := 0
    var maxDepth func(root *TreeNode) int
    maxDepth = func(root *TreeNode) int{
        if root == nil {
            return 0
        }
        leftDepth := maxDepth(root.Left)
        rightDepth := maxDepth(root.Right)
        curDepth := leftDepth + rightDepth
        if curDepth > maxDiameter {
            maxDiameter = curDepth
        }
        if leftDepth >= rightDepth {
            return leftDepth + 1
        }else {
            return rightDepth + 1
        }
    }
    maxDepth(root)
    return maxDiameter
}
```

### 102. 二叉树的层序遍历

- 地址：[传送门](https://leetcode.cn/problems/binary-tree-level-order-traversal/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：无
- 思路：这是一种迭代遍历的思路，通常递归问题转迭代问题时，都需要引入一个队列queue来处理。

```go
func levelOrder(root *TreeNode) [][]int {
    if root == nil {
        return nil
    }
    var ret [][]int
    var queue []*TreeNode
    queue = append(queue, root)
    for len(queue) > 0 {
        var level []int
        length := len(queue) // queue的长度会变，需要用变量单独记录，不然level的结果不对
        for i:=0; i<length; i++ {
            node := queue[0]
            queue = queue[1:]
            level = append(level, node.Val)
            if node.Left != nil {
                queue = append(queue, node.Left)
            }
            if node.Right != nil {
                queue = append(queue, node.Right)
            }
        }
        if len(level) > 0 {
            ret = append(ret, level)
        }
    }
    return ret
}
```

### 108. 将有序数组转换为二叉搜索树

- 地址：[传送门](https://leetcode.cn/problems/convert-sorted-array-to-binary-search-tree/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：无
- 思路：二叉搜索树的中序遍历是升序序列。动态规划，将问题划分为：中间节点+左右子树的问题，模仿二分查找的思路，二分地找数组的中间节点，递归地将该节点作为根节点，把左边给左边的树，右边给右边的树。

```go
func sortedArrayToBST(nums []int) *TreeNode {
    if len(nums) == 0 {
        return nil
    }
    return traverse(nums, 0, len(nums) - 1)
}

func traverse(nums []int, left int, right int) *TreeNode {
    if left > right {
        return nil
    }
    middle := (left + right) / 2
    root := &TreeNode{Val:nums[middle]}
    root.Left = traverse(nums, left, middle - 1)
    root.Right = traverse(nums, middle + 1, right)
    return root
}
```

### 98. 验证二叉搜索树

- 地址：[传送门](https://leetcode.cn/problems/validate-binary-search-tree/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：无
- 思路：动态规划，二叉搜索树的性质：根节点的值都大于左子树的值，并且根节点的值都小于右子树的值。

```go
func isValidBST(root *TreeNode) bool {
    return traverse(root, math.MinInt, math.MaxInt)
}

func traverse(root *TreeNode, left, right int) bool {
    if root == nil {
        return true
    }
    x := root.Val
    return x > left && x < right && traverse(root.Left, left, x) && traverse(root.Right, x, right)
}
```

### 230. 二叉搜索树中第K小的元素

- 地址：[传送门](https://leetcode.cn/problems/kth-smallest-element-in-a-bst/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：无
- 思路：中序遍历就是有序数组，直接返回下标为k-1的那个值

```go
func kthSmallest(root *TreeNode, k int) int {
    var f func(root *TreeNode)
    var ss []int
    f = func(root *TreeNode) {
        if root == nil {
            return
        }
        f(root.Left)
        ss = append(ss, root.Val)
        f(root.Right)
    }
    f(root)
    return ss[k-1]
}
```

### 199. 二叉树的右视图

- 地址：[传送门](https://leetcode.cn/problems/binary-tree-right-side-view/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：当前的深度大于结果的长度，才认为是需要添加到结果里面的，题目要求右视图，所以先递归右子树。当题目要求左视图，自然想到先递归左子树。

```go
func rightSideView(root *TreeNode) []int {
    if root == nil {
        return nil
    }
    var ret []int
    depth := 0
    var f func(node *TreeNode)
    f = func(node *TreeNode) {
        if node == nil {
            return
        }
        depth++
        if depth > len(ret) {
            ret = append(ret, node.Val)
        }
        f(node.Right)
        f(node.Left)
        depth--
    }
    f(root)
    return ret
}
```

### 114. 二叉树展开为链表

- 地址：[传送门](https://leetcode.cn/problems/flatten-binary-tree-to-linked-list/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：链表的遍历结果应该与二叉树的前序遍历相同，结果依旧用树的节点表示链表，其中right指针指向链表中的下一个节点，left指针始终指向nil。
- 思路：动态规划，划分子问题，传递一棵树，返回一个链表。只需要考虑当前root节点应该怎么做，递归函数会自动遍历出所有节点。

```go
func flatten(root *TreeNode)  {
    // 1、边界条件
    if root == nil {
        return
    }
    // 2、逻辑处理
    // 将左右子树展平为链表
    flatten(root.Left)
    flatten(root.Right)
    left := root.Left
    right := root.Right
    // 将左子树放在root的右子树上，并且把左子树置空
    root.Left = nil
    root.Right = left
    // 把右子树挪到末尾，并将原来的右子树接上去
    node := root
    for node.Right != nil {
        node = node.Right
    }
    node.Right = right
    // 3、返回
    return
}
```

### 105. 从前序与中序遍历序列构造二叉树

- 地址：[传送门](https://leetcode.cn/problems/construct-binary-tree-from-preorder-and-inorder-traversal/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：动态规划，找到前序的第一个节点在中序的位置，然后递归地根据根的位置调用buildTree，其定义是给我两个切片，我就能返回一棵树，给我左边的两个切片，我就返回左子树，给我右边的两个切片，我就返回右子树。如果题目变成了知道前序中序遍历，求后序遍历，那么只需要在本题的基础上，后续遍历这棵树并返回一个切片即可。知道前后序没法确定出中序，因为中序给了左右子树的位置信息。

```go
func buildTree(preorder []int, inorder []int) *TreeNode {
    if len(preorder) == 0 || len(inorder) == 0 {
        return nil
    }
    var root int
    for k, v := range inorder {
        if v == preorder[0] {
            root = k
            break
        }
    }
    return &TreeNode{
        Val: preorder[0],
        Left: buildTree(preorder[1: root+1], inorder[0:root]),
        Right: buildTree(preorder[root+1:],inorder[root+1:]),
    }
}
```

### 437. 路径总和 III

- 地址：[传送门](https://leetcode.cn/problems/path-sum-iii/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：路径 不需要从根节点开始，也不需要在叶子节点结束，但是路径方向必须是向下的（只能从父节点到子节点）。
- 思路：前缀和+哈希，这是数组技巧里面的考点。这题得借鉴一下第一题，两数之和的思路，前缀和数组改用为前缀和map，key是前缀和，value是路径数目，也就是结果的一部分，采用回溯算法的思想。

```go
func pathSum(root *TreeNode, targetSum int) int {
    prefixSum := map[int]int{0:1} // 初始化，前缀和为0的路径有1条。
    var f func(node *TreeNode, currentSum int) (ret int)
    f = func(node *TreeNode, currentSum int) (ret int) {
        if node == nil {
            return
        }
        currentSum += node.Val
        if cnt, ok := prefixSum[currentSum - targetSum]; ok {
            ret += cnt
        }
        prefixSum[currentSum]++
        ret = ret + f(node.Left, currentSum) + f(node.Right, currentSum)
        prefixSum[currentSum]--
        return ret
    }
    return f(root, 0)
}

```

### 236. 二叉树的最近公共祖先

- 地址：[传送门](https://leetcode.cn/problems/lowest-common-ancestor-of-a-binary-tree/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：动态规划

```go
func lowestCommonAncestor(root, p, q *TreeNode) *TreeNode {
    if root == nil || root == p || root == q {
        return root
    }
    left := lowestCommonAncestor(root.Left, p, q)
    right := lowestCommonAncestor(root.Right, p, q)
    if left != nil && right != nil {
        return root
    }
    if left != nil {
        return left
    }else {
        return right
    }
}
```

### 124. 二叉树中的最大路径和

- 地址：[传送门](https://leetcode.cn/problems/binary-tree-maximum-path-sum/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：把节点值的大小看做贡献值，那么当前节点对树的贡献值=自身的值+max(左子树，右子树)，记录下每次递归的最大值。递归结束时，最大值就是树的最大路径和。

```go
func maxPathSum(root *TreeNode) int {
    maxSum := math.MinInt32
    var maxGain func(node *TreeNode) int
    maxGain = func(node *TreeNode) int {
        if node == nil {
            return 0
        }
        leftGain := maxInt(maxGain(node.Left), 0)
        rightGain := maxInt(maxGain(node.Right), 0)
        currentSum := node.Val + leftGain + rightGain
        maxSum = maxInt(maxSum, currentSum)
        return node.Val + max(leftGain, rightGain)
    }
    maxGain(root)
    return maxSum
}

func maxInt(i, j int) int {
    if i >= j {
        return i
    }
    return j
}
```

## \*图论

### 200. 岛屿数量

- 地址：[传送门](https://leetcode.cn/problems/number-of-islands/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 994. 腐烂的橘子

- 地址：[传送门](https://leetcode.cn/problems/rotting-oranges/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 207. 课程表

- 地址：[传送门](https://leetcode.cn/problems/course-schedule/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 208. 实现 Trie (前缀树)

- 地址：[传送门](https://leetcode.cn/problems/implement-trie-prefix-tree/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*回溯

### 46. 全排列

- 地址：[传送门](https://leetcode.cn/problems/permutations/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 78. 子集

- 地址：[传送门](https://leetcode.cn/problems/subsets/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 17. 电话号码的字母组合

- 地址：[传送门](https://leetcode.cn/problems/letter-combinations-of-a-phone-number/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 39. 组合总和

- 地址：[传送门](https://leetcode.cn/problems/combination-sum/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 22. 括号生成

- 地址：[传送门](https://leetcode.cn/problems/generate-parentheses/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 79. 单词搜索

- 地址：[传送门](https://leetcode.cn/problems/word-search/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 131. 分割回文串

- 地址：[传送门](https://leetcode.cn/problems/palindrome-partitioning/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 51. N 皇后

- 地址：[传送门](https://leetcode.cn/problems/n-queens/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*二分查找

### 35. 搜索插入位置

- 地址：[传送门](https://leetcode.cn/problems/search-insert-position/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 74. 搜索二维矩阵

- 地址：[传送门](https://leetcode.cn/problems/search-a-2d-matrix/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 34. 在排序数组中查找元素的第一个和最后一个位置

- 地址：[传送门](https://leetcode.cn/problems/find-first-and-last-position-of-element-in-sorted-array/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 33.搜索旋转排序数组

- 地址：[传送门](https://leetcode.cn/problems/search-in-rotated-sorted-array/?envType=study-plan-v2&envId=top-100-liked)
- 要求：请设计一个时间复杂度为O(logN)的算法解决此问题。
- 思路：将数组一分为二，其中一定有一个是有序的，另一个可能是有序，也能是部分有序。此时有序部分用二分法查找。无序部分再一分为二，其中一个一定有序，另一个可能有序，可能无序。就这样循环。判断target在不在有序数组里，只需要比较最小值和最大值即可，如果target不在顺序区间，那么便去乱序区间，在其中再分割出有序区间。如果有序区间中有target那便好说，直接二分便可获得答案
- 例子：// [4, 5, 6, 7, 8, 9, 1, 2, 3], 3  第一次循环左边有序     // [7, 8, 9, 1, 2, 3, 4, 5, 6], 3  第一次循环右边有序

```go
func search(nums []int, target int) int {
    left, middle, right := 0, 0, len(nums) - 1
    for left <= right {
        middle = (left + right) / 2
        if nums[middle] == target {
            return middle
        }
        // 判断哪边有序
        if nums[left] <= nums[middle] {
            // 左边有序
            if nums[left] <= target && target < nums[middle] {
                // 目标值在这个有序区间
                right = middle - 1
            }else {
                // 目标值在这个无序区间
                left = middle + 1
            }
        }else {
            // 右边有序
            if nums[middle] < target && target <= nums[right] {
                // 目标值在这个有序区间
                left = middle + 1
            }else {
                // 目标值在这个无序区间
                right = middle - 1
            }
        }
    }
    return -1
}
```

### 153. 寻找旋转排序数组中的最小值

- 地址：[传送门](https://leetcode.cn/problems/find-minimum-in-rotated-sorted-array/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 4. 寻找两个正序数组的中位数

- 地址：[传送门](https://leetcode.cn/problems/median-of-two-sorted-arrays/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*栈

### 20. 有效的括号

- 地址：[传送门](https://leetcode.cn/problems/valid-parentheses/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：用一个栈，需要左括号入栈，遇到右括号就取栈顶元素，看是不是能匹配上，不能匹配则直接返回false，最后栈空则是有效的括号，否则不是。

```go
func isValid(s string) bool {
    if len(s) == 0 || len(s)%2 == 1 {
		return false
	}
	m := map[byte]byte{')': '(', ']': '[', '}': '{'}
	stack := []byte{}
	for _, value := range s {
		if value == '(' || value == '[' || value == '{' {
			stack = append(stack, byte(value))
		} else {
            if len(stack) == 0 { // 防止这种括号 }{
                return false
            }
			top := stack[len(stack)-1]
			stack = stack[:len(stack)-1]
			if m[byte(value)] != top {
				return false
			}
		}
	}
	return len(stack) == 0
}
```

### 155. 最小栈

- 地址：[传送门](https://leetcode.cn/problems/min-stack/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：在常数时间内检索到最小元素的栈。
- 思路：主栈主要用于实现push,pop和pop函数，辅助栈主要用于记录每次的最小值，保证栈顶元素始终是最小值即可，两个栈的长度是一致的，同时操作即可，很简单

```go
type MinStack struct {
    stack []int
    minStack []int
}


func Constructor() MinStack {
    return MinStack{
        stack: []int{},
        minStack: []int{},
    }
}


func (this *MinStack) Push(val int)  {
    this.stack = append(this.stack, val)
    if len(this.minStack) == 0 {
        this.minStack = append(this.minStack, val)
    }else {
        top := this.minStack[len(this.minStack)-1]  
        this.minStack = append(this.minStack, minInt(top,val))
    }
    
}

func minInt(i,j int) int {
    if i <= j {
        return i
    }
    return j
}


func (this *MinStack) Pop() {
    if len(this.stack) >= 1 {
        this.stack = this.stack[:len(this.stack)-1]
        this.minStack = this.minStack[:len(this.minStack)-1]
    }
    
}

func (this *MinStack) Top() int {
    if len(this.stack) >= 1 {
        return this.stack[len(this.stack)-1]
    }
    return math.MaxInt
}


func (this *MinStack) GetMin() int {
    if len(this.minStack) >= 1 {
        return this.minStack[len(this.minStack)-1]
    }
    return math.MaxInt
}
```

### 394. 字符串解码

- 地址：[传送门](https://leetcode.cn/problems/decode-string/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：可认为所有的输入均为合法输入
- 思路：用两个栈，一个用于存数字，一个用于存字母，遇到左括号数字和结果ret均入栈后，将其置为对应的零值，遇到右括号数字和ret均出站，并构建新的结果，仅仅遇到字母，则直接构建新的结果。
  
```go
func decodeString(s string) string {
	if len(s) == 0 {
		return ""
	}
	numStack := []int{}
	strStack := []string{}
	num := 0  // 用于累积读取完整数字
	ret := "" // 用于累积当前解码的字符串
	for _, char := range s {
		switch char {
		case '0', '1', '2', '3', '4', '5', '6', '7', '8', '9':
			n, _ := strconv.Atoi(string(char))
			num = num*10 + n
		case '[': // 当遇到左括号，表示一个新的编码字符串开始
			strStack = append(strStack, ret)
			ret = "" // 重置数字和字符串，以便处理新的编码字符串
			numStack = append(numStack, num)
			num = 0
		case ']': // 当遇到右括号，表示当前编码字符串结束
			count := numStack[len(numStack)-1]
			numStack = numStack[:len(numStack)-1]
			str := strStack[len(strStack)-1]
			strStack = strStack[:len(strStack)-1]
			ret = str + strings.Repeat(ret, count)
		default: // 当遇到字母时，直接添加到当前字符串中
			ret += string(char)
		}
	}
	return ret
}
```

### 739. 每日温度

- 地址：[传送门](https://leetcode.cn/problems/daily-temperatures/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：题目和顺序有关，可以考虑单调栈，二分，堆，排序这些技巧，挨个想，总有一个是对的，本题我们采用单调栈的思想。

```go

```

### 84. 柱状图中最大的矩形

- 地址：[传送门](https://leetcode.cn/problems/largest-rectangle-in-histogram/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*堆

### 215. 数组中的第K个最大元素

- 地址：[传送门](https://leetcode.cn/problems/kth-largest-element-in-an-array/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 347. 前 K 个高频元素

- 地址：[传送门](https://leetcode.cn/problems/top-k-frequent-elements/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 295. 数据流的中位数

- 地址：[传送门](https://leetcode.cn/problems/find-median-from-data-stream/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*贪心算法

### 121. 买卖股票的最佳时机

- 地址：[传送门](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 55. 跳跃游戏

- 地址：[传送门](https://leetcode.cn/problems/jump-game/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 45. 跳跃游戏 II

- 地址：[传送门](https://leetcode.cn/problems/jump-game-ii/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 763. 划分字母区间

- 地址：[传送门](https://leetcode.cn/problems/partition-labels/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*动态规划

### 70. 爬楼梯

- 地址：[传送门](https://leetcode.cn/problems/climbing-stairs/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 118. 杨辉三角

- 地址：[传送门](https://leetcode.cn/problems/pascals-triangle/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 198. 打家劫舍

- 地址：[传送门](https://leetcode.cn/problems/house-robber/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 279. 完全平方数

- 地址：[传送门](https://leetcode.cn/problems/perfect-squares/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 322. 零钱兑换

- 地址：[传送门](https://leetcode.cn/problems/coin-change/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 139. 单词拆分

- 地址：[传送门](https://leetcode.cn/problems/word-break/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 300. 最长递增子序列

- 地址：[传送门](https://leetcode.cn/problems/longest-increasing-subsequence/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 152. 乘积最大子数组

- 地址：[传送门](https://leetcode.cn/problems/maximum-product-subarray/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 416. 分割等和子集

- 地址：[传送门](https://leetcode.cn/problems/partition-equal-subset-sum/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 32. 最长有效括号

- 地址：[传送门](https://leetcode.cn/problems/longest-valid-parentheses/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*多维动态规划

### 62. 不同路径

- 地址：[传送门](https://leetcode.cn/problems/unique-paths/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 64. 最小路径和

- 地址：[传送门](https://leetcode.cn/problems/minimum-path-sum/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 5. 最长回文子串

- 地址：[传送门](https://leetcode.cn/problems/longest-palindromic-substring/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：首先明确一下，回文串就是正着读和反着读都一样的字符串，判断回文串很简单，用左右指针相向而行就行了，而且不需要考虑是奇数还是偶数。但寻找最长回文子串，需要考虑奇数还是偶数，同样采取左右指针，但这个左右指针是相背而行，从中间向两端搜索。

```go
func longestPalindrome(s string) string {
    res := ""
    for i := 0; i < len(s); i++ {
        // 以 s[i] 为中心的最长回文子串
        s1 := palindrome(s, i, i)
        // 以 s[i] 和 s[i+1] 为中心的最长回文子串
        s2 := palindrome(s, i, i + 1)
        res = maxLenOfString(res,s1)
        res = maxLenOfString(res,s2)
    }
    return res
}

func palindrome(s string, l, r int) string {
		if l > r {
			return ""
		}
		for l >= 0 && r < len(s) && s[l] == s[r] {
			l--
			r++
		}
		return s[l+1 : r] // 本来r也要减减，但由于是左闭右开的区间，所以刚好不用
}

func maxLenOfString(s1, s2 string) string{
    if len(s1) >= len(s2) {
        return s1
    }
    return s2
}

```

### 1143. 最长公共子序列

- 地址：[传送门](https://leetcode.cn/problems/longest-common-subsequence/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 72. 编辑距离

- 地址：[传送门](https://leetcode.cn/problems/edit-distance/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

## \*技巧

### 136. 只出现一次的数字

- 地址：[传送门](https://leetcode.cn/problems/single-number/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 169. 多数元素

- 地址：[传送门](https://leetcode.cn/problems/majority-element/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 75. 颜色分类

- 地址：[传送门](https://leetcode.cn/problems/sort-colors/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 31. 下一个排列

- 地址：[传送门](https://leetcode.cn/problems/next-permutation/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：

### 287. 寻找重复数

- 地址：[传送门](https://leetcode.cn/problems/find-the-duplicate-number/description/?envType=study-plan-v2&envId=top-100-liked)
- 要求：
- 思路：
