## 课程内容提要

- 1.软件架构的概述&emsp;&emsp;&emsp;✅✅✅
- 2.软件架构风格&emsp;&emsp;&emsp;&emsp;✅✅✅✅✅
- 3.架构描述语言&emsp;&emsp;&emsp;&emsp;✅✅✅
- 4.特定领域软件架构&emsp;&emsp;✅✅✅
- 5.基于架构的软件开发&emsp;✅✅✅✅
- 6.软件质量属性&emsp;&emsp;&emsp;&emsp;✅✅✅✅✅
- 7.软件架构评估&emsp;&emsp;&emsp;&emsp;✅✅✅✅✅
- 8.软件产品线&emsp;&emsp;&emsp;&emsp;&emsp;✅✅✅
- 9.构建与中间件技术&emsp;&emsp;✅✅✅✅
- 10.web架构设计 &emsp;&emsp;&emsp; ✅✅✅✅✅

### 1.软件架构的概述
#### 1.1 软件架构的概念
&emsp;&emsp;**软件架构**即**软件体系结构**，软件架构设计就是需求的再分配，即**将满足需求的职责分配到组件上**。它搭建起了需求分析与软件设计之间的鸿沟。如下图：
[![p9rdvi4.png](https://s1.ax1x.com/2023/05/11/p9rdvi4.png)](https://imgse.com/i/p9rdvi4)
- 架构的本质\
&emsp;&emsp;1. 软件架构为软件系统提供了一个**结构**、**行为**和**属性**的高级抽象。\
&emsp;&emsp;2. 软件架构风格是特定应用领域的**管用模式**，架构定义了一个**词汇表**和一组**约束**。\
- 架构的作用\
&emsp;&emsp;1. 软件架构是**项目干系人进行交流的手段**。\
&emsp;&emsp;2. 软件架构是**可传递和可复用的模型**。\
&emsp;&emsp;3. 软件架构使推理和控制的更改更加简单，有助于**循序渐进的原型设计**。
>例题
[![p9rwVFe.md.png](https://s1.ax1x.com/2023/05/11/p9rwVFe.md.png)](https://imgse.com/i/p9rwVFe)\
答案：D
#### 1.2 软件架构的发展
&emsp;&emsp;软件架构的发展经历了无架构模式(汇编语言)、萌芽阶段(程序结构设计)、初级阶段(统一建模语言UML)、高级阶段(4+1视图)。\
&emsp;&emsp;**4+1视图**如下：
[![p9rwWOx.md.png](https://s1.ax1x.com/2023/05/11/p9rwWOx.md.png)](https://imgse.com/i/p9rwWOx)。
>例题
[![p9rwokD.md.png](https://s1.ax1x.com/2023/05/11/p9rwokD.md.png)](https://imgse.com/i/p9rwokD)\
答案：A D C
### 2.软件架构风格
&emsp;&emsp;架构风格反映了领域中众多系统所共有的**结构**和**语义**特性，并指导如何将各个**构件**有效地组织成一个完整的系统。架构风格定义了用于描述系统的术语表和一组指导构建系统的规则。下图是架构师考试中常见的架构风格及其子风格，接下来会详细介绍每一种风格。
[![p9rTTqf.md.png](https://s1.ax1x.com/2023/05/11/p9rTTqf.md.png)](https://imgse.com/i/p9rTTqf)
#### 2.1 架构风格 - 数据流风格
&emsp;&emsp;数据流风格以数据驱动的方式推进项目，其的典型应用有**传统编译器**、**网络报文处理**，它包含2个子风格：\
1、批处理。做题要点：**大量整体数据**、**无需用户交互**\
2、管道过滤器。做题要点：**流式数据**、**弱用户交互**\
具体如下图：
[![p9rIyS1.md.png](https://s1.ax1x.com/2023/05/11/p9rIyS1.md.png)](https://imgse.com/i/p9rIyS1)
[![p9rI6Qx.md.png](https://s1.ax1x.com/2023/05/11/p9rI6Qx.md.png)](https://imgse.com/i/p9rI6Qx)
#### 2.2 架构风格 - 调用/返回风格
&emsp;&emsp;调用/返回风格包含3个子风格：\
1、主程序/子程序\
2、面向对象\
3、分层方法，改点后面会单独讲\
[![p9rIfTe.md.png](https://s1.ax1x.com/2023/05/11/p9rIfTe.md.png)](https://imgse.com/i/p9rIfTe)
[![p9rI5Yd.md.png](https://s1.ax1x.com/2023/05/11/p9rI5Yd.md.png)](https://imgse.com/i/p9rI5Yd)
#### 2.3 架构风格 - 独立构建风格
&emsp;&emsp;独立构建区别于返回/调用风格的点在于，相对松耦合，且放弃了对子程序的控制，它包含2个子风格：\
1、进程通信\
2、事件驱动系统（隐式调用）\
[![p9rIIfA.md.png](https://s1.ax1x.com/2023/05/11/p9rIIfA.md.png)](https://imgse.com/i/p9rIIfA)
[![p9rIH6P.md.png](https://s1.ax1x.com/2023/05/11/p9rIH6P.md.png)](https://imgse.com/i/p9rIH6P)
#### 2.4 架构风格 - 虚拟机风格
&emsp;&emsp;虚拟机风格包含2个子风格：\
1、解释器风格，做题关键字：需要自定义规则的场景\
2、规则系统，做题关键字：在解释器的基础上增加经验规则

[![p9rILm8.md.png](https://s1.ax1x.com/2023/05/11/p9rILm8.md.png)](https://imgse.com/i/p9rILm8)
[![p9rIO0S.md.png](https://s1.ax1x.com/2023/05/11/p9rIO0S.md.png)](https://imgse.com/i/p9rIO0S)

#### 2.5 架构风格 - 仓库风格
&emsp;&emsp;仓库风格包含2个子风格：\
1、数据库系统\
2、黑板系统
[![p9r7PdU.md.png](https://s1.ax1x.com/2023/05/11/p9r7PdU.md.png)](https://imgse.com/i/p9r7PdU)
[![p9rIzfs.md.png](https://s1.ax1x.com/2023/05/11/p9rIzfs.md.png)](https://imgse.com/i/p9rIzfs)
[![p9roppn.md.png](https://s1.ax1x.com/2023/05/11/p9roppn.md.png)](https://imgse.com/i/p9roppn)
#### 2.6 架构风格 - 闭环控制风格(过程风格)
[![p9ro9lq.md.png](https://s1.ax1x.com/2023/05/11/p9ro9lq.md.png)](https://imgse.com/i/p9ro9lq)
#### 2.7 架构风格 - C2架构风格
[![p9roC60.md.png](https://s1.ax1x.com/2023/05/11/p9roC60.md.png)](https://imgse.com/i/p9roC60)\
>例题
[![p9r7KeK.md.png](https://s1.ax1x.com/2023/05/11/p9r7KeK.md.png)](https://imgse.com/i/p9r7KeK)\
答案：
[![p9rq1FU.md.png](https://s1.ax1x.com/2023/05/11/p9rq1FU.md.png)](https://imgse.com/i/p9rq1FU)\
答案：
[![p9rOyqI.md.png](https://s1.ax1x.com/2023/05/11/p9rOyqI.md.png)](https://imgse.com/i/p9rOyqI)\
答案：















### 3.架构描述语言

### 4.特定领域软件架构

### 5.基于架构的软件开发

### 6.软件质量属性

### 7.软件架构评估

### 8.软件产品线

### 9.构建与中间件技术

### 10.web架构设计


