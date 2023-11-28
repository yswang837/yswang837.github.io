---
weight: 1
title: 1 golang并发编程
---

## 目录 ✌

---

&emsp;&emsp;并发错误的一般排查思路：可通过加锁来排查。

&emsp;&emsp;多线程程序在一个核的cpu上运行，就是并发。多线程程序在多个核的cpu上运行，就是并行。

&emsp;&emsp;go主张通过通讯来共享内存，但也支持通过共享内存来通讯；前者的数据结构主要是channel+goroutine，后者是互斥锁，读写锁+goroutine

## 