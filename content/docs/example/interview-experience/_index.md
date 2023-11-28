---
bookCollapseSection: true
weight: 20
title: 6. 面经
---

## 1、运动员赛跑

&emsp;&emsp;10个运动员参加百米赛跑，裁判一声枪响后运动员出发，按成绩升序输出成绩、排名、运动员编号。考点是golang的并发

```go
package main

import (
	"fmt"
	"sort"
	"sync"
	"time"
)

type RunnerResult struct {
	ID      int
	Elapsed time.Duration
}

type ByElapsed []RunnerResult

func (a ByElapsed) Len() int           { return len(a) }
func (a ByElapsed) Less(i, j int) bool { return a[i].Elapsed < a[j].Elapsed }
func (a ByElapsed) Swap(i, j int)      { a[i], a[j] = a[j], a[i] }

func raceRunner(id int, signal chan struct{}, wg *sync.WaitGroup, results chan RunnerResult) {
	startTime := time.Now()
	<-signal // 等待裁判的信号
	finishTime := time.Now()

	// 计算耗时
	elapsed := finishTime.Sub(startTime)

	// 通知比赛结果
	result := RunnerResult{
		ID:      id,
		Elapsed: elapsed,
	}
	results <- result

	wg.Done()
}

func main() {
	const runners = 10
	signal := make(chan struct{})
	results := make(chan RunnerResult, runners)
	var wg sync.WaitGroup

	// 启动运动员
	for i := 1; i <= runners; i++ {
		wg.Add(1)
		go raceRunner(i, signal, &wg, results)
	}

	// 等待一段时间模拟裁判准备就绪
	close(signal) // 裁判发出开始比赛的信号

	// 等待所有运动员完成比赛
	wg.Wait()
	close(results)

	var raceResults []RunnerResult
	for res := range results {
		raceResults = append(raceResults, res)
	}

	// 对结果按耗时进行排序（升序）
	sort.Sort(ByElapsed(raceResults))

	// 输出按耗时升序排列的结果
	fmt.Println("比赛结果及耗时情况（按耗时升序）：")
	for i, res := range raceResults {
		fmt.Printf("第%d名是运动员%d 耗时：%v\n", i+1, res.ID, res.Elapsed)
	}
}

```
