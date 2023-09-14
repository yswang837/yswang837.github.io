---
weight: 9
title: "9) web架构设计"
---

## 1 web架构设计 ✅✅✅✅

---

&emsp;&emsp;主要围绕**高性能**、高可用、可维护等性能展开。

[![pC2SX0H.md.png](https://s1.ax1x.com/2023/07/09/pC2SX0H.md.png)](https://imgse.com/i/pC2SX0H)

### 1.1 单机到分层架构 ✅✅✅✅

[![pC2pSht.md.png](https://s1.ax1x.com/2023/07/09/pC2pSht.md.png)](https://imgse.com/i/pC2pSht)

### 1.2 应用服务器集群 ✅✅

&emsp;&emsp;此时需要做负载均衡和Session一致性问题。

[![pC2pijS.md.png](https://s1.ax1x.com/2023/07/09/pC2pijS.md.png)](https://imgse.com/i/pC2pijS)

### 1.3 负载均衡 ✅✅✅✅

&emsp;&emsp;随着业务的增长，信息系统的访问量和数据流量快速增加，采用负载均衡(Load Balance)方法可避免由此导致的系统性能下降甚至崩溃。

&emsp;&emsp;1、负载均衡通常由服务器端安装的附加软件来实现；

&emsp;&emsp;2、负载均衡可在不同地理位置、不同网络结构的服务器群之间进行；

&emsp;&emsp;3、负载均衡可使用户只通过一个IP地址或域名就能访问相应的服务器；

&emsp;&emsp;4、负载均衡能增加系统的吞吐量。

[![pC2pMcT.md.png](https://s1.ax1x.com/2023/07/09/pC2pMcT.md.png)](https://imgse.com/i/pC2pMcT)

&emsp;&emsp;在OSI七层模型中，有两个层次可以用作做负载均衡，分别是：应用层、传输层。一般来说传输层的负载均衡效率更高。

[![pC2pL80.md.png](https://s1.ax1x.com/2023/07/09/pC2pL80.md.png)](https://imgse.com/i/pC2pL80)

&emsp;&emsp;HTTP重定向：类似于在浏览器中打开某个网页的时候，发生跳转，跳转到另一台应用服务器上进行处理。

&emsp;&emsp;VPN是正向代理的代表，它是从客户端->服务器。反向代理服务器：从服务器->客户端，请求来了首先访问代理服务器，将请求分发给具体的应用服务器，由应用服务器来处理并相应。

[![pC29C5R.md.png](https://s1.ax1x.com/2023/07/09/pC29C5R.md.png)](https://imgse.com/i/pC29C5R)

&emsp;&emsp;DNS域名解析负载均衡：将一个域名绑定成多个IP，每次轮询到不同的IP即可实现分流；

&emsp;&emsp;将一个外部IP绑定为内部的多个IP，在网关的位置，通过硬件来动态地转换为内部可用IP，一般4层就采用了这个技术。

[![pC29QPI.md.png](https://s1.ax1x.com/2023/07/09/pC29QPI.md.png)](https://imgse.com/i/pC29QPI)

- 负载均衡算法

[![pC29win.md.png](https://s1.ax1x.com/2023/07/09/pC29win.md.png)](https://imgse.com/i/pC29win)

### 1.4 有状态和无状态问题 ✅✅✅

&emsp;&emsp;购物车就是有状态的。

[![pC29Ro9.md.png](https://s1.ax1x.com/2023/07/09/pC29Ro9.md.png)](https://imgse.com/i/pC29Ro9)

- Session一致性是为了解决有状态请求

&emsp;&emsp;(1) 有状态 (2)无状态 (3)无状态 (4)有状态 (5)无状态

[![pC29gZ4.md.png](https://s1.ax1x.com/2023/07/09/pC29gZ4.md.png)](https://imgse.com/i/pC29gZ4)

### 1.5 持久化技术ORM ✅✅✅

[![pC2CsfI.md.png](https://s1.ax1x.com/2023/07/09/pC2CsfI.md.png)](https://imgse.com/i/pC2CsfI)

### 1.6 数据库读写分离 ✅✅✅

[![pC2Cf0g.md.png](https://s1.ax1x.com/2023/07/09/pC2Cf0g.md.png)](https://imgse.com/i/pC2Cf0g)

### 1.7 缓存技术 ✅✅✅✅

[![pC2PijK.md.png](https://s1.ax1x.com/2023/07/09/pC2PijK.md.png)](https://imgse.com/i/pC2PijK)

[![pC2PQjf.md.png](https://s1.ax1x.com/2023/07/09/pC2PQjf.md.png)](https://imgse.com/i/pC2PQjf)

[![pC2P1u8.md.png](https://s1.ax1x.com/2023/07/09/pC2P1u8.md.png)](https://imgse.com/i/pC2P1u8)

&emsp;&emsp;由于redis比较重要，下面小结接着讲。

### 1.8 redis ✅✅✅✅

- redis 集群切片场景方式

[![pC2ertO.md.png](https://s1.ax1x.com/2023/07/09/pC2ertO.md.png)](https://imgse.com/i/pC2ertO)

[![pC2wDsI.md.png](https://s1.ax1x.com/2023/07/10/pC2wDsI.md.png)](https://imgse.com/i/pC2wDsI)

[![pC2wyeP.md.png](https://s1.ax1x.com/2023/07/10/pC2wyeP.md.png)](https://imgse.com/i/pC2wyeP)

- redis 分布式存储方案

[![pC2w6df.md.png](https://s1.ax1x.com/2023/07/10/pC2w6df.md.png)](https://imgse.com/i/pC2w6df)

- redis 数据类型

[![pC2wco8.md.png](https://s1.ax1x.com/2023/07/10/pC2wco8.md.png)](https://imgse.com/i/pC2wco8)

- redis 数据淘汰机制

[![pC2wRJg.md.png](https://s1.ax1x.com/2023/07/10/pC2wRJg.md.png)](https://imgse.com/i/pC2wRJg)

- redis 持久化技术

[![pC2wWWQ.md.png](https://s1.ax1x.com/2023/07/10/pC2wWWQ.md.png)](https://imgse.com/i/pC2wWWQ)

- redis 存在的问题

[![pC2BMuR.md.png](https://s1.ax1x.com/2023/07/10/pC2BMuR.md.png)](https://imgse.com/i/pC2BMuR)

[![pC2BlHx.md.png](https://s1.ax1x.com/2023/07/10/pC2BlHx.md.png)](https://imgse.com/i/pC2BlHx)

[![pC2BG4O.md.png](https://s1.ax1x.com/2023/07/10/pC2BG4O.md.png)](https://imgse.com/i/pC2BG4O)

### 1.9 CND 内容分发网络 ✅✅✅

&emsp;&emsp;镜像站，就近访问原则，为了提高网络访问，如京东物流。

[![pC2BrUf.md.png](https://s1.ax1x.com/2023/07/10/pC2BrUf.md.png)](https://imgse.com/i/pC2BrUf)

### 1.10 XML与Json ✅✅

[![pC2B2vj.md.png](https://s1.ax1x.com/2023/07/10/pC2B2vj.md.png)](https://imgse.com/i/pC2B2vj)

### 1.11 web应用服务器 ✅✅✅

[![pC2BxVx.md.png](https://s1.ax1x.com/2023/07/10/pC2BxVx.md.png)](https://imgse.com/i/pC2BxVx)

### 1.12 REST ✅✅

[![pC2DPRe.md.png](https://s1.ax1x.com/2023/07/10/pC2DPRe.md.png)](https://imgse.com/i/pC2DPRe)

### 1.13 响应式web设计 ✅✅

[![pC2rBh8.md.png](https://s1.ax1x.com/2023/07/10/pC2rBh8.md.png)](https://imgse.com/i/pC2rBh8)

### 1.14 中台 ✅✅

&emsp;&emsp;中台是一套结合互联网技术和行业特性，将企业核心能力以共享服务形式沉淀，形成“大中台、小前台”的组织和业务机制，供企业快速低成本的进行业务创新的企业架构。中台又可以进一步细分，比如业务中台，数据中台，XX中台。本质上，都是对企业通用能力在不同层面的沉淀，并对外能力开放。中台的践行者：Supercell: 芬兰移动游戏巨头，2015年世界游戏前10占5席，员工仅200多人，因使用中台具有小团队快速开发能力，后被腾讯86亿美金收购；阿里:2015年参观Supercell，而后推行中台。

[![pC2rbu9.md.png](https://s1.ax1x.com/2023/07/10/pC2rbu9.md.png)](https://imgse.com/i/pC2rbu9)

[![pC2rjN6.md.png](https://s1.ax1x.com/2023/07/10/pC2rjN6.md.png)](https://imgse.com/i/pC2rjN6)

[![pC2s8U0.md.png](https://s1.ax1x.com/2023/07/10/pC2s8U0.md.png)](https://imgse.com/i/pC2s8U0)

### 1.15 web系统分层 ✅✅

[![pC2sfrd.md.png](https://s1.ax1x.com/2023/07/10/pC2sfrd.md.png)](https://imgse.com/i/pC2sfrd)
