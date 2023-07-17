# 软件开发模型 ✌

&emsp;&emsp;一个开发方法（方法论）下面可以有多个开发模型。各种开发模型之间是存在重合和交叠的，而不是完全隔离的。

## 1 瀑布模型

---

&emsp;&emsp;严格先后完成每个阶段，上一阶段的输出时下一个阶段的输入，是结构化开发方法的典型模型，适合于**需求明确**的项目，对大型项目来说风险较大。

[![p9TxwTA.md.png](https://s1.ax1x.com/2023/05/24/p9TxwTA.md.png)](https://imgse.com/i/p9TxwTA)

## 2 迭代/演化模型

---

&emsp;&emsp;先快速开发出一个能用的丐版模型，之后再进行完善和优化，每一轮迭代均发布一个可用的产品。

[![p97uiGT.md.png](https://s1.ax1x.com/2023/05/24/p97uiGT.md.png)](https://imgse.com/i/p97uiGT)

## 3 增量模型

---

&emsp;&emsp;先开发出最核心的组件，之后在再核心组件上开发出别的组件，每一次增量均发布一个可用的产品。

[![p97u9I0.png](https://s1.ax1x.com/2023/05/24/p97u9I0.png)](https://imgse.com/i/p97u9I0)

## 4 螺旋模型

---

&emsp;&emsp;螺旋模型 = 原型 + 瀑布模型，首次引入**风险分析**，适合大型项目，螺旋模型是在快速模型的基础上扩展而成的。

&emsp;&emsp;螺旋模型将整个软件开发过程分为多个阶段，每个阶段都由目标设定、风险分析、开发和有效性验证以及评审4个部分组成。

[![p97urQg.md.png](https://s1.ax1x.com/2023/05/24/p97urQg.md.png)](https://imgse.com/i/p97urQg)

>例题
[![pCNJCLD.md.png](https://s1.ax1x.com/2023/06/25/pCNJCLD.md.png)](https://imgse.com/i/pCNJCLD)
{{< expand "学霸肯定对了">}}B{{< /expand >}}

## 5 原型模型

---

&emsp;&emsp;适合需求不明确的系统。若题目中指明“需求不明确”，选原型而不选螺旋模型。

## 6 喷泉模型

---

&emsp;&emsp;早期著名的面向对象模型。它的特点是各个阶段之间没有明显的界限（区别于瀑布模型），各个阶段可以并发；但它非常不利于项目管理。

[![p97u2oq.png](https://s1.ax1x.com/2023/05/24/p97u2oq.png)](https://imgse.com/i/p97u2oq)

## 7 V模型

---

&emsp;&emsp;测试提前做，测试贯穿于始终。

[![p97uces.md.png](https://s1.ax1x.com/2023/05/24/p97uces.md.png)](https://imgse.com/i/p97uces)

## 8 构建组装模型

---

&emsp;&emsp;优点：快，成本低、可靠高。

&emsp;&emsp;缺点：构建库的建立需要慢慢积累。放到个人来说就是，代码库的建立需要慢慢积累。

&emsp;&emsp;软件系统通过构件组装分为三个不同的层次:定制(customization)、集成(integration)和扩展 (extension)。

[![p97u5SU.md.png](https://s1.ax1x.com/2023/05/24/p97u5SU.md.png)](https://imgse.com/i/p97u5SU)

## 9 快速应用开发模型RAD

---

&emsp;&emsp;快速应用开发=瀑布模型(SDLC) + 构建组装模型(CBSD)，可认为它综合了二者的优点；当系统模块化程度较高时可采用该开发模型。

[![p97KtcF.md.png](https://s1.ax1x.com/2023/05/24/p97KtcF.md.png)](https://imgse.com/i/p97KtcF)

## 10 统一过程模型UP/RUP

---

&emsp;&emsp;三大特点：用例驱动、以架构为中心、迭代和增量。

- 四个阶段：
  - 初始：确定项目范围和边界
  - 细化：设计并确定架构体系、指定工作计划及资源要求。
  - 构建：开发剩余的构建、构建组装与测试
  - 交付：制作发布版本
  
[![p97uTOJ.md.png](https://s1.ax1x.com/2023/05/24/p97uTOJ.md.png)](https://imgse.com/i/p97uTOJ)

>例题
[![pCNJkod.md.png](https://s1.ax1x.com/2023/06/25/pCNJkod.md.png)](https://imgse.com/i/pCNJkod)
{{< expand "学霸肯定对了">}}B A{{< /expand >}}

## 11 敏捷开发模型

---

&emsp;&emsp;小步快跑的模式，适合小型项目。

&emsp;&emsp;敏捷方法是以人为本的适应性方法，它介于无软件开发和传统软件开发方法(注重流程文档)之间；将更重要的注意力集中于可运行的代码本身，而不太重视各类文档、流程之类的。

[![p97MU8f.md.png](https://s1.ax1x.com/2023/05/24/p97MU8f.md.png)](https://imgse.com/i/p97MU8f)

- 价值观与最佳实践

[![p97M5qJ.png](https://s1.ax1x.com/2023/05/24/p97M5qJ.png)](https://imgse.com/i/p97M5qJ)

- 敏捷开发下的模型

[![p97QdF1.md.png](https://s1.ax1x.com/2023/05/24/p97QdF1.md.png)](https://imgse.com/i/p97QdF1)

>例题
[![p97QyOe.md.png](https://s1.ax1x.com/2023/05/24/p97QyOe.md.png)](https://imgse.com/i/p97QyOe)
{{< expand "学霸肯定对了">}}C{{< /expand >}}
[![p97QWFI.md.png](https://s1.ax1x.com/2023/05/24/p97QWFI.md.png)](https://imgse.com/i/p97QWFI)
{{< expand "学霸肯定对了">}}B A{{< /expand >}}
[![p97Q5Sf.md.png](https://s1.ax1x.com/2023/05/24/p97Q5Sf.md.png)](https://imgse.com/i/p97Q5Sf)
{{< expand "学霸肯定对了">}}B{{< /expand >}}
[![p97Qo6S.md.png](https://s1.ax1x.com/2023/05/24/p97Qo6S.md.png)](https://imgse.com/i/p97Qo6S)
{{< expand "学霸肯定对了">}}B D{{< /expand >}}
