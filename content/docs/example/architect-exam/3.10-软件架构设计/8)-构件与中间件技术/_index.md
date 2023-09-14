---
weight: 8
title: "8) 构建与中间件技术"
---

# 构件与中间件技术

## 1 构件的定义 ✅✅✅✅

---

&emsp;&emsp;软件构件是一种组装单元，它具有规范的接口规约和显式的语境依赖。软件构件可以被独立地部署并由第三方任意地组装。

&emsp;&emsp;构件是某系统中有价值的、几乎独立的并可替换的一个部分，它在良好定义的架构语境内满足某清晰的功能。

&emsp;&emsp;构件是一个独立发布的功能部分，可以通过其接口访问它的服务。我的理解是：构件>模块>对象

[![p9vU7ZQ.md.png](https://s1.ax1x.com/2023/05/31/p9vU7ZQ.md.png)](https://imgse.com/i/p9vU7ZQ)

&emsp;&emsp;构件的系统架构由一组平台决策、一组构件框架和构件框架之间的互操作设计组成。

&emsp;&emsp;构件框架是一种专用的架构(通常围绕一些关键的机制)，同时，也是一组固定地作用于构件层次机制的策略。

&emsp;&emsp;概念框架的互操作设计包括系统体系结构连接的所有框架间的互操作的规则。

&emsp;&emsp;构件是一组通常需要同时部署的原子构件。构件和原子构件之间的区别在于，大多数原子构件永远都不会被单独部署，尽管它们可以被单独部署。

&emsp;&emsp;一个原子构件是一个模块和一组资源。

&emsp;&emsp;模块是一组类和可能的非面向对象的结构体，比如过程或者函数。

&emsp;&emsp;资源是一个类型化的项的固定集合。

&emsp;&emsp;资源这个概念可以包含代码资源，进而包含模块。问题在除了编译器编译一个模块或包生成的资源外，还可能存在其他的资源。在“纯对象”的方法中，资源是外部化的不可改变的对象一一不可改变是因为构件没有持久化的标志，而目复制不能被区分。

&emsp;&emsp;构件的接口是一种服务提供者对消费者的承诺，即契约(contract)，用契约确保一组构件之间的行为组合。

## 2 中间件 ✅✅✅

---

&emsp;&emsp;中间件是构件的一种、中间件是一类系统软件。如ESB

[![p9vUbIs.md.png](https://s1.ax1x.com/2023/05/31/p9vUbIs.md.png)](https://imgse.com/i/p9vUbIs)

&emsp;&emsp;中间件技术的优点：

&emsp;&emsp;中间件通过标准接口实现与应用程序的关联，提供特定功能的服务；使用中间件可以提高应用软件可移植性；使用中间件有助于提高开发效率。

&emsp;&emsp;中间件是独立的系统级软件，连接操作系统层和应用程序层，将不同操作系统提供应用的接口标准化，协议统一化，屏蔽具体操作的细节，中间件一般提供如下功能：

&emsp;&emsp;1、通信支持。中间件为其所支持的应用软件提供平台化的运行环境，该环境屏蔽底层通信之间的接口差异，实现互操作，所以通信支持是中间件一个最基本的功能。

&emsp;&emsp;2、应用支持。中间件的目的就是服务上层应用，提供应用层不同服务之间的互操作机制。

&emsp;&emsp;3、公共服务。公共服务是对应用软件中共性功能或约束的提取。将这些共性的功能或者约束分类实现，并支持复用，作为公共服务，提供给应用程序使用。

&emsp;&emsp;中间件提供平台和应用之间的通用服务，这些服务具有标准的程序接口和协议。中间件的基本功能包括：为客户端和服务器之间提供连接和通信；提供交易管理机制保证交易的一致性；提供应用的负载均衡和高可用性等。

[![p9vUOGq.md.png](https://s1.ax1x.com/2023/05/31/p9vUOGq.md.png)](https://imgse.com/i/p9vUOGq)

### 2.1 消息中间件 ✅✅✅

&emsp;&emsp;1、消息中间件是消息传输过程中保存消息的一种容器；

&emsp;&emsp;2、消息中间件具有两个基本特点：采用异步处理模式应用程序和应用程序调用关系为松耦合关系；

&emsp;&emsp;3、消息中间件使得不同系统、不同进程之间能够通信，注意不是对象。

&emsp;&emsp;4、消息中间件的消息传递服务模型有点对点模型和发布-订阅模型之分。

## 3 构件的复用 ✅✅✅

---

- 复用的发展史
[![p9vg0zQ.md.png](https://s1.ax1x.com/2023/05/31/p9vg0zQ.md.png)](https://imgse.com/i/p9vg0zQ)

- 构建的复用流程
[![p9vgsLn.md.png](https://s1.ax1x.com/2023/05/31/p9vgsLn.md.png)](https://imgse.com/i/p9vgsLn)
[![p9vgcd0.md.png](https://s1.ax1x.com/2023/05/31/p9vgcd0.md.png)](https://imgse.com/i/p9vgcd0)
[![p9vggoV.md.png](https://s1.ax1x.com/2023/05/31/p9vggoV.md.png)](https://imgse.com/i/p9vggoV)
[![p9vgWJU.md.png](https://s1.ax1x.com/2023/05/31/p9vgWJU.md.png)](https://imgse.com/i/p9vgWJU)

>例题
[![p9vOP78.md.png](https://s1.ax1x.com/2023/05/31/p9vOP78.md.png)](https://imgse.com/i/p9vOP78)
{{< expand "学霸肯定对了">}}B

水平：通用，普遍

垂直：专用，特定用途{{< /expand >}}
[![p9vOVpj.md.png](https://s1.ax1x.com/2023/05/31/p9vOVpj.md.png)](https://imgse.com/i/p9vOVpj)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 3.1 软件的复用 ✅✅

&emsp;&emsp;软件复用过程包含：创建、复用、支持、管理4个过程。整体说来就是：构造/获取可复用的软件资产、管理可复用资产和使用可复用资产。

&emsp;&emsp;1、创建过程：界定和提供可复用资产，以满足复用者的需要；

&emsp;&emsp;2、复用过程：利用可复用资产来生产应用软件产品；

&emsp;&emsp;3、支持过程：全面支持可复用资产的获取、管理和维护工作；

&emsp;&emsp;4、管理过程：执行计划、启动、资源、跟踪并协调其他各个过程；

&emsp;&emsp;在软件架构复用中，计划复用是指在开发之前，就要进行规划，以决定哪些需要复用。资产复用(是指将已有的软件资产(如框架、组件、类库等)运用到新的软件系统中以提高软件开发效率和质量)是指开发过程中，只要发现有可复用的资产，就对其进行复用；系统复用是指将已有的个或多个系统的某一部分或全部内容，用于构建新的系统。

## 4 构件标准 ✅✅

---

[![pCwRUBT.md.png](https://s1.ax1x.com/2023/06/29/pCwRUBT.md.png)](https://imgse.com/i/pCwRUBT)

### 4.1 COBRA ✅✅

[![pCwRgu6.md.png](https://s1.ax1x.com/2023/06/29/pCwRgu6.md.png)](https://imgse.com/i/pCwRgu6)
[![pCwR7vt.md.png](https://s1.ax1x.com/2023/06/29/pCwR7vt.md.png)](https://imgse.com/i/pCwR7vt)
[![pCwRbKP.md.png](https://s1.ax1x.com/2023/06/29/pCwRbKP.md.png)](https://imgse.com/i/pCwRbKP)
[![pCwRv5Q.md.png](https://s1.ax1x.com/2023/06/29/pCwRv5Q.md.png)](https://imgse.com/i/pCwRv5Q)

>例题
[![pCwRzCj.md.png](https://s1.ax1x.com/2023/06/29/pCwRzCj.md.png)](https://imgse.com/i/pCwRzCj)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
