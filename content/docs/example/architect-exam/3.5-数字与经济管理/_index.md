---
weight: 5
title: 3.5 数字与经济管理
---

## 课程内容提要
- 1. 图论
  - 最小生成树&emsp;&emsp;&emsp;✅
  - 最短路径&emsp;&emsp;&emsp;&emsp;✅
  - 网络与最大流量&emsp;✅
- 2. 运筹方法
  - 线性规划&emsp;&emsp;&emsp;&emsp;✅
  - 动态规划&emsp;&emsp;&emsp;&emsp;✅✅✅
  - 预测与决策&emsp;&emsp;&emsp;✅
- 3. 数学建模&emsp;&emsp;&emsp;&emsp;✅✅

## 1 图论
### 1.1 最小生成树
[![pCiRVK0.md.png](https://s1.ax1x.com/2023/06/07/pCiRVK0.md.png)](https://imgse.com/i/pCiRVK0)
{{< expand "学霸肯定对了">}}23\
解题思路：按边看，依次找最小的变长将所有节点连接起来，不能有回路，及3-6，3-7，1-2，2-6，4-7，2-5，所以长度至少为2+3+3+4+5+6=23{{< /expand >}}


### 1.2 最短路径
[![pCiRNVO.md.png](https://s1.ax1x.com/2023/06/07/pCiRNVO.md.png)](https://imgse.com/i/pCiRNVO)\
{{< expand "学霸肯定对了">}}81\
21+20+20+8+12=81，其他路径都比81大{{< /expand >}}

### 1.3 网络与最大流量
[![pCiRysP.md.png](https://s1.ax1x.com/2023/06/07/pCiRysP.md.png)](https://imgse.com/i/pCiRysP)
[![pCijwBF.md.png](https://s1.ax1x.com/2023/06/07/pCijwBF.md.png)](https://imgse.com/i/pCijwBF)
[![pCFSJVU.md.png](https://s1.ax1x.com/2023/06/07/pCFSJVU.md.png)](https://imgse.com/i/pCFSJVU)
{{< expand "学霸肯定对了">}}23\
10+6+5+1+1=23{{< /expand >}}

## 2 运筹方法
### 2.1 线性规划
[![pCFSYaF.md.png](https://s1.ax1x.com/2023/06/07/pCFSYaF.md.png)](https://imgse.com/i/pCFSYaF)
{{< expand "学霸肯定对了">}}\
设产品1为X，产品2位Y，立不等式，画图，最优解在顶点处，将顶点都带入目标式子，得到最值{{< /expand >}}

### 2.2 动态规划
[![pCFSUPJ.md.png](https://s1.ax1x.com/2023/06/07/pCFSUPJ.md.png)](https://imgse.com/i/pCFSUPJ)
{{< expand "学霸肯定对了">}}B{{< /expand >}}
### 2.3 预测与决策
[![pCkAUyQ.md.png](https://s1.ax1x.com/2023/06/08/pCkAUyQ.md.png)](https://imgse.com/i/pCkAUyQ)
{{< expand "学霸肯定对了">}}C\
解析：第一个月A=0.5，B=0.5，所以用(0.5,0.5) * 转移矩阵P，得到(0.6,0.4)，第二个月：(0.6,0.4) * 转移矩阵P=(0.64,0.36)，所以选C{{< /expand >}}

[![pCkAaLj.md.png](https://s1.ax1x.com/2023/06/08/pCkAaLj.md.png)](https://imgse.com/i/pCkAaLj)
{{< expand "学霸肯定对了">}}C\
解析：设8点前有A人，来：x人/分钟，检票：y人/分钟，第二问开口最少为M，A+60x=60y * 8，A+40x=40y * 10，联立得到x=4y（来一波人开4个口），带入1式，得到A=240y，A+20x=20y*M，得到M=320y/20y=16{{< /expand >}}
[![pCn8kB4.md.png](https://s1.ax1x.com/2023/06/14/pCn8kB4.md.png)](https://imgse.com/i/pCn8kB4)
[![pCn8VE9.md.png](https://s1.ax1x.com/2023/06/14/pCn8VE9.md.png)](https://imgse.com/i/pCn8VE9)
{{< expand "学霸肯定对了">}}甲乙都会选择降价策略{{< /expand >}}
[![pCkE3nJ.md.png](https://s1.ax1x.com/2023/06/08/pCkE3nJ.md.png)](https://imgse.com/i/pCkE3nJ)\
总结：乐观->大中取大，悲观->小中取大，后悔值->大中取小
[![pCkEa9K.md.png](https://s1.ax1x.com/2023/06/08/pCkEa9K.md.png)](https://imgse.com/i/pCkEa9K)\
水路代价比较小
[![pCkEIBj.md.png](https://s1.ax1x.com/2023/06/08/pCkEIBj.md.png)](https://imgse.com/i/pCkEIBj)
{{< expand "学霸肯定对了">}}B\
加权平均值{{< /expand >}}

## 3 数学建模
[![pCkVuVA.md.png](https://s1.ax1x.com/2023/06/08/pCkVuVA.md.png)](https://imgse.com/i/pCkVuVA)
[![pCkVtbj.md.png](https://s1.ax1x.com/2023/06/08/pCkVtbj.md.png)](https://imgse.com/i/pCkVtbj)
