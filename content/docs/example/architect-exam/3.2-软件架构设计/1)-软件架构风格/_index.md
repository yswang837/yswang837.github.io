# 2.软件架构风格
&emsp;&emsp;架构风格反映了领域中众多系统所共有的**结构**和**语义**特性，并指导如何将各个**构件**有效地组织成一个完整的系统。架构风格定义了用于描述系统的术语表和一组指导构建系统的规则。下图是架构师考试中常见的架构风格及其子风格，接下来会详细介绍每一种风格。
[![p9rTTqf.md.png](https://s1.ax1x.com/2023/05/11/p9rTTqf.md.png)](https://imgse.com/i/p9rTTqf)
## 2.1 数据流风格
&emsp;&emsp;数据流风格以数据驱动的方式推进项目，其的典型应用有**传统编译器**、**网络报文处理**，它包含2个子风格：\
1、批处理。做题要点：**大量整体数据**、**无需用户交互**\
2、管道过滤器。做题要点：**流式数据**、**弱用户交互**\
具体如下图：
[![p9rIyS1.md.png](https://s1.ax1x.com/2023/05/11/p9rIyS1.md.png)](https://imgse.com/i/p9rIyS1)
[![p9rI6Qx.md.png](https://s1.ax1x.com/2023/05/11/p9rI6Qx.md.png)](https://imgse.com/i/p9rI6Qx)
## 2.2 调用/返回风格
&emsp;&emsp;调用/返回风格包含3个子风格：\
1、主程序/子程序风格\
2、面向对象风格\
3、分层风格\
[![p9rIfTe.md.png](https://s1.ax1x.com/2023/05/11/p9rIfTe.md.png)](https://imgse.com/i/p9rIfTe)
[![p9rI5Yd.md.png](https://s1.ax1x.com/2023/05/11/p9rI5Yd.md.png)](https://imgse.com/i/p9rI5Yd)


## 2.3 独立构建风格
&emsp;&emsp;独立构建区别于返回/调用风格的点在于，相对松耦合，且放弃了对子程序的控制，它包含2个子风格：\
1、进程通信\
2、事件驱动系统（隐式调用）\
[![p9rIIfA.md.png](https://s1.ax1x.com/2023/05/11/p9rIIfA.md.png)](https://imgse.com/i/p9rIIfA)
[![p9rIH6P.md.png](https://s1.ax1x.com/2023/05/11/p9rIH6P.md.png)](https://imgse.com/i/p9rIH6P)

## 2.4 虚拟机风格
&emsp;&emsp;虚拟机风格包含2个子风格：\
1、解释器风格，做题关键字：需要自定义规则的场景\
2、规则系统，做题关键字：在解释器的基础上增加经验规则

[![p9rILm8.md.png](https://s1.ax1x.com/2023/05/11/p9rILm8.md.png)](https://imgse.com/i/p9rILm8)
[![p9rIO0S.md.png](https://s1.ax1x.com/2023/05/11/p9rIO0S.md.png)](https://imgse.com/i/p9rIO0S)

## 2.5 仓库风格
&emsp;&emsp;仓库风格包含2个子风格：\
1、数据库系统\
2、黑板系统
[![p9r7PdU.md.png](https://s1.ax1x.com/2023/05/11/p9r7PdU.md.png)](https://imgse.com/i/p9r7PdU)
[![p9rIzfs.md.png](https://s1.ax1x.com/2023/05/11/p9rIzfs.md.png)](https://imgse.com/i/p9rIzfs)
[![p9roppn.md.png](https://s1.ax1x.com/2023/05/11/p9roppn.md.png)](https://imgse.com/i/p9roppn)
## 2.6 闭环控制风格(过程风格)
[![p9ro9lq.md.png](https://s1.ax1x.com/2023/05/11/p9ro9lq.md.png)](https://imgse.com/i/p9ro9lq)
## 2.7 C2架构风格
[![p9roC60.md.png](https://s1.ax1x.com/2023/05/11/p9roC60.md.png)](https://imgse.com/i/p9roC60)\
>例题
[![p9r7KeK.md.png](https://s1.ax1x.com/2023/05/11/p9r7KeK.md.png)](https://imgse.com/i/p9r7KeK)\
答案：
[![p9rq1FU.md.png](https://s1.ax1x.com/2023/05/11/p9rq1FU.md.png)](https://imgse.com/i/p9rq1FU)\
答案：
[![p9rOyqI.md.png](https://s1.ax1x.com/2023/05/11/p9rOyqI.md.png)](https://imgse.com/i/p9rOyqI)\
答案：
## 2.8 架构风格具体实例
&emsp;&emsp;没有最好的架构，只有更适合具体业务场景的架构。
### 2.8.1 从 C/S -> B/S -> 混合架构
- 双层C/S架构\
&emsp;&emsp;通过图示可以看出非常明显的缺点：将业务逻辑的代码嵌入进客户端，在早期互联网并不普及的情况下，频繁变更的业务逻辑代码和难以推广升级的客户端存在巨大矛盾。
[![p9sqZv9.md.png](https://s1.ax1x.com/2023/05/12/p9sqZv9.md.png)](https://imgse.com/i/p9sqZv9)
- 三层C/S架构\
&emsp;&emsp;相比于双层C/S架构，三层C/S架构的优势在于：将业务逻辑层单独拆分出来(独立于数据库服务器、用户客户端)放在单独的服务器上，经常变更的业务逻辑代码并不会直接影响到客户端的使用。其劣势依然需要用户安装客户端(你可以认为就是手机中的APP)
[![p9sqDPS.md.png](https://s1.ax1x.com/2023/05/12/p9sqDPS.md.png)](https://imgse.com/i/p9sqDPS)
[![p9sLpxH.md.png](https://s1.ax1x.com/2023/05/12/p9sLpxH.md.png)](https://imgse.com/i/p9sLpxH)
- B/S架构\
&emsp;&emsp;相比于C/S架构，B/S架构也有自己的优缺点\
优势：推广容易，不需要用户下载什么客户端之类的，只需要浏览器访问对应地址即可，这也就是早期各大厂都是从门户网站起家的。
劣势：响应速度较慢，早期只能整个提交页面数据(不能局部刷新)、其安全性较低等。
[![p9sLRQH.png](https://s1.ax1x.com/2023/05/12/p9sLRQH.png)](https://imgse.com/i/p9sLRQH)
- 混合架构

### 2.8.2 MVC架构风格

### 2.8.3 MVP架构风格

### 2.8.4 MVVM架构风格

### 2.8.5 RIA架构风格

### 2.8.6 基于服务的架构(SOA)

### 2.8.7 微服务

### 2.8.8 MDA
