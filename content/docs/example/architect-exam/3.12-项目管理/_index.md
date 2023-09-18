---
weight: 12
title: 3.12 项目管理
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

&emsp;&emsp;范围定义的输入包括：项目章程、项目范围管理计划、组织过程资产、批准的变更申请。

[![pC0op1e.md.png](https://s1.ax1x.com/2023/06/30/pC0op1e.md.png)](https://imgse.com/i/pC0op1e)

>例题
[![pCrZdsS.md.png](https://s1.ax1x.com/2023/07/03/pCrZdsS.md.png)](https://imgse.com/i/pCrZdsS)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 3 时间管理

---

&emsp;&emsp;项目时间管理中的过程包括活动定义、活动排序、活动的资源估算、活动历时估算、制定进度计划以及进度控制。

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

&emsp;&emsp;项目的成本管理中，**成本预算**将总的成本估算分配到各项活动和工作包上，来建立一个成本的基线。

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

&emsp;&emsp;配置项的状态通常包括：草稿、正在修改、正式发布。

&emsp;&emsp;配置项主要有以下两大类：

&emsp;&emsp;1、属于产品组成部分的工作成果，各种版本的文档、计算机程序、部件及数据的集合。

&emsp;&emsp;2、属于项目管理和机构支撑过程城产生的文档，如工作计划、项目质量报、项目跟踪报告等。这些文档虽然不是产品的组成部分，但是值得保存。

&emsp;&emsp;软件文档是影响软件可维护性的决定因素。根据文档内容，软件文档又可分为**用户文档**和**系统文档**两类。其中用户文档主要描述**系统功能**和使用方法，并不关心这些功能是怎样实现的，它包括：功能描述文档，安装文档，使用手册，参考手册，操作指南文档。

[![pCsaENR.md.png](https://s1.ax1x.com/2023/07/04/pCsaENR.md.png)](https://imgse.com/i/pCsaENR)

### 6.1 软件工具

&emsp;&emsp;按描述需求定义的方法可将需求分析工具分为**基于自然语言或图形描述的工具**和**基于形式化需求定义语言的工具**。

&emsp;&emsp;项目管理工具用来辅助软件项目管理活动(其中，“指导软件设计人员按软件生存周期各个阶段的适用技术进行设计工作“不是它的活动)。通常项目管理活动包括项目的计划、调度、通信、**成本估算**、资源分配及质量控制等。

&emsp;&emsp;软件系统工具的种类繁多，通常可以按照软件过程活动将软件工具分为软件开发工具、软件维护工具、软件管理和软件支持工具。

&emsp;&emsp;软件开发工具是指用干辅助软件开发过程活动的各种软件。其中，**软件建模工具**是辅助建立软件系统的抽象模型的。常见的软件建模工具包括Rational Rose、Together、WinA&D、OuickUML、EclipseUML等。

&emsp;&emsp;**版本控制工具**属于**软件维护工具**，**软件评价工具**属于**软件管理与软件支持工具**。

&emsp;&emsp;软件测试工具根据工作原理不同可分为静态测试工具和动态测试工具。其中静态测试工具是对代码进行语法扫描，找到不符合编码规范的地方，根据某种质量模型评价代码的质量，生成系统的调用关系图等。它直接对代码进行分析，不需要运行代码，也不需要对代码编译链接和生成可执行文件，静态测试工具可用于**对软件需求、结构设计、详细设计和代码进行评审、走审和审查，也可用于对软件的复杂度分析、数据流分析、控制流分析和接口分析提供支持**，动态测试工具与静态测试工具不同，它需要运行被测试系统，并设置探针，向代码生成的可执行文件中插入检测代码，**可用于软件的覆盖分析和性能分析，也可用于软件的模拟、建模、仿真测试和变异测试等**。

&emsp;&emsp;源代码控制系统 (SCCS)是UNIX系统上的开发项目中使用的源代码和文档文件所做的更改控制的工具。

[![pCsaYCt.md.png](https://s1.ax1x.com/2023/07/04/pCsaYCt.md.png)](https://imgse.com/i/pCsaYCt)

>例题
[![pCsalHH.md.png](https://s1.ax1x.com/2023/07/04/pCsalHH.md.png)](https://imgse.com/i/pCsalHH)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 课后习题

---

todo 习题