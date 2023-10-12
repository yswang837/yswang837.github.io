---
weight: 2
title: "2) 软件架构风格"
---

# 2.软件架构风格 ✅✅✅✅✅

&emsp;&emsp;软件架构风格是指描述特定软件系统的组织方式和惯用模式。组织方式描述了系统的组成构件和这些构件之间的拓扑关系，惯用模式则反映众多系统共有的结构和语义。以下是常见风格的特点或应用：

&emsp;&emsp;批处理--->无用户交互，传统编译器(优先认为是批处理)，网络报文处理(优先认为是批处理)。

&emsp;&emsp;管道过滤器--->流式数据，弱用户交互，传统编译器，网络报文处理。

&emsp;&emsp;层次架构--->采用层次化架构风格的系统，划分的层次越多，系统性能越差。

&emsp;&emsp;过程控制--->控制系统，其特点是不断采集系统当前状态，与系统中的设定状态进行对比，并通过将当前状态与设定状态进行对比从而进行控制。

&emsp;&emsp;隐式调用--->回调机制，采用隐式调用架构风格的系统，可以通过处理函数的并发调用提高系统处理性能。注意把隐式调用转为显示调用并不能提高系统性能。

&emsp;&emsp;事件驱动系统--->注册事件处理的是回调函数，当某个事件发生时(例如键盘敲击、鼠标移动等)，系统会查找并选择合适的回调函数处理该事件，windows系统。

&emsp;&emsp;解释器--->运行时的系统自定义行为与改变的能力，采用解释器架构风格的系统，可以通过部分解释代码预先编译的方式提高系统性能。

&emsp;&emsp;规则系统--->在解释器的基础上增加经验规则，适用于专家系统。

&emsp;&emsp;黑板风格--->信号处理领域，语音识别系统是一个十分典型的专家系统，其特点是求解的正确结果不止一个，求解过程比较复杂，需要通过专家知识和反馈逐步得到正确结果。

&emsp;&emsp;虚拟机风格--->通过虚拟机架构屏蔽不同的硬件环境。

&emsp;&emsp;C2体系结构风格--->通过连接件绑定在一起的按照一组规则运作的并行构件网络。

&emsp;&emsp;数据仓库--->现代集成开发环境(现代编译器)。

下图是架构师考试中常见的架构风格及其子风格，接下来会详细介绍每一种风格。
[![p9rTTqf.md.png](https://s1.ax1x.com/2023/05/11/p9rTTqf.md.png)](https://imgse.com/i/p9rTTqf)

## 2.1 数据流风格 ✅✅✅✅✅

---

&emsp;&emsp;数据流风格以数据驱动的方式推进项目，其的典型应用有传统编译器、网络报文处理，它包含2个子风格：

&emsp;&emsp;1、批处理。做题要点：大量整体数据、无需用户交互

&emsp;&emsp;2、管道过滤器。做题要点：流式数据、弱用户交互，对于采用管道-过滤器架构风格的系统，可以通过引入过滤器的数据并发处理提高系统性能。



具体如下图：

[![p9rIyS1.md.png](https://s1.ax1x.com/2023/05/11/p9rIyS1.md.png)](https://imgse.com/i/p9rIyS1)
[![p9rI6Qx.md.png](https://s1.ax1x.com/2023/05/11/p9rI6Qx.md.png)](https://imgse.com/i/p9rI6Qx)

&emsp;&emsp;一个软件的架构设计是随着技术的不断进步而不断变化的。以编译器为例，其主流架构经历了批处理(或管道-过滤器)到数据共享为中心(数据仓库)的转变过程。早期的编译器采用批处理(或管道-过滤器)架构风格，以文本形式输入的代码被逐步转化为各种形式，最终生成可执行代码。现代的编译器采用以数据共享为中心的架构风格，主要关心编译过程中程序的中间表示。分析树是在语法分析阶段结束后才产生作为语义分析的输入，分析树是数据中心中重要的共享数据，为后续的语义分析提供了帮助。

## 2.2 调用/返回风格 ✅✅✅✅✅

---

&emsp;&emsp;调用/返回风格包含3个子风格：

&emsp;&emsp;1、主程序/子程序风格

&emsp;&emsp;2、面向对象风格，可以通过减少功能调用层次提高系统性能，注意对象管理层并不能提高系统性能，反而会降低性能(层次越多性能越差)。

&emsp;&emsp;3、分层风格，将在“2.8 架构风格具体实例”中详细说明

[![p9rIfTe.md.png](https://s1.ax1x.com/2023/05/11/p9rIfTe.md.png)](https://imgse.com/i/p9rIfTe)
[![p9rI5Yd.md.png](https://s1.ax1x.com/2023/05/11/p9rI5Yd.md.png)](https://imgse.com/i/p9rI5Yd)

## 2.3 独立构建风格 ✅✅✅✅✅

---

&emsp;&emsp;独立构建区别于返回/调用风格的点在于，相对松耦合，且放弃了对子程序的控制，它包含2个子风格：

&emsp;&emsp;1、进程通信

&emsp;&emsp;2、事件驱动系统（隐式调用）

[![p9rIIfA.md.png](https://s1.ax1x.com/2023/05/11/p9rIIfA.md.png)](https://imgse.com/i/p9rIIfA)
[![p9rIH6P.md.png](https://s1.ax1x.com/2023/05/11/p9rIH6P.md.png)](https://imgse.com/i/p9rIH6P)

## 2.4 虚拟机风格 ✅✅✅✅✅

---

&emsp;&emsp;虚拟机风格包含2个子风格：

&emsp;&emsp;1、解释器风格，做题关键字：需要自定义规则的场景

&emsp;&emsp;2、规则系统，做题关键字：在解释器的基础上增加经验规则；

[![p9rILm8.md.png](https://s1.ax1x.com/2023/05/11/p9rILm8.md.png)](https://imgse.com/i/p9rILm8)
[![p9rIO0S.md.png](https://s1.ax1x.com/2023/05/11/p9rIO0S.md.png)](https://imgse.com/i/p9rIO0S)

## 2.5 仓库风格 ✅✅✅✅✅

---

&emsp;&emsp;仓库风格包含2个子风格：

&emsp;&emsp;1、数据库系统

&emsp;&emsp;2、黑板系统

[![p9r7PdU.md.png](https://s1.ax1x.com/2023/05/11/p9r7PdU.md.png)](https://imgse.com/i/p9r7PdU)
[![p9rIzfs.md.png](https://s1.ax1x.com/2023/05/11/p9rIzfs.md.png)](https://imgse.com/i/p9rIzfs)
[![p9roppn.md.png](https://s1.ax1x.com/2023/05/11/p9roppn.md.png)](https://imgse.com/i/p9roppn)

## 2.6 闭环控制风格(过程风格) ✅✅✅✅✅

---

&emsp;&emsp;不适合于复杂的系统。

[![p9ro9lq.md.png](https://s1.ax1x.com/2023/05/11/p9ro9lq.md.png)](https://imgse.com/i/p9ro9lq)

## 2.7 C2架构风格 ✅✅✅✅✅

---

&emsp;&emsp;C2属于层次架构风格，做题要点：由构件和连接件组成。

[![p9roC60.md.png](https://s1.ax1x.com/2023/05/11/p9roC60.md.png)](https://imgse.com/i/p9roC60)

>例题
[![p9r7KeK.md.png](https://s1.ax1x.com/2023/05/11/p9r7KeK.md.png)](https://imgse.com/i/p9r7KeK)
{{< expand "学霸肯定对了">}}1.虚拟机&emsp;&emsp;2.数据流&emsp;&emsp;3.隐式调用&emsp;&emsp;4.解释器&emsp;&emsp;5.过程控制{{< /expand >}}
[![p9rq1FU.md.png](https://s1.ax1x.com/2023/05/11/p9rq1FU.md.png)](https://imgse.com/i/p9rq1FU)
{{< expand "学霸肯定对了">}}1.黑板&emsp;&emsp;2.解释器&emsp;&emsp;3.事件驱动风格{{< /expand >}}
[![p9rOyqI.md.png](https://s1.ax1x.com/2023/05/11/p9rOyqI.md.png)](https://imgse.com/i/p9rOyqI)
{{< expand "学霸肯定对了">}}1.顺序批处理&emsp;&emsp;2.数据共享&emsp;&emsp;3.隐式调用风格&emsp;&emsp;4.适配&emsp;&emsp;5.虚拟机{{< /expand >}}
>案例分析例题
[![pCgRR1K.md.png](https://s1.ax1x.com/2023/07/09/pCgRR1K.md.png)](https://imgse.com/i/pCgRR1K)
[![pCgW9Nn.md.png](https://s1.ax1x.com/2023/07/09/pCgW9Nn.md.png)](https://imgse.com/i/pCgW9Nn)
{{< expand "学霸肯定对了">}}
[![pCgWkcT.md.png](https://s1.ax1x.com/2023/07/09/pCgWkcT.md.png)](https://imgse.com/i/pCgWkcT)
[![pCgWZB4.md.png](https://s1.ax1x.com/2023/07/09/pCgWZB4.md.png)](https://imgse.com/i/pCgWZB4)
{{< /expand >}}

## 2.8 架构风格具体实例 ✅✅✅✅✅

---

&emsp;&emsp;没有最好的架构，只有更适合具体业务场景的架构。分层架构的脆弱性在于：底层发生错误可能会导致整个系统无法正常运行、层与层之间引入通信机制势必造成性能下降，层分的越多，性能越差。

### 2.8.1 从 C/S -> 混合架构 ✅✅✅✅

&emsp;&emsp;属于层次架构风格的实例。C/S系统开发时可以采用不同的分布式架构：双层C/S将频繁变动的业务逻辑代码(功能层)迁入到客户端上，三次C/S将客户端、功能层、数据层分别放在不同的地方，B/S不需要下载客户端，混合架构融合了C/S和B/S的优势。详情见下。

- 双层C/S架构

&emsp;&emsp;通过图示可以看出非常明显的缺点：将业务逻辑的代码嵌入进客户端，在早期互联网并不普及的情况下，频繁变更的业务逻辑代码和难以推广升级的客户端存在巨大矛盾。

[![p9sqZv9.md.png](https://s1.ax1x.com/2023/05/12/p9sqZv9.md.png)](https://imgse.com/i/p9sqZv9)

- 三层C/S架构

&emsp;&emsp;相比于双层C/S架构，三层C/S架构的优势在于：将业务逻辑层(或者叫功能层)单独拆分出来(独立于数据库服务器、用户客户端)放在单独的服务器上(应用服务端)，经常变更的业务逻辑代码并不会直接影响到客户端的使用。其劣势依然需要用户安装客户端(你可以认为就是手机中的APP)。

[![p9sqDPS.md.png](https://s1.ax1x.com/2023/05/12/p9sqDPS.md.png)](https://imgse.com/i/p9sqDPS)
[![pPyElVI.md.png](https://s1.ax1x.com/2023/09/07/pPyElVI.md.png)](https://imgse.com/i/pPyElVI)
[![pPyEmxe.md.png](https://s1.ax1x.com/2023/09/07/pPyEmxe.md.png)](https://imgse.com/i/pPyEmxe)

- B/S架构

&emsp;&emsp;相比于C/S架构，B/S架构也有自己的优缺点

&emsp;&emsp;优势：推广容易，不需要用户下载什么客户端之类的，只需要浏览器访问对应地址即可，这也就是早期各大厂都是从门户网站起家的。现在由于互联网的普及，推广和升级APP变得相对容易，也就会先出现APP(如抖音、拼多多)，后出现网页。

&emsp;&emsp;劣势：响应速度较慢，早期只能提交整个页面数据(不能局部刷新)、其安全性较低、用户体验相对较差等，现在基本上解决的挺好的了。
[![p9sLRQH.png](https://s1.ax1x.com/2023/05/12/p9sLRQH.png)](https://imgse.com/i/p9sLRQH)

- 混合架构

&emsp;&emsp;结合了C/S和B/S的优势，左图适用于企业内部的软件，对系统的维护有优势；右图适用于主流互联网公司的架构，查询用B/S、修改用C/S架构。总之，C/S更适合内部做修改，B/S更适合外部做查询。

[![p9sxzJP.md.png](https://s1.ax1x.com/2023/05/12/p9sxzJP.md.png)](https://imgse.com/i/p9sxzJP)

### 2.8.2 MVC架构风格 ✅✅✅

&emsp;&emsp;属于层次架构风格的实例。

&emsp;&emsp;MVC(Model-View-Controller)，Model(模型) 是应用程序中用于处理应用程序数据逻辑的部分，通常模型对象负责在数据库中存取数据。View(视图) 是应用程序中处理数据显示的部分，通常视图是依据模型数据创建的。Controller(控制器)是应用程序中处理用户交互的部分，通常控制器负责从视图读取数据，控制用户输入，并向模型发送数据。

&emsp;&emsp;MVC分为主动MVC和被动MVC(具体不用了解)，MVC架构的缺点在于MV之间没有解耦，不是严格的分层架构(严格的分层架构：当前层之和上下层之间有联系)

[![p9ym5FK.md.png](https://s1.ax1x.com/2023/05/12/p9ym5FK.md.png)](https://imgse.com/i/p9ym5FK)

&emsp;&emsp;在J2EE中(java相关的框架在考试中经常被拿来举例子，因此会java的很有优势)，Model是EJB(Enterprise JavaBeans)，View界面是JSP(Java Server Pages)；Controller是Servlet，用于分发客户请求、有效组织其他构建为客户端提供服务，其核心业务逻辑由Session Bean构建实现。

### 2.8.3 MVP架构风格 ✅✅

&emsp;&emsp;属于层次架构风格的实例。

&emsp;&emsp;MVP(Model-View-Presenter)，~~注意：它不是LOL中的MVP~~，它是MVC的变种，它实现了MV之间的解耦。

[![p9ynxBR.md.png](https://s1.ax1x.com/2023/05/12/p9ynxBR.md.png)](https://imgse.com/i/p9ynxBR)

### 2.8.4 MVVM架构风格 ✅✅

&emsp;&emsp;属于层次架构风格的实例。

&emsp;&emsp;MVVM(Model-ViewModel-View),类似于vue中的双向数据绑定，View改变则ViewModel也改变，反之亦然。

[![p9ynzH1.md.png](https://s1.ax1x.com/2023/05/12/p9ynzH1.md.png)](https://imgse.com/i/p9ynzH1)

### 2.8.5 RIA架构风格 ✅✅

&emsp;&emsp;属于层次架构风格的实例。

&emsp;&emsp;RIA(富互联网架构)类似于综合了C/S和B/S架构的优点(C/S反应快，交互强，B/S易传播，B/S交互能力不那么强，一般以文字和图片为主)，它在首次加载初期比较慢，一旦加载完成使用就快多了。典型的例子就是在线网游、小程序。

### 2.8.6 基于服务的架构SOA ✅✅✅✅✅

&emsp;&emsp;SOA(Service-Oriented Architecture)，服务是一种为了满足某项业务需求的操作、规则等的逻辑组合，它包含一系列有序活动的交互，为实现用户目标提供支持。服务可认为是标准化程度很高的一种构件。经典场景：对历史遗留系统进行集成。
[![p9glNbF.md.png](https://s1.ax1x.com/2023/05/15/p9glNbF.md.png)](https://imgse.com/i/p9glNbF)

&emsp;&emsp;1、服务构件粗粒度，传统构件细粒度居多。

&emsp;&emsp;2、服务构件的接口是标准的，主要是WSDL(Web Service Describe Language)接口，传统构件常以具体API(Application Program Interface)形式出现。

&emsp;&emsp;3、服务构件的实现与语言无关，传统构件绑定某种特定语言。

&emsp;&emsp;4、服务构件可以通过构件容器提供QOS的服务(即服务质量。在有限的带宽资源下，QoS为各种业务分配带宽，为业务提供端到端的服务质量保证。例如，语音、视频和重要的数据应用在网络设备中可以通过配置QoS优先得到服务)，传统构件完全由程序代码直接控制。

[![pCddrGD.md.png](https://s1.ax1x.com/2023/06/28/pCddrGD.md.png)](https://imgse.com/i/pCddrGD)

&emsp;&emsp;SOA的实现方式1：ESB企业服务总线。ESB提供了位置透明性的消息路由和寻址服务，ESB支持多种的消息传递范型，ESB支持多种数据格式及其相互转换。

[![p9gsw36.md.png](https://s1.ax1x.com/2023/05/15/p9gsw36.md.png)](https://imgse.com/i/p9gsw36)

&emsp;&emsp;SOA的实现方式2：Web Service；服务请求者可以通过域名或者IP直接访问服务提供者，但当服务过多、关系过于复杂、或者忘记了域名或者IP时，使得访问变得困难，此时服务注册中心就排上了用场，所有服务提供者需要将服务描述提供给注册中心，服务请求者只需要访问注册中心即可。基于Web Services实现的面向服务系统中，服务提供者、服务请求者和服务注册器之间的远程交互通过SOAP(简单对象访问协议)消息实现，服务内容描述通过WSDL(Web服务描述语言，可以看作服务使用说明书)标准实现，服务注册信息通过UDDI(服务统一描述、发现和集成)框架实现，通过BPEL/BPEL4WS (业务过程执行语言)将分散的、功能单一的Web服务组织成一个复杂的有机应用。



### 2.8.7 微服务 ✅✅✅✅

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

### 2.8.8 MDA ✅✅

&emsp;&emsp;模型驱动架构。是形式化方法下的产物。

&emsp;&emsp;**平台无关模型**通过变换工具转为**平台相关模型**，再通过变换工具转为**代码code**

[![p9gq4xO.md.png](https://s1.ax1x.com/2023/05/15/p9gq4xO.md.png)](https://imgse.com/i/p9gq4xO)
[![p9gqOit.md.png](https://s1.ax1x.com/2023/05/15/p9gqOit.md.png)](https://imgse.com/i/p9gqOit)
