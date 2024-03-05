---
weight: 1
title: 5.7 面经
---

## 1、运动员赛跑(滴滴)

&emsp;&emsp;9个运动员参加110米跨栏比赛，裁判一声枪响后运动员出发，按成绩升序输出排名、运动员编号、成绩。考点是golang的并发

```go
package main

import (
	"fmt"
	"math/rand"
	"sort"
	"sync"
	"time"
)

type resultItem struct {
	Id    int
	Score float32
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

type race struct {
	total  int
	runner int
	wg     *sync.WaitGroup
	judge  chan struct{}
	result chan resultItem
}

func newRace(total, runner int) *race {
	return &race{
		total:  total,
		runner: runner,
		wg:     &sync.WaitGroup{},
		judge:  make(chan struct{}, 1),
		result: make(chan resultItem, runner),
	}
}

func main() {
	r := newRace(110, 9)
	r.judge <- struct{}{}
	time.Sleep(time.Second)
	<-r.judge
	for i := 0; i < r.runner; i++ {
		r.wg.Add(1)
		go r.run(i)
	}
	r.wg.Wait()
	close(r.judge)
	close(r.result)
	var raceResult []resultItem
	for ret := range r.result {
		raceResult = append(raceResult, ret)
	}
	sort.Sort(sortResult(raceResult))
	fmt.Printf("%d米跨栏比赛成绩如下:\n", r.total)
	for i, val := range raceResult {
		fmt.Printf("第%d名，编号是%d，耗时%.2fs\n", i+1, val.Id+1, val.Score)
	}
}

func (r *race) run(i int) {
	speed := 5 * (rand.Float32() + 2)
	r.result <- resultItem{i, float32(r.total) / speed}
	r.wg.Done()
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

## 9、反转链表(百度)

&emsp;&emsp;这是leetcode的hot-100原题，见[传送门](https://yswang837.github.io/docs/example/leetcode/5.1-hot100/#206%E5%8F%8D%E8%BD%AC%E9%93%BE%E8%A1%A8)

## 10、go的两个协程交替打印奇数偶数(小米)

```go
package main

import (
	"fmt"
	"sync"
)

type printGames struct {
	// 创建两个channel，用于控制奇数和偶数的打印
	oddChan  chan bool
	evenChan chan bool
	wg       *sync.WaitGroup
}

func newPrintGames() *printGames {
	return &printGames{
		oddChan:  make(chan bool),
		evenChan: make(chan bool),
		wg:       &sync.WaitGroup{},
	}
}

func main() {
	p := newPrintGames()
	p.wg.Add(2)
	// 启动第一个goroutine打印奇数
	go func() {
		defer p.wg.Done()
		for i := 1; i <= 100; i += 2 {
			<-p.oddChan // 等待奇数信号
			fmt.Printf("协程%d: %d\n", 1, i)
			p.evenChan <- true // 发送偶数信号
		}
	}()

	// 启动第二个goroutine打印偶数
	go func() {
		defer p.wg.Done()
		for i := 2; i <= 100; i += 2 {
			<-p.evenChan // 等待偶数信号
			fmt.Printf("协程%d: %d\n", 2, i)
			if i == 100 {
				return
			}
			p.oddChan <- true // 发送奇数信号
		}
	}()

	// 初始化第一个信号，让第一个goroutine开始打印
	p.oddChan <- true

	// 等待所有goroutine完成
	p.wg.Wait()
	close(p.oddChan)
	close(p.evenChan)
}

```
