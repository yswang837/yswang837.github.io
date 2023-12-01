---
weight: 1
title: 5.6 经典数据结构
---

## 1、LRU

[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#146lru%E7%BC%93%E5%AD%98)

```go
type Node struct {
    key, val int
    prev, next *Node
}

type LRUCache struct {
    capacity int
    head, tail *Node
    hashMap map[int]*Node
}


func Constructor(capacity int) LRUCache {
    head, tail := &Node{}, &Node{}
    head.next = tail
    tail.prev = head
    return LRUCache {
        capacity: capacity,
        hashMap: map[int]*Node{},
        head: head,
        tail: tail,
    }
}

func (this *LRUCache) Get(key int) int {
    if node, ok := this.hashMap[key];ok {
        remove(node)
        insert(this.head,node)
        return node.val
    }
    return -1
}

func remove(node *Node) {
    // prev <-> node <-> next
    node.prev.next = node.next
    node.next.prev = node.prev
}

func insert(head, node *Node) {
    // head <-> next
    // head <-> node <-> next
    next := head.next
    head.next = node
    node.prev = head
    node.next = next
    next.prev = node
}


func (this *LRUCache) Put(key int, value int)  {
    if node, ok := this.hashMap[key];ok {
        remove(node)
        node.val = value
        insert(this.head,node)
    }else {
        newNode := &Node{key:key, val:value}
        insert(this.head,newNode)
        this.hashMap[key] = newNode
        if len(this.hashMap) > this.capacity {
            lastNode := this.tail.prev
            remove(lastNode)
            delete(this.hashMap,lastNode.key)
        }
    }
}

```
