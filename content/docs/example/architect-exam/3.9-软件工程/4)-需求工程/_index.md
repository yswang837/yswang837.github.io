# 4. 需求工程 ✌

## 4.1 概述

&emsp;&emsp;软件需求是指用户对系统在功能、行为、性能、设计约束等方面的期望。

&emsp;&emsp;软件需求是指用户解决问题或达到目标所需的条件或能力，是系统或系统部件要满足合同、标准、规范或其他正式规定文档所需具有的条件或能力，以及反映这些条件或能力的文档说明。

&emsp;&emsp;需求工程包括两个维度：需求开发维度(技术维度)和需求管理维度(管理维度)。

&emsp;&emsp;需求定义的产出是：需求规格说明书SRS。

&emsp;&emsp;需要验证的产出是需求基线，需求管理的对象就是需求基线。

[![p9HF9te.md.png](https://s1.ax1x.com/2023/05/25/p9HF9te.md.png)](https://imgse.com/i/p9HF9te)

>例题
[![p9HFah4.md.png](https://s1.ax1x.com/2023/05/25/p9HFah4.md.png)](https://imgse.com/i/p9HFah4)
{{< expand "学霸肯定对了">}}D{{< /expand >}}

## 4.2 需求获取

从技术维度分：

&emsp;&emsp;需求分为：业务需求(整体全局)、用户需求(用户视角)、系统需求(计算机化)。

&emsp;&emsp;系统需求分为：功能需求、性能需求、设计约束需求(既不是功能需求、又不是性能需求的就属于设计约束需求)。

从管理维度分：

&emsp;&emsp;需求分为：基本需求、期望需求(比较难把握，客户觉得你应该做的)、兴奋需求。

[![p9HFsnx.md.png](https://s1.ax1x.com/2023/05/25/p9HFsnx.md.png)](https://imgse.com/i/p9HFsnx)

## 4.3 需求分析

需求分析包含两个方面：

&emsp;&emsp;1、结构化需求分析SA；

&emsp;&emsp;2、面向对象需求分析OOA。

### 4.3.1 结构化需求分析SA

SA要求完成功能模型(DFD)、行为模型(STD)、数据模型(ER图)，其中数据字典起到解释的作用(学生：学号、名字、年龄)。

[![p9HF6HK.md.png](https://s1.ax1x.com/2023/05/25/p9HF6HK.md.png)](https://imgse.com/i/p9HF6HK)

DFD：Data Flow Diagram，系统跟外界实体之间的交互，数据、加工交换的方式。

[![p9HFf9H.md.png](https://s1.ax1x.com/2023/05/25/p9HFf9H.md.png)](https://imgse.com/i/p9HFf9H)

STD：State Transform Diagram

[![p9HF4gA.md.png](https://s1.ax1x.com/2023/05/25/p9HF4gA.md.png)](https://imgse.com/i/p9HF4gA)

E-R图：实体关系图

[![p9HFout.md.png](https://s1.ax1x.com/2023/05/25/p9HFout.md.png)](https://imgse.com/i/p9HFout)
>例题
[![p9HFXCQ.md.png](https://s1.ax1x.com/2023/05/25/p9HFXCQ.md.png)](https://imgse.com/i/p9HFXCQ)
{{< expand "学霸肯定对了">}}C D{{< /expand >}}

### 4.3.2 面向对象需求分析OOA

&emsp;&emsp;面向对象的相关概念。

[![p9Hk9bV.md.png](https://s1.ax1x.com/2023/05/25/p9Hk9bV.md.png)](https://imgse.com/i/p9Hk9bV)

类的考察方法：

&emsp;&emsp;实体类：永久保存某些数据。

&emsp;&emsp;边界类：人机交互界面、系统交互接口之类的。

&emsp;&emsp;实体类：非实体类和边界类就是实体类。

#### 1）UML

&emsp;&emsp;UML全称Unified Modeling Language，统一建模语言，UML由**构造块**、规则和公共机制；构造块中最重要的是**事物**和**图**；事物中包含结构事物是静态部分、行为事物是动态部分。

[![p9H0rH1.md.png](https://s1.ax1x.com/2023/05/25/p9H0rH1.md.png)](https://imgse.com/i/p9H0rH1)

&emsp;&emsp;UML图同事物一样，也分为静态部分和动态部分，静态图称为结构图，动态图为行为图。得知道每种图大致是什么意思(标红的为重点)。

[![p9H06N6.md.png](https://s1.ax1x.com/2023/05/25/p9H06N6.md.png)](https://imgse.com/i/p9H06N6)

&emsp;&emsp;UML4+1视图，同架构的4+1视图可以一一对应

[![p9H0R3D.md.png](https://s1.ax1x.com/2023/05/25/p9H0R3D.md.png)](https://imgse.com/i/p9H0R3D)

&emsp;&emsp;一般UML分析阶段建模主要是建立**用例模型**(用例图)和**分析模型**(类图)

[![p9H05DA.md.png](https://s1.ax1x.com/2023/05/25/p9H05DA.md.png)](https://imgse.com/i/p9H05DA)

## 4.4 需求定义

[![p9H0H4f.md.png](https://s1.ax1x.com/2023/05/25/p9H0H4f.md.png)](https://imgse.com/i/p9H0H4f)

>例题
[![p9H0L8S.md.png](https://s1.ax1x.com/2023/05/25/p9H0L8S.md.png)](https://imgse.com/i/p9H0L8S)
{{< expand "学霸肯定对了">}}{{< /expand >}}

## 4.5 需求验证

[![p9Hj0HJ.md.png](https://s1.ax1x.com/2023/05/25/p9Hj0HJ.md.png)](https://imgse.com/i/p9Hj0HJ)

