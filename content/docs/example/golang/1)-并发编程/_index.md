---
weight: 1
title: 1 并发
---

## 目录 ✌

---

# 通道用例大全

&emsp;&emsp;[参考链接](https://www.bookstack.cn/books/golang101-1.21.a)

&emsp;&emsp;希望这篇文章能够说服你接受下面的观点：

&emsp;&emsp;1、使用通道进行异步和并发编程是简单和惬意的；

&emsp;&emsp;2、通道技术比很多其它语言采用的其它并发方案有着更多的应用场景和更多的使用变种。

## 1、将通道用做future/promise

### 1.1 返回单向接收通道作为函数返回值

```go
package main

import (
	"fmt"
	"math/rand"
	"time"
)

func main() {
	start := time.Now()
	a, b := longTask(), longTask()
	fmt.Println(sumOfSquare(<-a, <-b))
	fmt.Println(time.Since(start))
}

func longTask() <-chan int {
	ret := make(chan int, 1)
	go func() { // 开启协程，执行时间将从6s减少为3s
		time.Sleep(3 * time.Second) // 模拟一个长任务
		ret <- rand.Intn(100)
	}()
	return ret
}

func sumOfSquare(i, j int) int {
	return i*i + j*j
}
```

### 1.2 将单向发送通道类型用做函数实参

```go
package main

import (
	"fmt"
	"math/rand"
	"time"
)

func main() {
	start := time.Now()
	a:= make(chan int, 2)
	longTask(a)
	longTask(a)
	fmt.Println(sumOfSquare(<-a, <-a))
	fmt.Println(time.Since(start))
}

func longTask(task chan int) {
	go func() { // 开启协程，执行时间将从6s减少为3s
		time.Sleep(3 * time.Second) // 模拟一个长任务
		task <- rand.Intn(100)
	}()
}

func sumOfSquare(i, j int) int {
	return i*i + j*j
}

```

### 1.3 响应最快的协程

```go
package main

import (
	"fmt"
	"math/rand"
	"time"
)

func source(c chan<- int32) {
	ra, rb := rand.Int31(), rand.Intn(3)+1
	time.Sleep(time.Duration(rb) * time.Second) // 模拟不同的生产者的耗时睡眠1秒/2秒/3秒
	c <- ra
}
func main() {
	startTime := time.Now()
	c := make(chan int32, 5) // 必须用一个缓冲通道
	for i := 0; i < cap(c); i++ {
		go source(c)
	}
	rnd := <-c // 只响应了第一个协程的执行结果
	fmt.Println(time.Since(startTime))
	fmt.Println(rnd)
}

```

## 2 使用通道实现通知

&emsp;&emsp;通知只关心是否发生，并不关心通知的值，所以通常用不占空间的空struct。

### 2.1 发送一个值给通道实现单对单通知

```go
package main

import (
	"fmt"
	"math/rand"
	"os"
	"sort"
)

func main() {
	values := make([]byte, 32*1024*1024) // 32MB
	if _, err := rand.Read(values); err != nil {
		fmt.Println(err.Error())
		os.Exit(-1)
	}
	fmt.Println("排序前....", values[0], values[len(values)-1])
	done := make(chan struct{}) // 缓冲或者非缓冲通道都行
	go func() {
		sort.Slice(values, func(i, j int) bool {
			return values[i] < values[j]
		})
		done <- struct{}{}
	}()

	// 并发做一下别的事情

	// 排序完成
	<-done
	fmt.Println("排序后....", values[0], values[len(values)-1])
}

```
