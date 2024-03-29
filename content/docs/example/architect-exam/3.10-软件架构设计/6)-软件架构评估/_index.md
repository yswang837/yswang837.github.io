---
weight: 6
title: "6) 软件架构评估"
---

# 软件架构评估

- 问题：

&emsp;&emsp;1、为什么要进行架构评估？

&emsp;&emsp;答：架构复审的目的是标识潜在的风险，及早发现架构设计中的缺陷和错误。

&emsp;&emsp;2、架构评估到底评什么？

&emsp;&emsp;答：性能是否足够，可修改性是否好，可用性怎么样，安全性是否满足要求，开发成本如何等等问题。

&emsp;&emsp;3、架构评估怎么评？

&emsp;&emsp;答：见架构评估方法

## 1 点位 ✅✅✅

---

- 敏感点：为了实现某种特定的质量属性，是一个或多个构件的特性。

- 权衡点：是影响多个质量属性的特性，是多个质量属性的敏感点。

- 风险点：是指架构设计中潜在的、存在问题的架构决策所带来的隐患。

- 非风险点：是指不会带来隐患，一般以“xxx要求是可以实现 (或接受)的”方式表达。

[![p9vUlvT.png](https://s1.ax1x.com/2023/05/31/p9vUlvT.png)](https://imgse.com/i/p9vUlvT)

## 2 架构评估方法 ✅✅✅

---

&emsp;&emsp;架构评估方法包含3种方式：基于问卷调查(检查表)的方式、基于场景的方式、基于度量的方式。越来越客观准确，但实际实施起来的难度越来越大，所以通常都采用相对较中庸的方法：基于场景的方式。

[![p9vUGb4.md.png](https://s1.ax1x.com/2023/05/31/p9vUGb4.md.png)](https://imgse.com/i/p9vUGb4)

## 3 基于场景的评估方法 ✅✅✅✅

---

- 什么是场景

&emsp;&emsp;场景(scene)：在进行架构评估时，一般首先要精确地得出具体的质量目标(如性能上，在10ms内返回结果等)，并以之作为判定该架构优劣的标准。为得出这些目标而采用的机制叫做场景。场景是从风险承担者的角度对与系统交互的简短描述。在架构评估中，一般采用刺激(stimulus)、环境(environment)和响应(response)三方面来对场景进行描述；刻画质量属性的手段由六部分组成：刺激源、刺激、制品、环境、响应、响应度量。

[![pCwY7Pe.md.png](https://s1.ax1x.com/2023/06/29/pCwY7Pe.md.png)](https://imgse.com/i/pCwY7Pe)

&emsp;&emsp;基于场景的评估方法包含3种：软件架构分析法(SAAM, Software Architecture Analysis Method)、架构权衡分析法(ATAM, Architecture Tradeoff Analysis Method)、成本效益分析法(CBAM)。

### 3.1 SAAM ✅✅✅✅

&emsp;&emsp;SAAM最初用于分析架构可修改性，后扩展到其他质量属性。SAAM的输入是问题描述、需求说明和架构描述；其分析过程包括场景开发(用质量效用树对场景进行分类和确定优先级)、架构描述、单个场景评估、场景交互和总体评估。

[![p9vUta9.md.png](https://s1.ax1x.com/2023/05/31/p9vUta9.md.png)](https://imgse.com/i/p9vUta9)

- 质量效用树

&emsp;&emsp;M：middle

&emsp;&emsp;L：low

&emsp;&emsp;H：high

&emsp;&emsp;在识别出质量属性描述后，通常采用效用树对质量属性的描述进行刻画与排序。从树根到叶子结点分别是：根->质量属性->属性分类(细化)->具体场景。

[![p9vU0xK.md.png](https://s1.ax1x.com/2023/05/31/p9vU0xK.md.png)](https://imgse.com/i/p9vU0xK)

### 3.2 ATAM ✅✅✅✅

&emsp;&emsp;在SAAM的基础上发展起来的，主要针对性能、可用性、安全性和可修改性(用质量效用树对场景进行分类和确定优先级)，在系统开发之前，对这些质量属性进行评价和折中。整个评估过程强调以属性为核心。第二、三阶段容易记错。

[![p9vUN5R.md.png](https://s1.ax1x.com/2023/05/31/p9vUN5R.md.png)](https://imgse.com/i/p9vUN5R)

>例题
[![p9vUaP1.md.png](https://s1.ax1x.com/2023/05/31/p9vUaP1.md.png)](https://imgse.com/i/p9vUaP1)
{{< expand "学霸肯定对了">}}D B

提到影响两个及以上属性时，基本上都是权衡点。{{< /expand >}}
[![p9vUd8x.md.png](https://s1.ax1x.com/2023/05/31/p9vUd8x.md.png)](https://imgse.com/i/p9vUd8x)
{{< expand "学霸肯定对了">}}D

基于度量的架构评估方法才是最精确的，它是一种代码评估方法，需要对软件系统进行测试，ATAM不是一种精确的评估工具，ATAM本身不是精确评估，所以不太需要单独评估需求是否准确，需求是否准确是需求工程要干的活儿{{< /expand >}}
[![p9vUw26.md.png](https://s1.ax1x.com/2023/05/31/p9vUw26.md.png)](https://imgse.com/i/p9vUw26)
{{< expand "学霸肯定对了">}}C C{{< /expand >}}
>案例分析例题
[![pCgWYHH.md.png](https://s1.ax1x.com/2023/07/09/pCgWYHH.md.png)](https://imgse.com/i/pCgWYHH)
[![pCgWGuD.md.png](https://s1.ax1x.com/2023/07/09/pCgWGuD.md.png)](https://imgse.com/i/pCgWGuD)
{{< expand "学霸肯定对了">}}
[![pCgWyDg.md.png](https://s1.ax1x.com/2023/07/09/pCgWyDg.md.png)](https://imgse.com/i/pCgWyDg)
[![pCgWsKS.md.png](https://s1.ax1x.com/2023/07/09/pCgWsKS.md.png)](https://imgse.com/i/pCgWsKS)
{{< /expand >}}
