---
weight: 1
title: 5.7 面经
---

## 1、运动员赛跑(滴滴)

&emsp;&emsp;10个运动员参加百米赛跑，裁判一声枪响后运动员出发，按成绩升序输出成绩、排名、运动员编号。考点是golang的并发

```go
package main

import (
	"fmt"
	"sort"
	"sync"
	"time"
)

type resultItem struct {
	Id    int
	Score time.Duration
}

type sortResult []resultItem

func (s sortResult) Len() int {
	return len(s)
}

func (s sortResult) Less(i, j int) bool {
	return s[i].Score < s[j].Score
}

func (s sortResult) Swap(i, j int) {
	s[i], s[j] = s[j], s[i]
}

func main() {
	const runner = 10
	wg := &sync.WaitGroup{}
	result := make(chan resultItem, runner)
	judge := make(chan struct{}, 1)
	judge <- struct{}{}
	time.Sleep(time.Second)
	<-judge
	for i := 0; i < runner; i++ {
		wg.Add(1)
		go run(i, wg, result)
	}
	wg.Wait()
	close(judge)
	close(result)
	var raceResult []resultItem
	for r := range result {
		raceResult = append(raceResult, r)
	}
	sort.Sort(sortResult(raceResult))
	for i, val := range raceResult {
		fmt.Printf("第%d名，编号是%d,耗时%+v\n", i+1, val.Id, val.Score)
	}
}

func run(i int, wg *sync.WaitGroup, result chan resultItem) {
	start := time.Now()
	result <- resultItem{i, time.Since(start)}
	wg.Done()
}
```

## 2、设计一个LRU算法(百度, 阿里云)

&emsp;&emsp;这是leetcode的hot-100原题，[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#146lru%E7%BC%93%E5%AD%98)

## 3、求二叉树的最大深度(百度)

&emsp;&emsp;这是leetcode的hot-100原题，见[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#104-%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E6%9C%80%E5%A4%A7%E6%B7%B1%E5%BA%A6)

## 4、旋转搜索数组(字节)

&emsp;&emsp;这是leetcode的hot-100原题，见[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#33%E6%90%9C%E7%B4%A2%E6%97%8B%E8%BD%AC%E6%8E%92%E5%BA%8F%E6%95%B0%E7%BB%84)

## 5、有效的括号(美团)

&emsp;&emsp;这是leetcode的hot-100原题，见[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#20-%E6%9C%89%E6%95%88%E7%9A%84%E6%8B%AC%E5%8F%B7)

## 6、从前序与中序遍历序列构造二叉树(滴滴)

&emsp;&emsp;这是leetcode的hot-100原题，见[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#105-%E4%BB%8E%E5%89%8D%E5%BA%8F%E4%B8%8E%E4%B8%AD%E5%BA%8F%E9%81%8D%E5%8E%86%E5%BA%8F%E5%88%97%E6%9E%84%E9%80%A0%E4%BA%8C%E5%8F%89%E6%A0%91)，这个题与“从后序与中序遍历序列构造二叉树”如出一辙。

## 7、三数之和(滴滴)

&emsp;&emsp;这是leetcode的hot-100原题，见[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#15%E4%B8%89%E6%95%B0%E4%B9%8B%E5%92%8C)

## 8、两数相加(滴滴)

&emsp;&emsp;这是leetcode的hot-100原题，见[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#2-%E4%B8%A4%E6%95%B0%E7%9B%B8%E5%8A%A0)
