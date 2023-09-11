---
weight: 5
title: "5) 软件质量属性"
---


# 软件质量属性

&emsp;&emsp;最常见的质量属性分别是：性能(Performance)、可用性(Availability)、可修改性(Modifiability)、安全性(Security)、可测试性(Testability)、易用性(Usability)等。

[![pCw8H8s.md.png](https://s1.ax1x.com/2023/06/29/pCw8H8s.md.png)](https://imgse.com/i/pCw8H8s)

## 1 性能

---

&emsp;&emsp;性能 (performance) 是指系统的响应能力，即要经过多长时间才能对某个事件做出响应，或者在某段时间内系统所能处理的事件的个数。例如：

&emsp;&emsp;1、同时支持1000并发；

&emsp;&emsp;2、响应时间小于1ms；

&emsp;&emsp;3、显示分辨率达到4k；

[![p9R7JVs.md.png](https://s1.ax1x.com/2023/05/17/p9R7JVs.md.png)](https://imgse.com/i/p9R7JVs)

## 2 可用性

---

&emsp;&emsp;可用性(availability)是系统能够正常运行的时间比例。经常用两次故障之间的时间长度或在出现故障时系统能够恢复正常的速度来表示。例如：

&emsp;&emsp;1、主服务器故障，一分钟内切换至备用服务器；

&emsp;&emsp;2、系统故障，1小时内修复；

&emsp;&emsp;3、系统支持 7 x 24 小时工作。

[![p9R7rqJ.md.png](https://s1.ax1x.com/2023/05/17/p9R7rqJ.md.png)](https://imgse.com/i/p9R7rqJ)

## 3 安全性

&emsp;&emsp;安全性(security)是指系统在向合法用户提供服务的同时能够阻止非授权用户使用的企图或拒绝服务的能力。安全性又可划分为机密性、完整性、不可否认性及可控性等特性。例如：

&emsp;&emsp;1、可抵御sql注入攻击；

&emsp;&emsp;2、对计算机的操作都有完整记录；

&emsp;&emsp;3、用户信息数据库授权必须保证99.9%可用。

&emsp;&emsp;安全性还有个战术：限制访问。

[![p9R7vQS.md.png](https://s1.ax1x.com/2023/05/17/p9R7vQS.md.png)](https://imgse.com/i/p9R7vQS)

## 4 可修改性

---

&emsp;&emsp;可修改性(modifiability)是指能够快速地以较高的性价比对系统进行变更的能力。通常以某些具体的变更为基准，通过考察这些变更的代价衡量可修改性。例如：

&emsp;&emsp;1、更改系统报表模块，2人在两周内必须完成；

&emsp;&emsp;2、对Web界面风格进行修改，修改必须在2个月内完成。

&emsp;&emsp;可修改性还有个战术：接口实现分离。

&emsp;&emsp;可修改性是指能够快速地以较高的性能价格比对系统进行变更的能力。包括可维护性、可扩展性、结构重组、可移植性4个方面。注意可变性不是它要考虑的范围。

[![p9RHhYq.md.png](https://s1.ax1x.com/2023/05/17/p9RHhYq.md.png)](https://imgse.com/i/p9RHhYq)

>例题
[![p9Rb9XD.md.png](https://s1.ax1x.com/2023/05/17/p9Rb9XD.md.png)](https://imgse.com/i/p9Rb9XD)
{{< expand "学霸肯定对了">}}A D A{{< /expand >}}
[![p9RbMng.md.png](https://s1.ax1x.com/2023/05/17/p9RbMng.md.png)](https://imgse.com/i/p9RbMng)
{{< expand "学霸肯定对了">}}B C A C C A{{< /expand >}}

## 基本不考的几个属性

---

&emsp;&emsp;易用性：界面友好，新用户学习系统使用时间不超过2小时。

&emsp;&emsp;可测试性：提供远程调试接口，支持远程调试。

&emsp;&emsp;可靠性、功能性、可变性、互操作性。

&emsp;&emsp;可伸缩性：当用户数和数据量增加时，软件系统维持高服务质量的能力。
