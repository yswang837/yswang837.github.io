---
weight: 13
title: 3.13 项目管理
---
## 课程内容提要

- 1. 立项管理&emsp;&emsp;&emsp;✅
- 2. 范围管理&emsp;&emsp;&emsp;✅✅
- 3. 时间管理&emsp;&emsp;&emsp;✅✅✅✅
- 4. 成本管理&emsp;&emsp;&emsp;✅
- 5. 软件质量管理&emsp;✅✅
- 6. 软件配置管理&emsp;✅✅

## 1 立项管理

### 1.1 盈亏平衡分析

---

[![pC0IL01.md.png](https://s1.ax1x.com/2023/06/30/pC0IL01.md.png)](https://imgse.com/i/pC0IL01)

## 2 范围管理

---

[![pC0op1e.md.png](https://s1.ax1x.com/2023/06/30/pC0op1e.md.png)](https://imgse.com/i/pC0op1e)

>例题
[![pCrZdsS.md.png](https://s1.ax1x.com/2023/07/03/pCrZdsS.md.png)](https://imgse.com/i/pCrZdsS)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 3 时间管理

---

[![pCrUNrQ.md.png](https://s1.ax1x.com/2023/07/03/pCrUNrQ.md.png)](https://imgse.com/i/pCrUNrQ)
>例题
[![pCsed2t.md.png](https://s1.ax1x.com/2023/07/04/pCsed2t.md.png)](https://imgse.com/i/pCsed2t)
{{< expand "学霸肯定对了">}}B{{< /expand >}}

[![pCsmvfs.md.png](https://s1.ax1x.com/2023/07/04/pCsmvfs.md.png)](https://imgse.com/i/pCsmvfs)

### 3.1 单代号网络图

&emsp;&emsp;关键路径是最早完成时间下的最长的路径。关键路径可以有多条，关键路径的条数越少越好。

&emsp;&emsp;ES和EF是正向推导过程。关键路径需要反推才能得到。总时差=LS-ES，总时差为0的节点连接起来就是关键路径。

&emsp;&emsp;自由时差小于等于总时差。当前节点的自由时差=紧后活动的ES-当前活动的EF。自由时差会影响紧后活动（压缩了别人的自由）

[![pCsefx0.md.png](https://s1.ax1x.com/2023/07/04/pCsefx0.md.png)](https://imgse.com/i/pCsefx0)

### 3.2 双代号网络图

&emsp;&emsp;虚线不能去掉，2->3的距离为0，但不能删掉，因为A和B都是E的紧前活动，也不能合并。

[![pCsmNeU.md.png](https://s1.ax1x.com/2023/07/04/pCsmNeU.md.png)](https://imgse.com/i/pCsmNeU)
[![pCsmq0S.md.png](https://s1.ax1x.com/2023/07/04/pCsmq0S.md.png)](https://imgse.com/i/pCsmq0S)

### 3.3 甘特图

&emsp;&emsp;细线表示计划，粗线表示当前进度。

[![pCsnhHU.md.png](https://s1.ax1x.com/2023/07/04/pCsnhHU.md.png)](https://imgse.com/i/pCsnhHU)

>例题
[![pCsnjHO.md.png](https://s1.ax1x.com/2023/07/04/pCsnjHO.md.png)](https://imgse.com/i/pCsnjHO)
{{< expand "学霸肯定对了">}}C

[![pCsukKP.md.png](https://s1.ax1x.com/2023/07/04/pCsukKP.md.png)](https://imgse.com/i/pCsukKP)

也就是求D的总时差{{< /expand >}}
[![pCsuEb8.md.png](https://s1.ax1x.com/2023/07/04/pCsuEb8.md.png)](https://imgse.com/i/pCsuEb8)
{{< expand "学霸肯定对了">}}A A

正常进度=直接费用+间接费用=55+12*5=115天，赶工进度：压缩D两天，压缩A两天，B和D同时压1天，也就是：55+4+8+4+35=106，需要7天。{{< /expand >}}

## 4 成本管理

---

[![pCsNCGV.md.png](https://s1.ax1x.com/2023/07/04/pCsNCGV.md.png)](https://imgse.com/i/pCsNCGV)

### 4.1 挣值分析

[![pCsU1f0.md.png](https://s1.ax1x.com/2023/07/04/pCsU1f0.md.png)](https://imgse.com/i/pCsU1f0)

>例题
[![pCsU20H.md.png](https://s1.ax1x.com/2023/07/04/pCsU20H.md.png)](https://imgse.com/i/pCsU20H)
{{< expand "学霸肯定对了">}}C{{< /expand >}}
>案例分析例题
[![pC2sOMQ.md.png](https://s1.ax1x.com/2023/07/10/pC2sOMQ.md.png)](https://imgse.com/i/pC2sOMQ)
[![pC2sxZn.md.png](https://s1.ax1x.com/2023/07/10/pC2sxZn.md.png)](https://imgse.com/i/pC2sxZn)
{{< expand "学霸肯定对了">}}
说明：活动E不是关键路径上的活动，不应该加班。

[![pC27GIU.md.png](https://s1.ax1x.com/2023/07/10/pC27GIU.md.png)](https://imgse.com/i/pC27GIU)

[![pC27oo8.md.png](https://s1.ax1x.com/2023/07/10/pC27oo8.md.png)](https://imgse.com/i/pC27oo8)

[![pC27Xyn.md.png](https://s1.ax1x.com/2023/07/10/pC27Xyn.md.png)](https://imgse.com/i/pC27Xyn)
{{< /expand >}}
[![pC27jLq.md.png](https://s1.ax1x.com/2023/07/10/pC27jLq.md.png)](https://imgse.com/i/pC27jLq)
{{< expand "学霸肯定对了">}}

松弛时间：总时差，关键路径上的总时差为0，反之亦然。

[![pC2Hkl9.md.png](https://s1.ax1x.com/2023/07/10/pC2Hkl9.md.png)](https://imgse.com/i/pC2Hkl9)

[![pC2HEO1.md.png](https://s1.ax1x.com/2023/07/10/pC2HEO1.md.png)](https://imgse.com/i/pC2HEO1)

[![pC2HCYF.md.png](https://s1.ax1x.com/2023/07/10/pC2HCYF.md.png)](https://imgse.com/i/pC2HCYF)
{{< /expand >}}

## 5 软件质量管理

---

[![pCsUfAA.md.png](https://s1.ax1x.com/2023/07/04/pCsUfAA.md.png)](https://imgse.com/i/pCsUfAA)

### 5.1 质量保证方式CMMI

&emsp;&emsp;软件过程改进：CMMI

[![pCsa9jU.md.png](https://s1.ax1x.com/2023/07/04/pCsa9jU.md.png)](https://imgse.com/i/pCsa9jU)

## 6 软件配置管理

---

[![pCsaENR.md.png](https://s1.ax1x.com/2023/07/04/pCsaENR.md.png)](https://imgse.com/i/pCsaENR)

### 6.1 软件工具

[![pCsaYCt.md.png](https://s1.ax1x.com/2023/07/04/pCsaYCt.md.png)](https://imgse.com/i/pCsaYCt)

>例题
[![pCsalHH.md.png](https://s1.ax1x.com/2023/07/04/pCsalHH.md.png)](https://imgse.com/i/pCsalHH)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

### 6.2 版本控制

[![pCsarUs.md.png](https://s1.ax1x.com/2023/07/04/pCsarUs.md.png)](https://imgse.com/i/pCsarUs)

## 课后习题

---

todo 习题