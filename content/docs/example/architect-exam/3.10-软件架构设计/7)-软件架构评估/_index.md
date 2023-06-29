---
weight: 7
title: "7) 软件架构评估"
---

# 软件架构评估

问题：

1、为什么要进行架构评估？

2、架构评估到底评什么？

3、架构评估怎么评？

## 1. 名词解释

---

**敏感点**：是一个或多个构件 (和/或构件之间的关系)的特性。

**权衡点**：是影响多个质量属性的特性，是多个质量属性的敏感点。

**风险点**：是指架构设计中潜在的、存在问题的架构决策所带来的隐患。

**非风险点**：是指不会带来隐患，一般以“xxx要求是可以实现 (或接受)的”方式表达。

[![p9vUlvT.png](https://s1.ax1x.com/2023/05/31/p9vUlvT.png)](https://imgse.com/i/p9vUlvT)

## 2、架构评估方法

---

&emsp;&emsp;架构评估方法包含3种方式：基于问卷调查的方式、基于度量的方式、**基于场景的方式**。
[![p9vUGb4.md.png](https://s1.ax1x.com/2023/05/31/p9vUGb4.md.png)](https://imgse.com/i/p9vUGb4)

### 2.1 基于场景的评估方法

- 什么是场景

[![pCwY7Pe.md.png](https://s1.ax1x.com/2023/06/29/pCwY7Pe.md.png)](https://imgse.com/i/pCwY7Pe)

&emsp;&emsp;基于场景的评估方法包含3种：**软件架构分析法**(SAAM)、**架构权衡分析法**(ATAM)、成本效益分析法(CBAM)。

- SAAM：最初用于分析架构**可修改性**，后扩展到其他质量属性。

&emsp;&emsp;问题描述、需求说明和架构描述作为SAAM的输入。

[![p9vUta9.md.png](https://s1.ax1x.com/2023/05/31/p9vUta9.md.png)](https://imgse.com/i/p9vUta9)

- ATAM：在SAAM的基础上发展起来的，主要针对性能、实用性、安全性和可修改性，在系统开发之前，对这些**质量属性进行评价和折中**。

[![p9vUN5R.md.png](https://s1.ax1x.com/2023/05/31/p9vUN5R.md.png)](https://imgse.com/i/p9vUN5R)

>例题
[![p9vUaP1.md.png](https://s1.ax1x.com/2023/05/31/p9vUaP1.md.png)](https://imgse.com/i/p9vUaP1)
{{< expand "学霸肯定对了">}}D B{{< /expand >}}
[![p9vUd8x.md.png](https://s1.ax1x.com/2023/05/31/p9vUd8x.md.png)](https://imgse.com/i/p9vUd8x)
{{< expand "学霸肯定对了">}}D{{< /expand >}}
[![p9vUw26.md.png](https://s1.ax1x.com/2023/05/31/p9vUw26.md.png)](https://imgse.com/i/p9vUw26)
{{< expand "学霸肯定对了">}}C C{{< /expand >}}

### 2.2 质量效用数

&emsp;&emsp;M:middle,L:low,H:high

[![p9vU0xK.md.png](https://s1.ax1x.com/2023/05/31/p9vU0xK.md.png)](https://imgse.com/i/p9vU0xK)
