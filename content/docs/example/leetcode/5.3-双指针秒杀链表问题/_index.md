---
weight: 1
title: 5.3 双指针秒杀链表问题
---

&emsp;&emsp;

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
