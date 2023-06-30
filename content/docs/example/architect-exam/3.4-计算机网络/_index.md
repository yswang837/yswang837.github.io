---
weight: 4
title: 3.4 计算机网络
---

## 课程内容提要 ✌
- 1. TCP/IP协议族
  - DHCP与DNS&emsp;  &emsp;&emsp;  &emsp;✅✅✅
  - TCP与UDP&emsp;&emsp;&emsp;&emsp;  &emsp;✅✅✅
- 2. 网络规划与设计
  - 逻辑设计&emsp;&emsp;&emsp;&emsp;✅✅✅✅
  - 物理设计&emsp;&emsp;&emsp;&emsp;✅✅✅✅
  - 常见的网络设计
    - 层次网络设计&emsp;&emsp;&emsp;✅✅✅
    - 网络冗余设计&emsp;&emsp;&emsp;✅✅
- 3. 网络存储&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;✅
  - 各式网络存储架构
  - 磁盘阵列容量计算
- 4. IPV6&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;✅
- 5. 网络接入技术
- 6. 综合布线&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;✅
- 7. 网络技术扩展
  - 物联网&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;✅
  - 云计算&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;✅

## 1 TCP/IP协议族

---

[![pCebHj1.md.png](https://s1.ax1x.com/2023/06/13/pCebHj1.md.png)](https://imgse.com/i/pCebHj1)
[![pCebqnx.md.png](https://s1.ax1x.com/2023/06/13/pCebqnx.md.png)](https://imgse.com/i/pCebqnx)

### 1.1 TCP与UDP

[![pCebvND.md.png](https://s1.ax1x.com/2023/06/13/pCebvND.md.png)](https://imgse.com/i/pCebvND)

>例题
[![pCeqp3d.md.png](https://s1.ax1x.com/2023/06/13/pCeqp3d.md.png)](https://imgse.com/i/pCeqp3d)
{{< expand "学霸肯定对了">}}C\
A项窗口大小不是固定的，B项前项纠错一般自行纠错，后项纠错一般才要求重发；D项IP不是虚电路，而是走路由器。所以选C{{< /expand >}}

### 1.2 DHCP与DNS

- DNS(Domain Name System)

&emsp;&emsp;在Linux中，DNS的配置文件保存在/etc/resolv.conf。/etc/resolv.conf是DNS客户机的配置文件，用于设置DNS服务器的IP地址及DNS城名，还包含了主机的城名搜索顺序。该文件是由域名解析器 (一个根据主机名解析IP地址的库)使用的配置文件。它的格式比较简单，每行以一个关键字开头，后接一个或多个由空格隔开的参数（一般情况下，系统不会去回写用户程序、用户数据，即便系统去写了这两部分也不会对系统本身造成较大的影响。只有系统对系统本身的目录或关键文件回写异常，才有可能导致较大的影响，严重的会导致系统崩溃。举个例子，linux系统下root账号回写/etc/resolv.conf异常时，可能会导致系统DNS服务异常）。

[![pCmCD41.md.png](https://s1.ax1x.com/2023/06/13/pCmCD41.md.png)](https://imgse.com/i/pCmCD41)
[![pCmxskq.md.png](https://s1.ax1x.com/2023/06/14/pCmxskq.md.png)](https://imgse.com/i/pCmxskq)

>例题
[![pCmxhnJ.md.png](https://s1.ax1x.com/2023/06/14/pCmxhnJ.md.png)](https://imgse.com/i/pCmxhnJ)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCmx7h6.md.png](https://s1.ax1x.com/2023/06/14/pCmx7h6.md.png)](https://imgse.com/i/pCmx7h6)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

- DHCP(Dynamic Host Configuration Protocol)

[![pCmxOje.md.png](https://s1.ax1x.com/2023/06/14/pCmxOje.md.png)](https://imgse.com/i/pCmxOje)

>例题
[![pCmzP9f.md.png](https://s1.ax1x.com/2023/06/14/pCmzP9f.md.png)](https://imgse.com/i/pCmzP9f)
{{< expand "学霸肯定对了">}}A{{< /expand >}}

## 2 网络规划与设计

---

&emsp;&emsp;网络规划与设计包含5个阶段，它们分别是：需求分析、通信规范分析、逻辑网络设计、物理网络设计、实施阶段。这里重点看逻辑网络设计和物理网络设计，需求分析和通信规范分析的产物需要知道。

[![pCmz8u4.md.png](https://s1.ax1x.com/2023/06/14/pCmz8u4.md.png)](https://imgse.com/i/pCmz8u4)

### 2.1 逻辑网络设计

[![pCmzw8K.md.png](https://s1.ax1x.com/2023/06/14/pCmzw8K.md.png)](https://imgse.com/i/pCmzw8K)

### 2.2 物理网络设计

[![pCmz25t.md.png](https://s1.ax1x.com/2023/06/14/pCmz25t.md.png)](https://imgse.com/i/pCmz25t)

>例题
[![pCmzIKg.md.png](https://s1.ax1x.com/2023/06/14/pCmzIKg.md.png)](https://imgse.com/i/pCmzIKg)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCmzban.md.png](https://s1.ax1x.com/2023/06/14/pCmzban.md.png)](https://imgse.com/i/pCmzban)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCmzq5q.md.png](https://s1.ax1x.com/2023/06/14/pCmzq5q.md.png)](https://imgse.com/i/pCmzq5q)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCmzzMF.md.png](https://s1.ax1x.com/2023/06/14/pCmzzMF.md.png)](https://imgse.com/i/pCmzzMF)
{{< expand "学霸肯定对了">}}D{{< /expand >}}

## 2.3 常见的网络设计

- 层次网络设计

[![pCnSpqJ.md.png](https://s1.ax1x.com/2023/06/14/pCnSpqJ.md.png)](https://imgse.com/i/pCnSpqJ)

>例题
[![pCnSAG6.md.png](https://s1.ax1x.com/2023/06/14/pCnSAG6.md.png)](https://imgse.com/i/pCnSAG6)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCnSERK.md.png](https://s1.ax1x.com/2023/06/14/pCnSERK.md.png)](https://imgse.com/i/pCnSERK)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

- 网络冗余设计

[![pCnPdXT.md.png](https://s1.ax1x.com/2023/06/14/pCnPdXT.md.png)](https://imgse.com/i/pCnPdXT)

>例题
[![pCnFcy6.md.png](https://s1.ax1x.com/2023/06/14/pCnFcy6.md.png)](https://imgse.com/i/pCnFcy6)
{{< expand "学霸肯定对了">}}B{{< /expand >}}

## 3 网络存储

---

- 各式网络存储架构

[![pCneIfg.md.png](https://s1.ax1x.com/2023/06/14/pCneIfg.md.png)](https://imgse.com/i/pCneIfg)
[![pCneH6s.md.png](https://s1.ax1x.com/2023/06/14/pCneH6s.md.png)](https://imgse.com/i/pCneH6s)

- 磁盘阵列容量计算

&emsp;&emsp;会计算Raid3和5的磁盘容量就行

[![pCnn2If.md.png](https://s1.ax1x.com/2023/06/14/pCnn2If.md.png)](https://imgse.com/i/pCnn2If)

>例题
[![pCneX7V.md.png](https://s1.ax1x.com/2023/06/14/pCneX7V.md.png)](https://imgse.com/i/pCneX7V)
{{< expand "学霸肯定对了">}}C{{< /expand >}}
[![pCnnhRg.md.png](https://s1.ax1x.com/2023/06/14/pCnnhRg.md.png)](https://imgse.com/i/pCnnhRg)
{{< expand "学霸肯定对了">}}B B

3块80G的Raid5的容量=(3-1) * 80=160G，2块80G和1块40G的磁盘做Raid5的容量=(3-1) * 40=80G{{< /expand >}}

## 4 IPV6

---

- IPV6的特点

[![pCnuCe1.md.png](https://s1.ax1x.com/2023/06/14/pCnuCe1.md.png)](https://imgse.com/i/pCnuCe1)
[![pCnumyd.md.png](https://s1.ax1x.com/2023/06/14/pCnumyd.md.png)](https://imgse.com/i/pCnumyd)
[![pCKQiFI.md.png](https://s1.ax1x.com/2023/06/15/pCKQiFI.md.png)](https://imgse.com/i/pCKQiFI)

- IPV4->IPV6

[![pCnukFK.md.png](https://s1.ax1x.com/2023/06/14/pCnukFK.md.png)](https://imgse.com/i/pCnukFK)

- IPV6地址合法性判断

[![pCnuZSe.md.png](https://s1.ax1x.com/2023/06/14/pCnuZSe.md.png)](https://imgse.com/i/pCnuZSe)

>例题
[![pCKQkfP.md.png](https://s1.ax1x.com/2023/06/15/pCKQkfP.md.png)](https://imgse.com/i/pCKQkfP)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 5 网络接入技术

---

[![pCKQVl8.md.png](https://s1.ax1x.com/2023/06/15/pCKQVl8.md.png)](https://imgse.com/i/pCKQVl8)
[![pCKQ8pV.md.png](https://s1.ax1x.com/2023/06/15/pCKQ8pV.md.png)](https://imgse.com/i/pCKQ8pV)

## 6 综合布线

---

[![pCKQNm4.md.png](https://s1.ax1x.com/2023/06/15/pCKQNm4.md.png)](https://imgse.com/i/pCKQNm4)
[![pCKQwkR.md.png](https://s1.ax1x.com/2023/06/15/pCKQwkR.md.png)](https://imgse.com/i/pCKQwkR)
>例题
[![pCKQBfx.md.png](https://s1.ax1x.com/2023/06/15/pCKQBfx.md.png)](https://imgse.com/i/pCKQBfx)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 7 网络技术扩展

---

### 7.1 物联网

[![pCKQI9P.md.png](https://s1.ax1x.com/2023/06/15/pCKQI9P.md.png)](https://imgse.com/i/pCKQI9P)
[![pCKQgne.md.png](https://s1.ax1x.com/2023/06/15/pCKQgne.md.png)](https://imgse.com/i/pCKQgne)

- 感知层的关键技术

[![pCKQ7jS.md.png](https://s1.ax1x.com/2023/06/15/pCKQ7jS.md.png)](https://imgse.com/i/pCKQ7jS)
[![pCKQbng.md.png](https://s1.ax1x.com/2023/06/15/pCKQbng.md.png)](https://imgse.com/i/pCKQbng)

>例题
[![pCKQqBQ.md.png](https://s1.ax1x.com/2023/06/15/pCKQqBQ.md.png)](https://imgse.com/i/pCKQqBQ)
{{< expand "学霸肯定对了">}}D{{< /expand >}}

### 7.2 云计算

[![pCKllHH.md.png](https://s1.ax1x.com/2023/06/15/pCKllHH.md.png)](https://imgse.com/i/pCKllHH)

>例题
[![pCKldKS.md.png](https://s1.ax1x.com/2023/06/15/pCKldKS.md.png)](https://imgse.com/i/pCKldKS)
{{< expand "学霸肯定对了">}}A{{< /expand >}}

## 课后习题

---

todo 计算机网络习题
