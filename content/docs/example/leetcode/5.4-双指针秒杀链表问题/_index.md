---
weight: 1
title: 5.4 双指针秒杀链表问题
---

## 双指针秒杀链表问题

&emsp;&emsp;相比于双指针秒杀数组问题来说，双指针秒杀链表问题更有技巧性。比如说，经常会定义虚拟头结点dummy，因为可能会涉及到删除head节点这类题目。

### 83.删除排序链表中的重复元素

[传送门](https://leetcode.cn/problems/remove-duplicates-from-sorted-list/)

```go
func deleteDuplicates(head *ListNode) *ListNode {
    if head == nil {
        return nil
    }
    slow, fast := head, head
    for fast != nil {
        if fast.Val != slow.Val {
            slow = slow.Next
            slow.Val = fast.Val
        }
        fast = fast.Next
    }
    slow.Next = nil
    return head
}
//           f
//     s
// 1 1 2 3 3
// 1 2 2 3 3
// 1 2 3 3 3
```

### 876.链表的中间结点

[传送门](https://leetcode.cn/problems/middle-of-the-linked-list/description/)

```go
func middleNode(head *ListNode) *ListNode {
    if head == nil {
        return nil
    }
    slow, fast := head, head
    for fast != nil && fast.Next != nil {
        fast = fast.Next.Next
        slow = slow.Next
    }
    return slow
}
```

### 140.训练计划II(剑指Offer)

[传送门](https://leetcode.cn/problems/lian-biao-zhong-dao-shu-di-kge-jie-dian-lcof/description/)

```go
func trainingPlan(head *ListNode, cnt int) *ListNode {
    if head == nil {
        return nil
    }
    slow, fast := head, head
    for i:=0; i<cnt; i++ {
        fast = fast.Next
    }
    for fast != nil {
        fast = fast.Next
        slow = slow.Next
    }
    return slow
}
```

### 19.删除链表的倒数第N个结点

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#19-%E5%88%A0%E9%99%A4%E9%93%BE%E8%A1%A8%E7%9A%84%E5%80%92%E6%95%B0%E7%AC%AC-n-%E4%B8%AA%E7%BB%93%E7%82%B9)

### 21.合并两个有序链表

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#21-%E5%90%88%E5%B9%B6%E4%B8%A4%E4%B8%AA%E6%9C%89%E5%BA%8F%E9%93%BE%E8%A1%A8)

### 86.分隔链表

[传送门](https://leetcode.cn/problems/partition-list/description/)

```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func partition(head *ListNode, x int) *ListNode {
    if head == nil {
        return nil
    }
    dummy1 := &ListNode{-1,nil}
    dummy2 := &ListNode{-1,nil}
    cur1 := dummy1
    cur2 := dummy2

    for head != nil {
        if head.Val < x {
            cur1.Next = head
            cur1 = cur1.Next            
        }else {
            cur2.Next = head
            cur2 = cur2.Next
        }
        // head = head.Next // 这样写最后链表可能成环。5 - > 2，当前head在5，head往下挪后，还有指针指向了2，最后将两个链表连接成一个链表时，可能会形成环。所以需要将next指针置空，下面3行，可简写为一行 // head, head.Next = head.Next, nil
        tmp := head.Next
        head.Next = nil
        head = tmp
    }

    cur1.Next = dummy2.Next
    return dummy1.Next
}
```

### 23.合并k个有序链表

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#23-%E5%90%88%E5%B9%B6-k-%E4%B8%AA%E5%8D%87%E5%BA%8F%E9%93%BE%E8%A1%A8)

### 141.环形链表

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#141-%E7%8E%AF%E5%BD%A2%E9%93%BE%E8%A1%A8)

### 142.环形链表II

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#142-%E7%8E%AF%E5%BD%A2%E9%93%BE%E8%A1%A8-ii)

### 160.相交链表

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#160-%E7%9B%B8%E4%BA%A4%E9%93%BE%E8%A1%A8)
