---
bookCollapseSection: true
weight: 20
title: 6. 面经
---

## 1、运动员赛跑(didi)

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

## 2、设计一个LRU算法(baidu)

&emsp;&emsp;这是leetcode的原题，[传送门](https://leetcode.cn/problems/lru-cache/description/)

## 3、求二叉树的最大深度(baidu)

&emsp;&emsp;这是leetcode的原题，见[传送门](http://localhost:1313/docs/example/leetcode/5.5-%E4%BA%8C%E5%8F%89%E6%A0%91/)的104和175两种解法

## 4、旋转搜索数组

&emsp;&emsp;这是leetcode的原题，见[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#33%E6%90%9C%E7%B4%A2%E6%97%8B%E8%BD%AC%E6%8E%92%E5%BA%8F%E6%95%B0%E7%BB%84)
