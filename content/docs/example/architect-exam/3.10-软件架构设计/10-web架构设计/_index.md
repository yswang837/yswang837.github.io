---
weight: 10
title: "10) web架构设计"
---

## todo

## 1 web架构设计

---

&emsp;&emsp;主要围绕**高性能**、高可用、可维护等性能展开。

[![pC2SX0H.md.png](https://s1.ax1x.com/2023/07/09/pC2SX0H.md.png)](https://imgse.com/i/pC2SX0H)

### 1.1 单机到数据库-web应用服务器分离

[![pC2pSht.md.png](https://s1.ax1x.com/2023/07/09/pC2pSht.md.png)](https://imgse.com/i/pC2pSht)

### 1.2 应用服务器集群

&emsp;&emsp;此时需要做负载均衡和Session一致性问题。

[![pC2pijS.md.png](https://s1.ax1x.com/2023/07/09/pC2pijS.md.png)](https://imgse.com/i/pC2pijS)

### 1.3 负载均衡

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

### 1.4 有状态和无状态问题

&emsp;&emsp;购物车就是有状态的。

[![pC29Ro9.md.png](https://s1.ax1x.com/2023/07/09/pC29Ro9.md.png)](https://imgse.com/i/pC29Ro9)

- Session一致性是为了解决有状态请求

&emsp;&emsp;(1) 有状态 (2)无状态 (3)无状态 (4)有状态 (5)无状态

[![pC29gZ4.md.png](https://s1.ax1x.com/2023/07/09/pC29gZ4.md.png)](https://imgse.com/i/pC29gZ4)

### 1.5 持久化技术ORM

[![pC2CsfI.md.png](https://s1.ax1x.com/2023/07/09/pC2CsfI.md.png)](https://imgse.com/i/pC2CsfI)

### 1.6 数据库读写分离

[![pC2Cf0g.md.png](https://s1.ax1x.com/2023/07/09/pC2Cf0g.md.png)](https://imgse.com/i/pC2Cf0g)

### 1.7 缓存技术

[![pC2PijK.md.png](https://s1.ax1x.com/2023/07/09/pC2PijK.md.png)](https://imgse.com/i/pC2PijK)

[![pC2PQjf.md.png](https://s1.ax1x.com/2023/07/09/pC2PQjf.md.png)](https://imgse.com/i/pC2PQjf)

[![pC2P1u8.md.png](https://s1.ax1x.com/2023/07/09/pC2P1u8.md.png)](https://imgse.com/i/pC2P1u8)

&emsp;&emsp;由于redis比较重要，下面小结接着讲。

### 1.8 redis

- redis 集群切片场景方式

[![pC2ertO.md.png](https://s1.ax1x.com/2023/07/09/pC2ertO.md.png)](https://imgse.com/i/pC2ertO)


- 