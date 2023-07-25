---
weight: 2
title: "2) 软件架构风格"
---

# 2.软件架构风格

&emsp;&emsp;架构风格反映了领域中众多系统所共有的**结构**和**语义**特性，并指导如何将各个**构件**有效地组织成一个完整的系统。架构风格定义了用于描述系统的术语表和一组指导构建系统的规则，强调对架构设计的重用。以下是常见风格的特点或应用：

&emsp;&emsp;批处理--->传统编译器。

&emsp;&emsp;管道过滤器--->支持分阶段数据处理。

&emsp;&emsp;层次架构--->采用层次化架构风格的系统，划分的层次越多，系统性能越差。

&emsp;&emsp;过程控制--->控制系统，其特点是不断采集系统当前状态，与系统中的设定状态进行对比，并通过将当前状态与设定状态进行对比从而进行控制。

&emsp;&emsp;隐式调用--->回调机制，采用隐式调用架构风格的系统，可以通过处理函数的并发调用提高系统处理性能。

&emsp;&emsp;事件驱动系统--->注册事件处理的是回调函数，当某个界面事件发生时（例如键盘敲击、鼠标移动等)，系统会查找并选择合适的回调函数处理该事件。

&emsp;&emsp;解析器--->运行时的系统行为定义与改变的能力，采用解释器架构风格的系统，可以通过部分解释代码预先编译的方式提高系统性能。

&emsp;&emsp;黑板风格--->信号处理领域，语音识别系统是一个十分典型的专家系统，其特点是求解的正确结果不止一个，求解过程比较复杂，需要通过专家知识和反馈逐步得到正确结果。

&emsp;&emsp;虚拟机风格--->通过虚拟机架构屏蔽不同的硬件环境。

&emsp;&emsp;C2体系结构风格--->通过连接件绑定在一起的按照一组规则运作的并行构件网络。

&emsp;&emsp;数据仓库--->现代集成开发环境（现代编译器）。

下图是架构师考试中常见的架构风格及其子风格，接下来会详细介绍每一种风格。
[![p9rTTqf.md.png](https://s1.ax1x.com/2023/05/11/p9rTTqf.md.png)](https://imgse.com/i/p9rTTqf)

## 2.1 数据流风格

---

&emsp;&emsp;数据流风格以数据驱动的方式推进项目，其的典型应用有**传统编译器**、**网络报文处理**，它包含2个子风格：

&emsp;&emsp;1、批处理。做题要点：**大量整体数据**、**无需用户交互**

&emsp;&emsp;2、管道过滤器。做题要点：**流式数据**、**弱用户交互**

具体如下图：

[![p9rIyS1.md.png](https://s1.ax1x.com/2023/05/11/p9rIyS1.md.png)](https://imgse.com/i/p9rIyS1)
[![p9rI6Qx.md.png](https://s1.ax1x.com/2023/05/11/p9rI6Qx.md.png)](https://imgse.com/i/p9rI6Qx)

## 2.2 调用/返回风格

---

&emsp;&emsp;调用/返回风格包含3个子风格：

&emsp;&emsp;1、主程序/子程序风格

&emsp;&emsp;2、面向对象风格

&emsp;&emsp;3、分层风格，将在“2.8 架构风格具体实例”中详细说明

[![p9rIfTe.md.png](https://s1.ax1x.com/2023/05/11/p9rIfTe.md.png)](https://imgse.com/i/p9rIfTe)
[![p9rI5Yd.md.png](https://s1.ax1x.com/2023/05/11/p9rI5Yd.md.png)](https://imgse.com/i/p9rI5Yd)

## 2.3 独立构建风格

---

&emsp;&emsp;独立构建区别于返回/调用风格的点在于，相对松耦合，且放弃了对子程序的控制，它包含2个子风格：

&emsp;&emsp;1、进程通信

&emsp;&emsp;2、事件驱动系统（隐式调用）

[![p9rIIfA.md.png](https://s1.ax1x.com/2023/05/11/p9rIIfA.md.png)](https://imgse.com/i/p9rIIfA)
[![p9rIH6P.md.png](https://s1.ax1x.com/2023/05/11/p9rIH6P.md.png)](https://imgse.com/i/p9rIH6P)

## 2.4 虚拟机风格

---

&emsp;&emsp;虚拟机风格包含2个子风格：

&emsp;&emsp;1、解释器风格，做题关键字：需要自定义规则的场景

&emsp;&emsp;2、规则系统，做题关键字：在解释器的基础上增加经验规则；基于规则的系统包括规则集、规则解释器、规则/数据选择器及工作内存；它的特点是将业务逻辑中频繁变化的部分定义为规则。

[![p9rILm8.md.png](https://s1.ax1x.com/2023/05/11/p9rILm8.md.png)](https://imgse.com/i/p9rILm8)
[![p9rIO0S.md.png](https://s1.ax1x.com/2023/05/11/p9rIO0S.md.png)](https://imgse.com/i/p9rIO0S)

## 2.5 仓库风格

---

&emsp;&emsp;仓库风格包含2个子风格：

&emsp;&emsp;1、数据库系统

&emsp;&emsp;2、黑板系统

[![p9r7PdU.md.png](https://s1.ax1x.com/2023/05/11/p9r7PdU.md.png)](https://imgse.com/i/p9r7PdU)
[![p9rIzfs.md.png](https://s1.ax1x.com/2023/05/11/p9rIzfs.md.png)](https://imgse.com/i/p9rIzfs)
[![p9roppn.md.png](https://s1.ax1x.com/2023/05/11/p9roppn.md.png)](https://imgse.com/i/p9roppn)

## 2.6 闭环控制风格(过程风格)

---

&emsp;&emsp;不适合于特别复杂的系统。

[![p9ro9lq.md.png](https://s1.ax1x.com/2023/05/11/p9ro9lq.md.png)](https://imgse.com/i/p9ro9lq)

## 2.7 C2架构风格

---

&emsp;&emsp;C2属于层次架构风格。

[![p9roC60.md.png](https://s1.ax1x.com/2023/05/11/p9roC60.md.png)](https://imgse.com/i/p9roC60)

>例题
[![p9r7KeK.md.png](https://s1.ax1x.com/2023/05/11/p9r7KeK.md.png)](https://imgse.com/i/p9r7KeK)
{{< expand "学霸肯定对了">}}1.虚拟机&emsp;&emsp;2.数据流&emsp;&emsp;3.隐式调用&emsp;&emsp;4.解释器&emsp;&emsp;5.过程控制{{< /expand >}}
[![p9rq1FU.md.png](https://s1.ax1x.com/2023/05/11/p9rq1FU.md.png)](https://imgse.com/i/p9rq1FU)
{{< expand "学霸肯定对了">}}1.黑板&emsp;&emsp;2.解释器&emsp;&emsp;3.事件驱动风格{{< /expand >}}
[![p9rOyqI.md.png](https://s1.ax1x.com/2023/05/11/p9rOyqI.md.png)](https://imgse.com/i/p9rOyqI)
{{< expand "学霸肯定对了">}}1.顺序批处理&emsp;&emsp;2.数据共享&emsp;&emsp;3.隐式调用风格&emsp;&emsp;4.适配&emsp;&emsp;5.虚拟机{{< /expand >}}
[![pCgRR1K.md.png](https://s1.ax1x.com/2023/07/09/pCgRR1K.md.png)](https://imgse.com/i/pCgRR1K)
[![pCgW9Nn.md.png](https://s1.ax1x.com/2023/07/09/pCgW9Nn.md.png)](https://imgse.com/i/pCgW9Nn)
{{< expand "学霸肯定对了">}}
[![pCgWkcT.md.png](https://s1.ax1x.com/2023/07/09/pCgWkcT.md.png)](https://imgse.com/i/pCgWkcT)
[![pCgWZB4.md.png](https://s1.ax1x.com/2023/07/09/pCgWZB4.md.png)](https://imgse.com/i/pCgWZB4)
{{< /expand >}}

## 2.8 架构风格具体实例

---

&emsp;&emsp;没有最好的架构，只有更适合具体业务场景的架构。分层架构的脆弱性在于：底层发生错误会导致整个系统无法正常运行、层与层之间引入通信机制势必造成性能下降。

### 2.8.1 从 C/S -> B/S -> 混合架构

&emsp;&emsp;属于层次架构风格的实例。

- 双层C/S架构

&emsp;&emsp;通过图示可以看出非常明显的缺点：将业务逻辑的代码嵌入进客户端，在早期互联网并不普及的情况下，频繁变更的业务逻辑代码和难以推广升级的客户端存在巨大矛盾。

[![p9sqZv9.md.png](https://s1.ax1x.com/2023/05/12/p9sqZv9.md.png)](https://imgse.com/i/p9sqZv9)

- 三层C/S架构

&emsp;&emsp;相比于双层C/S架构，三层C/S架构的优势在于：将业务逻辑层(功能层)单独拆分出来(独立于数据库服务器、用户客户端)放在单独的服务器上(应用服务端)，经常变更的业务逻辑代码并不会直接影响到客户端的使用。其劣势依然需要用户安装客户端(你可以认为就是手机中的APP)。

[![p9sqDPS.md.png](https://s1.ax1x.com/2023/05/12/p9sqDPS.md.png)](https://imgse.com/i/p9sqDPS)
[![p9sLpxH.md.png](https://s1.ax1x.com/2023/05/12/p9sLpxH.md.png)](https://imgse.com/i/p9sLpxH)

- B/S架构

&emsp;&emsp;相比于C/S架构，B/S架构也有自己的优缺点

&emsp;&emsp;优势：推广容易，不需要用户下载什么客户端之类的，只需要浏览器访问对应地址即可，这也就是早期各大厂都是从门户网站起家的。

&emsp;&emsp;劣势：响应速度较慢，早期只能整个提交页面数据(不能局部刷新)、其安全性较低等。

[![p9sLRQH.png](https://s1.ax1x.com/2023/05/12/p9sLRQH.png)](https://imgse.com/i/p9sLRQH)
- 混合架构

&emsp;&emsp;结合了C/S和B/S的优势，左图适用于企业内部的软件，对系统的维护有优势；右图适用于主流互联网公司的架构，查询用B/S、修改用C/S架构。

[![p9sxzJP.md.png](https://s1.ax1x.com/2023/05/12/p9sxzJP.md.png)](https://imgse.com/i/p9sxzJP)

### 2.8.2 MVC架构风格

&emsp;&emsp;属于层次架构风格的实例。

&emsp;&emsp;MVC(Model-View-Controller)，Model(模型) 是应用程序中用于处理应用程序数据逻辑的部分，通常模型对象负责在数
据库中存取数据。View(视图) 是应用程序中处理数据显示的部分，通常视图是依据模型数据创建的。Controller(控制器)是应用程序中处理用户交互的部分，通常控制器负责从视图读取数据，控制用户输入，并向模型发送数据。

&emsp;&emsp;MVC分为主动MVC和被动MVC(具体不用了解)，MVC架构的缺点在于MV之间没有解耦，不是严格的分层架构(严格的分层架构：当前层之和上下层之间有联系)

[![p9ym5FK.md.png](https://s1.ax1x.com/2023/05/12/p9ym5FK.md.png)](https://imgse.com/i/p9ym5FK)

&emsp;&emsp;在J2EE中（java相关的框架在考试中经常被拿来举例子，因此会java的很有优势），Model是EJB(Entity Bean/Session Bean)，View是JSP，Controller是Servlet。

### 2.8.3 MVP架构风格

&emsp;&emsp;属于层次架构风格的实例。

&emsp;&emsp;MVP(Model-View-Presenter)，~~注意：它不是LOL中的MVP~~，它是MVC的变种，它实现了MV之间的解耦。

[![p9ynxBR.md.png](https://s1.ax1x.com/2023/05/12/p9ynxBR.md.png)](https://imgse.com/i/p9ynxBR)

### 2.8.4 MVVM架构风格

&emsp;&emsp;属于层次架构风格的实例。

&emsp;&emsp;MVVM(Model-ViewModel-View),类似于vue中的双向数据绑定，View改变则ViewModel也改变，反之亦然。

[![p9ynzH1.md.png](https://s1.ax1x.com/2023/05/12/p9ynzH1.md.png)](https://imgse.com/i/p9ynzH1)

### 2.8.5 RIA架构风格

&emsp;&emsp;属于层次架构风格的实例。

&emsp;&emsp;RIA(富互联网架构)类似于综合了C/S和B/S架构的优点(C/S反应快，交互强，B/S易传播，B/S交互能力不那么强，一般以文字和图片为主)，它在首次加载初期比较慢，一旦加载完成使用就快多了。典型的例子就是在线网游、小程序。

### 2.8.6 基于服务的架构(SOA)

&emsp;&emsp;服务是一种为了满足某项业务需求的操作、规则等的逻辑组合，它包含一系列有序活动的交互，为实现用户目标提供支持。经典场景：对历史遗留系统进行集成。如下图：

[![pCddrGD.md.png](https://s1.ax1x.com/2023/06/28/pCddrGD.md.png)](https://imgse.com/i/pCddrGD)

[![p9glNbF.md.png](https://s1.ax1x.com/2023/05/15/p9glNbF.md.png)](https://imgse.com/i/p9glNbF)

&emsp;&emsp;1、服务构件粗粒度，传统构件细粒度居多。

&emsp;&emsp;2、服务构件的接口是标准的，主要是WSDL接口，传统构件常以具体API形式出现。

&emsp;&emsp;3、服务构件的实现与语言无关，传统构件绑定某种特定语言。

&emsp;&emsp;4、服务构件可以通过构件容器提供OoS的服务，传统构件完全由程序代码直接控制。

[![p9gsw36.md.png](https://s1.ax1x.com/2023/05/15/p9gsw36.md.png)](https://imgse.com/i/p9gsw36)

&emsp;&emsp;SOA的实现方式1：WebService；WSDL就是WebService接口对应的WSDL文件，该文件通过xml格式说明如何调用可以看作WebService的接口文档 (使用说明书)。

[![p9gssDe.md.png](https://s1.ax1x.com/2023/05/15/p9gssDe.md.png)](https://imgse.com/i/p9gssDe)

&emsp;&emsp;SOA的实现方式2：ESB 企业服务总线。

### 2.8.7 微服务

&emsp;&emsp;微服务顾名思义，就是很小的服务，所以它属于面向服务架构SOA的一种。

&emsp;&emsp;微服务架构是一种架构模式，它提倡将单一应用程序划分成一组小的服务，服务之间互相协调、互相配合，为用户提供最终价值。每个服务运行在其独立的进程中，服务与服务间采用轻量级的通信机制互相沟通 (通常是基于HTTP协议的RESTfulAPI)。每个服务都围绕着具体业务进行构建，并且能够被独立的部署到生产环境、类生产环境等。另外，应当尽量避免统一的、集中式的服务管理机制，对具体的一个服务而言，应根据业务上下文，选择合适的语言、工具对其进行构建。

&emsp;&emsp;其特点有：

&emsp;&emsp;1、小,且专注于做一件事情。

&emsp;&emsp;2、轻量级的通信机制。

&emsp;&emsp;3、松耦合、独立部署。

&emsp;&emsp;微服务和单体架构服务的对比，微服务类似于活字印刷，单体架构服务类似于版式印刷。

[![p9gsj2V.md.png](https://s1.ax1x.com/2023/05/15/p9gsj2V.md.png)](https://imgse.com/i/p9gsj2V)

微服务的优势：

&emsp;&emsp;1、技术异构

&emsp;&emsp;2、弹性扩展

&emsp;&emsp;3、在自动化部署情况下，能简化部署

&emsp;&emsp;4、可组织性

微服务的劣势：

&emsp;&emsp;1、分布式系统的复杂度

&emsp;&emsp;2、运维成本

&emsp;&emsp;3、服务间的依赖管理和测试

&emsp;&emsp;4、部署自动化

- SOA与微服务的对比

[![p9gyVxK.md.png](https://s1.ax1x.com/2023/05/15/p9gyVxK.md.png)](https://imgse.com/i/p9gyVxK)
[![p9gyMad.md.png](https://s1.ax1x.com/2023/05/15/p9gyMad.md.png)](https://imgse.com/i/p9gyMad)

### 2.8.8 MDA

&emsp;&emsp;模型驱动架构。是形式化方法下的产物。

&emsp;&emsp;**平台无关模型**通过变换工具转为**平台相关模型**，再通过变换工具转为**代码code**

[![p9gq4xO.md.png](https://s1.ax1x.com/2023/05/15/p9gq4xO.md.png)](https://imgse.com/i/p9gq4xO)
[![p9gqOit.md.png](https://s1.ax1x.com/2023/05/15/p9gqOit.md.png)](https://imgse.com/i/p9gqOit)
