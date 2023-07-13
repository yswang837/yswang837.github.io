# 需求工程 ✌

## 1 概述

---

&emsp;&emsp;软件需求是指用户对系统在行为、功能、性能、设计约束等方面的期望。

&emsp;&emsp;需求工程包括两个维度：需求开发维度(技术维度)和需求管理维度(管理维度)。

&emsp;&emsp;需求定义的产出是：需求规格说明书SRS。

&emsp;&emsp;对需求规格说明书SRS进行需要验证得到需求基线，需求管理的对象就是需求基线。

[![p9HF9te.md.png](https://s1.ax1x.com/2023/05/25/p9HF9te.md.png)](https://imgse.com/i/p9HF9te)

>例题
[![p9HFah4.md.png](https://s1.ax1x.com/2023/05/25/p9HFah4.md.png)](https://imgse.com/i/p9HFah4)
{{< expand "学霸肯定对了">}}D{{< /expand >}}

## 2 需求获取

---

从技术维度分：

&emsp;&emsp;需求分为：业务需求(整体全局)、用户需求(用户视角)、系统需求(计算机化)。

&emsp;&emsp;系统需求分为：功能需求、性能需求、设计约束需求(既不是功能需求、又不是性能需求的就属于设计约束需求)。

从管理维度分：

&emsp;&emsp;需求分为：基本需求、期望需求(比较难把握，客户觉得你应该做的)、兴奋需求。

[![p9HFsnx.md.png](https://s1.ax1x.com/2023/05/25/p9HFsnx.md.png)](https://imgse.com/i/p9HFsnx)

## 3 需求分析

---

需求分析包含两个方面：

&emsp;&emsp;1、结构化需求分析SA；

&emsp;&emsp;2、面向对象需求分析OOA。

### 4.3.1 结构化需求分析SA

&emsp;&emsp;SA要求完成功能模型(数据流图DFD，也叫分层数据流图)、行为模型(状态转换图STD)、数据模型(ER图)，其中数据字典起到解释的作用(学生：学号、名字、年龄)，比如学生关系包含学号、名字、年龄等。

[![p9HF6HK.md.png](https://s1.ax1x.com/2023/05/25/p9HF6HK.md.png)](https://imgse.com/i/p9HF6HK)

- DFD：Data Flow Diagram，（功能建模）系统跟外界实体之间的交互，数据、加工交换的方式。

[![pCyFSJ0.md.png](https://s1.ax1x.com/2023/07/05/pCyFSJ0.md.png)](https://imgse.com/i/pCyFSJ0)
[![pCyFEw9.md.png](https://s1.ax1x.com/2023/07/05/pCyFEw9.md.png)](https://imgse.com/i/pCyFEw9)
[![p9HFf9H.md.png](https://s1.ax1x.com/2023/05/25/p9HFf9H.md.png)](https://imgse.com/i/p9HFf9H)

- DFD的平衡原则：用于DFD里面填空(类似于完形填空)，如上图的“注册请求”、“课程安排”等在父图和子图中应该是一致的。

[![pCyF6kn.md.png](https://s1.ax1x.com/2023/07/05/pCyF6kn.md.png)](https://imgse.com/i/pCyF6kn)

- DFD答题技巧

[![pCyFI0J.md.png](https://s1.ax1x.com/2023/07/05/pCyFI0J.md.png)](https://imgse.com/i/pCyFI0J)
[![pCyFHt1.md.png](https://s1.ax1x.com/2023/07/05/pCyFHt1.md.png)](https://imgse.com/i/pCyFHt1)
[![pCyFX6O.md.png](https://s1.ax1x.com/2023/07/05/pCyFX6O.md.png)](https://imgse.com/i/pCyFX6O)


STD：State Transform Diagram，（状态建模）

[![p9HF4gA.md.png](https://s1.ax1x.com/2023/05/25/p9HF4gA.md.png)](https://imgse.com/i/p9HF4gA)

E-R图：实体关系图，（数据建模）

[![p9HFout.md.png](https://s1.ax1x.com/2023/05/25/p9HFout.md.png)](https://imgse.com/i/p9HFout)
>例题
[![p9HFXCQ.md.png](https://s1.ax1x.com/2023/05/25/p9HFXCQ.md.png)](https://imgse.com/i/p9HFXCQ)
{{< expand "学霸肯定对了">}}C D

用例图、对象图、通信图、顺序图和活动图都是面向对象的图，都是UML里面的图{{< /expand >}}

### 4.3.2 面向对象需求分析OOA

&emsp;&emsp;面向对象的相关概念。

[![p9Hk9bV.md.png](https://s1.ax1x.com/2023/05/25/p9Hk9bV.md.png)](https://imgse.com/i/p9Hk9bV)

类的考察方法：

&emsp;&emsp;实体类：永久保存某些数据。

&emsp;&emsp;边界类：人机交互界面、系统交互接口之类的。

&emsp;&emsp;控制类：非实体类和边界类就是控制类，如业务逻辑(订单结算等)。

>案例分析例题
[![pC6KH00.md.png](https://s1.ax1x.com/2023/07/06/pC6KH00.md.png)](https://imgse.com/i/pC6KH00)
[![pC6MFAK.md.png](https://s1.ax1x.com/2023/07/06/pC6MFAK.md.png)](https://imgse.com/i/pC6MFAK)
{{< expand "学霸肯定对了">}}
[![pC6MMHP.md.png](https://s1.ax1x.com/2023/07/06/pC6MMHP.md.png)](https://imgse.com/i/pC6MMHP)
{{< /expand >}}

#### 1）UML

&emsp;&emsp;UML全称Unified Modeling Language，统一建模语言，UML由**构造块**、规则和公共机制；构造块中最重要的是**事物**和**图**；事物中包含结构事物是静态部分、行为事物是动态部分。

[![p9H0rH1.md.png](https://s1.ax1x.com/2023/05/25/p9H0rH1.md.png)](https://imgse.com/i/p9H0rH1)

&emsp;&emsp;UML图同事物一样，也分为静态部分和动态部分，静态图称为结构图，动态图为行为图(交互图)。得知道每种图大致是什么意思(标红的为重点，案例分析里面需要掌握的图有：**类图**、**用例图**、顺序图、通信图、**状态图**、**活动图**)。

[![p9H06N6.md.png](https://s1.ax1x.com/2023/05/25/p9H06N6.md.png)](https://imgse.com/i/p9H06N6)

- 用例图

[![pCykUE9.md.png](https://s1.ax1x.com/2023/07/05/pCykUE9.md.png)](https://imgse.com/i/pCykUE9)

&emsp;&emsp;细化用例描述，第一列包含9种用例规约。

[![pC6id7d.md.png](https://s1.ax1x.com/2023/07/06/pC6id7d.md.png)](https://imgse.com/i/pC6id7d)

- 用例的关系

&emsp;&emsp;包含关系如上图的用户登录。如何区分包含关系和扩展关系：前者是必须的，后者非必须。

&emsp;&emsp;扩展关系如上图的查询书籍信息和修改书籍信息，只有查询书籍信息且信息不对时才会修改书籍信息，修改书籍信息是非必须执行的。

&emsp;&emsp;明显的父子的继承关系，注意却别包含关系··。

[![pCykyuD.md.png](https://s1.ax1x.com/2023/07/05/pCykyuD.md.png)](https://imgse.com/i/pCykyuD)
[![pCyA9rF.md.png](https://s1.ax1x.com/2023/07/05/pCyA9rF.md.png)](https://imgse.com/i/pCyA9rF)

>例题
[![pCyAEP1.md.png](https://s1.ax1x.com/2023/07/05/pCyAEP1.md.png)](https://imgse.com/i/pCyAEP1)
{{< expand "学霸肯定对了">}}B C{{< /expand >}}
>案例分析例题
[![pC6itXD.md.png](https://s1.ax1x.com/2023/07/06/pC6itXD.md.png)](https://imgse.com/i/pC6itXD)
{{< expand "学霸肯定对了">}}
问题1：用例模型的参与者有：仓库管理员、仓库经理、系统管理员、时间、温度、温度调节系统。

问题2：用例名称、用例ID、角色、用例说明、前置条件、后置条件、基本事件流、其他事件流、异常事件流。

问题3：用例之间的关系包括：包含关系、扩展关系、泛化关系。“出入库操作”与“登录”属于包含关系；“查询统计报表”与“生成统计报表”属于扩展关系；“用户注册”与“邮件注册”和“电话注册”属于典型的泛化关系。{{< /expand >}}

&emsp;&emsp;UML4+1视图，同架构的4+1视图可以一一对应

[![p9H0R3D.md.png](https://s1.ax1x.com/2023/05/25/p9H0R3D.md.png)](https://imgse.com/i/p9H0R3D)

&emsp;&emsp;一般UML分析阶段建模主要是建立**用例模型**(用例图)和**分析模型**(类图)

[![p9H05DA.md.png](https://s1.ax1x.com/2023/05/25/p9H05DA.md.png)](https://imgse.com/i/p9H05DA)

- 类图

[![pCyA6zV.md.png](https://s1.ax1x.com/2023/07/05/pCyA6zV.md.png)](https://imgse.com/i/pCyA6zV)

- 类图的关系

&emsp;&emsp;依赖关系好辨识：a调用b的函数，称为a依赖b。

&emsp;&emsp;泛化关系：父子关系，父：一般；子：特殊。

&emsp;&emsp;聚合关系：汽车和轮胎，汽车坏了，其零件还能用。

&emsp;&emsp;组合关系：公司和部门，公司没了，部门自然也就没了。

&emsp;&emsp;实现关系：接口和类

[![pC6CUgO.md.png](https://s1.ax1x.com/2023/07/06/pC6CUgO.md.png)](https://imgse.com/i/pC6CUgO)

>例题
[![pC6PpI1.md.png](https://s1.ax1x.com/2023/07/06/pC6PpI1.md.png)](https://imgse.com/i/pC6PpI1)
{{< expand "学霸肯定对了">}}D C{{< /expand >}}

- 顺序图

[![pC6PFxO.md.png](https://s1.ax1x.com/2023/07/06/pC6PFxO.md.png)](https://imgse.com/i/pC6PFxO)

- 通信图(协作图)

[![pC6PVqH.md.png](https://s1.ax1x.com/2023/07/06/pC6PVqH.md.png)](https://imgse.com/i/pC6PVqH)

- 状态图

[![pC6PnII.md.png](https://s1.ax1x.com/2023/07/06/pC6PnII.md.png)](https://imgse.com/i/pC6PnII)

>案例分析例题
[![pC6Plz8.md.png](https://s1.ax1x.com/2023/07/06/pC6Plz8.md.png)](https://imgse.com/i/pC6Plz8)
{{< expand "学霸肯定对了">}}
[![pC6P3QS.md.png](https://s1.ax1x.com/2023/07/06/pC6P3QS.md.png)](https://imgse.com/i/pC6P3QS)
{{< /expand >}}

- 活动图

&emsp;&emsp;活动图和状态图有点像，可以根据节点里面的内容是状态还是活动来进行区分。

&emsp;&emsp;活动图对标的是流程图，流程图是结构化时代的，而活动图是面向对象的图。

&emsp;&emsp;活动图中的两个粗线之间的活动是可以并行执行的。

[![pC6Ptds.md.png](https://s1.ax1x.com/2023/07/06/pC6Ptds.md.png)](https://imgse.com/i/pC6Ptds)

- 泳道活动图

[![pC6PNon.md.png](https://s1.ax1x.com/2023/07/06/pC6PNon.md.png)](https://imgse.com/i/pC6PNon)

- 定时图(计时图)

[![pC6iAf0.md.png](https://s1.ax1x.com/2023/07/06/pC6iAf0.md.png)](https://imgse.com/i/pC6iAf0)

>例题
[![pC6PdJ0.md.png](https://s1.ax1x.com/2023/07/06/pC6PdJ0.md.png)](https://imgse.com/i/pC6PdJ0)
{{< expand "学霸肯定对了">}}B A

&emsp;&emsp;第一空分析：交互过程建模，说明要选择动态图。第二空分析：执行流程，说明要选择动态图。{{< /expand >}}

- 构建图与包图

&emsp;&emsp;构建图是对外提供的一个接口和功能，包图是为了管理方便，将相关的东西放在一个文件夹中。

[![pC6ie6U.md.png](https://s1.ax1x.com/2023/07/06/pC6ie6U.md.png)](https://imgse.com/i/pC6ie6U)

- 部署图

&emsp;&emsp;描述的是硬件节点和软件构建之间的关系。

[![pC6ium4.md.png](https://s1.ax1x.com/2023/07/06/pC6ium4.md.png)](https://imgse.com/i/pC6ium4)

## 4 需求定义

---

&emsp;&emsp;把需求分析的成果落地成文档的过程就是需求定义的过程。需求定义包含2大类：严格定义法、原型法。

&emsp;&emsp;需求定义的产物的是：需求规格说明书SRS。

[![p9H0H4f.md.png](https://s1.ax1x.com/2023/05/25/p9H0H4f.md.png)](https://imgse.com/i/p9H0H4f)

>例题
[![p9H0L8S.md.png](https://s1.ax1x.com/2023/05/25/p9H0L8S.md.png)](https://imgse.com/i/p9H0L8S)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 5 需求验证

---

&emsp;&emsp;对需求规格说明书SRS进行验证，需求甲方参与确认。最为最终的需求基线。

[![p9Hj0HJ.md.png](https://s1.ax1x.com/2023/05/25/p9Hj0HJ.md.png)](https://imgse.com/i/p9Hj0HJ)

## 6 需求变更控制

---

&emsp;&emsp;需求变更是每个项目中客观存在的。无法杜绝的。我们要做的是管理和控制好需求的变更。

[![pCUFZ11.md.png](https://s1.ax1x.com/2023/06/26/pCUFZ11.md.png)](https://imgse.com/i/pCUFZ11)

>例题
[![pCUFmX6.md.png](https://s1.ax1x.com/2023/06/26/pCUFmX6.md.png)](https://imgse.com/i/pCUFmX6)
{{< expand "学霸肯定对了">}}D B{{< /expand >}}

## 7 需求版本控制

[![pCsarUs.md.png](https://s1.ax1x.com/2023/07/04/pCsarUs.md.png)](https://imgse.com/i/pCsarUs)

## 8 需求跟踪

---

&emsp;&emsp;需求工程的目标是获取用户最真实的需求，可往往在开发测试过程中会出现遗漏，这时候需要及时跟踪需求，以发现纰漏。

&emsp;&emsp;用户的需求称为原始需求，软件需求可以认为是用例(功能)，UC-n没有打钩，表示这个功能多余了，用户其实不需要这个功能；FR-m没有打钩，表示这个功能漏做了。

[![pCUiz60.md.png](https://s1.ax1x.com/2023/06/26/pCUiz60.md.png)](https://imgse.com/i/pCUiz60)

## 9 需求状态管理

---

&emsp;&emsp;又称为需求管理，一个需求确认以后，往往会有多个状态的变迁。

[![pCUi4SI.md.png](https://s1.ax1x.com/2023/06/26/pCUi4SI.md.png)](https://imgse.com/i/pCUi4SI)
