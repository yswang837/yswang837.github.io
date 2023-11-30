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

[传送门](https://leetcode.cn/problems/remove-nth-node-from-end-of-list/)

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

### 21.合并两个有序链表

[传送门](https://leetcode.cn/problems/merge-two-sorted-lists/)

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

[传送门](https://leetcode.cn/problems/merge-k-sorted-lists/description/)

- 思路1：我们已经实现了合并两个有序链表的函数，合并k个有序链表，也就扩展下就行了，但时间复杂度有点高，不过还是通过了，代码如下：

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

- 思路2：使用优先级队列（二叉堆），这个代码后面再补充，https://labuladong.github.io/algo/di-ling-zh-bfe1b/shuang-zhi-0f7cc/

```go

```

### 141.环形链表

[传送门](https://leetcode.cn/problems/linked-list-cycle/description/)

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

### 142.环形链表II

[传送门](https://leetcode.cn/problems/linked-list-cycle-ii/description/)

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

### 160.相交链表

[传送门](https://leetcode.cn/problems/intersection-of-two-linked-lists/description/)

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
