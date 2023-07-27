---
weight: 11
title: 3.11 系统安全性和可靠性
---

## 课程内容提要

- 1. 安全基础技术
  - 对称加密&emsp;✅✅✅
  - 非对称加密✅✅✅
  - 信息摘要&emsp;&emsp;&emsp;&emsp;&emsp;✅✅✅
  - 数字签名&emsp;&emsp;&emsp;&emsp;&emsp;✅✅✅
  - 数字证书
- 2. 网络安全
  - 网络各层次的安全保障&emsp;&emsp;✅✅✅
  - 网络攻击&emsp;&emsp;&emsp;&emsp;&emsp;✅✅
  - 等级保护标准&emsp;&emsp;&emsp;✅✅
  - 安全防范体系的层次
  - 信息安全体系结构
  - 无线加密技术
- 3. 可靠性相关基本概念&emsp;✅✅
- 4. 系统可靠性分析&emsp;&emsp;&emsp;✅✅✅✅
- 5. 软件可靠性设计&emsp;&emsp;&emsp;✅✅✅✅

## 1 安全基础基础

---

&emsp;&emsp;安全性(security)是指系统在向合法用户提供服务的同时能够阻止非授权用户使用的企图或拒绝服务的能力。安全性是根据系统可能受到的安全威胁的类型来分类的。安全性又可划分为机密性、完整性、不可否认性及可控性等特性。其中，机密性保证信息不泄露给未授权的用户、实体或过程，完整性保证信息的完整和准确，防止信息被非法修改;不可否认性是指防止发送方否认发送过信息，可控性保证对信息的传播及内容具有控制的能力，防止为非法者所用。

&emsp;&emsp;一个完整的信息安全系统至少包含三类措施:技术方面的安全措施，管理方面的安全措施和相应的政策法律。信息安全的技术措施主要有:信息加密、数字签名、数据完整性保护、身份鉴别、访问控制、数据备份和灾难恢复、网络控制技术、反病毒技术、安全审计、业务填充、路由控制机制、公证机制等。

### 1.1 对称加密

一般用对称加密原文，已到达高速、节省空间的目的。

- 对称加密：公钥和秘钥一样，或者说公钥可以推导出秘钥。常见的对称加密算法有：DES、AES、RC-5、IDEA

[![pCwWn2R.md.png](https://s1.ax1x.com/2023/06/29/pCwWn2R.md.png)](https://imgse.com/i/pCwWn2R)

### 1.2 非对称加密

- 非对称加密：公钥和秘钥不一样，或者说公钥不能推导出秘钥。加密强度高但加密效率低，一般用非对称加密保证数据的安全性，秘钥分发相对简单。常见的非对称加密算法有：RSA。

[![pCwWMKx.md.png](https://s1.ax1x.com/2023/06/29/pCwWMKx.md.png)](https://imgse.com/i/pCwWMKx)

&emsp;&emsp;非对称加密：**加密解密规则，用接收方的公钥加密**。pa加密sa可解密，sa加密pa可解密。

[![pCwWUxI.md.png](https://s1.ax1x.com/2023/06/29/pCwWUxI.md.png)](https://imgse.com/i/pCwWUxI)

### 1.3 信息摘要

&emsp;&emsp;相当于做md5，原文发生一小点变化，那摘要信息将完全不一样(雪崩效应)，下载安装包的时候，也会有个校验md5，就是指的这个。

[![pCwWrdS.md.png](https://s1.ax1x.com/2023/06/29/pCwWrdS.md.png)](https://imgse.com/i/pCwWrdS)

### 1.4 数字签名

&emsp;&emsp;数字签名是采用非对称加密技术，具体用发送方A的私钥Sa加密信息后，接收方如果用发送方的公钥Pa能解密，那么这个信息就一定是A发送的。

[![pCwWhLV.md.png](https://s1.ax1x.com/2023/06/29/pCwWhLV.md.png)](https://imgse.com/i/pCwWhLV)

>例题
[![pCwfEOP.md.png](https://s1.ax1x.com/2023/06/29/pCwfEOP.md.png)](https://imgse.com/i/pCwfEOP)
{{< expand "学霸肯定对了">}}对称加密压缩信息，非对称加密传递对称秘钥，数字签名发送者不可抵赖，信息摘要防止信息被篡改。
[![pC0wZWT.md.png](https://s1.ax1x.com/2023/06/30/pC0wZWT.md.png)](https://imgse.com/i/pC0wZWT)
{{< /expand >}}
[![pC0wKOJ.md.png](https://s1.ax1x.com/2023/06/30/pC0wKOJ.md.png)](https://imgse.com/i/pC0wKOJ)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pC0wJfK.md.png](https://s1.ax1x.com/2023/06/30/pC0wJfK.md.png)](https://imgse.com/i/pC0wJfK)
{{< expand "学霸肯定对了">}}C B{{< /expand >}}

### 1.5 数字证书CA

&emsp;&emsp;每个数字证书上都会有其CA机构颁发的签名，我们可以通过验证CA机构对数字证书的签名来核实数字证书的有效性。如果证书有效，说明此网站经过CA机构中心的认证，是可信的网站，所以这个动作是用来验证网站真伪的，而不能验证客户方的真伪。

&emsp;&emsp;负责生成和签署数字证书的是证书机构CA、负责验证用户身份的是注册机构RA。

[![pC0wcp8.md.png](https://s1.ax1x.com/2023/06/30/pC0wcp8.md.png)](https://imgse.com/i/pC0wcp8)

- PKI公钥体系

[![pC0w47n.md.png](https://s1.ax1x.com/2023/06/30/pC0w47n.md.png)](https://imgse.com/i/pC0w47n)
[![pC0wIkq.md.png](https://s1.ax1x.com/2023/06/30/pC0wIkq.md.png)](https://imgse.com/i/pC0wIkq)

## 2 网络安全

---

&emsp;&emsp;信息系统面临多种类型的网络安全威胁。其中，**信息泄露是指信息被泄露或透露给某个非授权的实体;破坏数据完整性是指数据被非授权地进行修改;拒绝服务是指对信息或其他资源的合法访问被无条件地阻止；业务流分析是指通过对系统进行长期监听，利用统计分析方法对诸如通信频度、通信的信息流向、通信总量的变化等参数进行研究，从而发现有价值的信息和规律**。

&emsp;&emsp;网络安全漏洞通常是指网络节点的系统软件或应用软件在逻辑上的缺陷。

&emsp;&emsp;SYN Flooding攻击的原理是：利用TCP三次握手，恶意造成大量TCP半连接，耗尽服务器资源，导致系统拒绝服务。

### 2.1 网络各层次的安全保障

&emsp;&emsp;需要知道各个层用什么协议来保障安全。

&emsp;&emsp;PGP (Pretty Good Privacy):优良保密协议。

&emsp;&emsp;SSL (Secure Sockets Layer):安全套接字协议。

&emsp;&emsp;TLS (Transport Layer Security):传输层安全协议。

&emsp;&emsp;SET(Secure Electronic Transaction):安全电子交易协议。

&emsp;&emsp;IPSEC(Internet Protocol Security):互联网安全协议。

[![pC0wHpT.md.png](https://s1.ax1x.com/2023/06/30/pC0wHpT.md.png)](https://imgse.com/i/pC0wHpT)

>例题
[![pC00ph6.md.png](https://s1.ax1x.com/2023/06/30/pC00ph6.md.png)](https://imgse.com/i/pC00ph6)
{{< expand "学霸肯定对了">}}D{{< /expand >}}
[![pC00C9K.md.png](https://s1.ax1x.com/2023/06/30/pC00C9K.md.png)](https://imgse.com/i/pC00C9K)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

### 2.2 网络攻击

[![pC00icD.md.png](https://s1.ax1x.com/2023/06/30/pC00icD.md.png)](https://imgse.com/i/pC00icD)
[![pC00AnH.md.png](https://s1.ax1x.com/2023/06/30/pC00AnH.md.png)](https://imgse.com/i/pC00AnH)

>例题
[![pC00EBd.md.png](https://s1.ax1x.com/2023/06/30/pC00EBd.md.png)](https://imgse.com/i/pC00EBd)
{{< expand "学霸肯定对了">}}A{{< /expand >}}

### 2.3 等级保护标准

&emsp;&emsp;等级最低：用户自主。等级最高：访问验证。

&emsp;&emsp;银行：安全标记。广播电台：结构化保护

[![pC00n4P.md.png](https://s1.ax1x.com/2023/06/30/pC00n4P.md.png)](https://imgse.com/i/pC00n4P)
[![pC00ljg.md.png](https://s1.ax1x.com/2023/06/30/pC00ljg.md.png)](https://imgse.com/i/pC00ljg)

### 2.4 安全防范体系的层次

[![pC0BSbj.md.png](https://s1.ax1x.com/2023/06/30/pC0BSbj.md.png)](https://imgse.com/i/pC0BSbj)

>例题
[![pC05KPS.md.png](https://s1.ax1x.com/2023/06/30/pC05KPS.md.png)](https://imgse.com/i/pC05KPS)
{{< expand "学霸肯定对了">}}C D{{< /expand >}}

### 2.5 信息安全体系结构

&emsp;&emsp;自主访问控制：主体是用户，给用户赋予用些权限。访问控制列表：主体是资源，给资源的权限赋予给用户。强制访问控制：资源和用户都分级，高级的用户可以访问低级的资源。

[![pC05Q2Q.md.png](https://s1.ax1x.com/2023/06/30/pC05Q2Q.md.png)](https://imgse.com/i/pC05Q2Q)
[![pC058rn.md.png](https://s1.ax1x.com/2023/06/30/pC058rn.md.png)](https://imgse.com/i/pC058rn)

>案例分析例题
[![pC2bQEV.md.png](https://s1.ax1x.com/2023/07/10/pC2bQEV.md.png)](https://imgse.com/i/pC2bQEV)
[![pC2bRbt.md.png](https://s1.ax1x.com/2023/07/10/pC2bRbt.md.png)](https://imgse.com/i/pC2bRbt)
{{< expand "学霸肯定对了">}}
[![pC2Hv1H.md.png](https://s1.ax1x.com/2023/07/10/pC2Hv1H.md.png)](https://imgse.com/i/pC2Hv1H)
[![pC2bIPS.md.png](https://s1.ax1x.com/2023/07/10/pC2bIPS.md.png)](https://imgse.com/i/pC2bIPS)
{{< /expand >}}

### 2.6 无线加密技术

&emsp;&emsp;目前，无线网络中已存在好几种加密技术，由于安全性能的不同，无线设备的不同技术支持，支持的加密技术也不同，一般常见的有:WEP、WPA/WPA2、WPA-PSKWPA2-PSK。

&emsp;&emsp;1、WEP安全加密方式：WEP(有线等效保密)，一种数据加密算法，用于提供等同于有线局域网的保护能力。它的安全技术源自于名为RC4的RSA数据加密技术，是无线局域网WLAN的必要的安全防护层。目前常见的是64位WEP加密和128位WEP加密，WEP基本已被弃用。

&emsp;&emsp;2、WPA安全加密方式：WEP之后,人们将期望转向了其升级后的WPA，与之前WEF的静态密钥不同，WPA需要不断的转换密钥。WPA采用有效的密钥分发机制，可以跨越不同厂商的无线网卡实现应用，其作为WEP的升级版，在安全的防护上比WEP更为周密，主要体现在身份认证、加密机制和数据包检查等方面，而且它还提升了无线网络的管理能力。

&emsp;&emsp;3、WPA2：WPA2是IEEE 802.11i标准的认证形式,WPA2实现了802.111的强制性元素，特别是Michael算法被公认彻底安全的CCMP(计数器模式密码块链消息完整码协议)讯息认证码所取代、而RC4加密算法也被AES所取代。简言之，WPA2是WPA的增强版，安全性更高。

## 3 可靠性相关基本概念

---

&emsp;&emsp;可靠性(Reliability)是指产品在规定的条件下和规定的时间内完成规定功能的能力。常用的度量指标主要有故障率(或失效率)、平均失效等待时间、平均失效间隔时间和可靠度等。可靠度就是软件系统在规定的条件下、规定的时间内不发生失效的概率。

[![pC05dGF.md.png](https://s1.ax1x.com/2023/06/30/pC05dGF.md.png)](https://imgse.com/i/pC05dGF)

## 4 系统可靠性分析

---

### 4.1 可靠性指标

&emsp;&emsp;MTTF：平均失效等待时间，也叫平均无故障时间。

&emsp;&emsp;MTBF：平均失效间隔时间，也叫平均故障间隔时间。

[![pC05jzQ.md.png](https://s1.ax1x.com/2023/06/30/pC05jzQ.md.png)](https://imgse.com/i/pC05jzQ)

### 4.2 串并联系统可靠性计算

[![pC05zss.md.png](https://s1.ax1x.com/2023/06/30/pC05zss.md.png)](https://imgse.com/i/pC05zss)
[![pC0ISLn.md.png](https://s1.ax1x.com/2023/06/30/pC0ISLn.md.png)](https://imgse.com/i/pC0ISLn)

## 5 软件可靠性设计

---

### 5.1 影响软件可靠性的因素

&emsp;&emsp;分为5个方面。

[![pC0IAWF.md.png](https://s1.ax1x.com/2023/06/30/pC0IAWF.md.png)](https://imgse.com/i/pC0IAWF)

### 5.2 高可靠软件设计采用的设计方案

[![pC0IEz4.md.png](https://s1.ax1x.com/2023/06/30/pC0IEz4.md.png)](https://imgse.com/i/pC0IEz4)

- N版本程序设计

[![pC0Iue1.md.png](https://s1.ax1x.com/2023/06/30/pC0Iue1.md.png)](https://imgse.com/i/pC0Iue1)

- 恢复块设计(动态冗余)

[![pC0IYyd.md.png](https://s1.ax1x.com/2023/06/30/pC0IYyd.md.png)](https://imgse.com/i/pC0IYyd)

- 防卫式程序设计

&emsp;&emsp;对于程序中存在的错误和不一致性，通过在程序中包含错误检查代码和错误恢复代码，使得一旦错误发生，程序能撤销错误状态，恢复到一个已知的正确状态中去。

&emsp;&emsp;实现策略:错误检测、破坏估计、错误恢复。

- 双机容错

[![pC0IsSg.md.png](https://s1.ax1x.com/2023/06/30/pC0IsSg.md.png)](https://imgse.com/i/pC0IsSg)

>案例分析例题
[![pC2qlqI.md.png](https://s1.ax1x.com/2023/07/10/pC2qlqI.md.png)](https://imgse.com/i/pC2qlqI)
[![pCRvawj.md.png](https://s1.ax1x.com/2023/07/11/pCRvawj.md.png)](https://imgse.com/i/pCRvawj)
[![pC2bT2Q.md.png](https://s1.ax1x.com/2023/07/10/pC2bT2Q.md.png)](https://imgse.com/i/pC2bT2Q)

{{< expand "学霸肯定对了">}}
[![pC2bbKs.md.png](https://s1.ax1x.com/2023/07/10/pC2bbKs.md.png)](https://imgse.com/i/pC2bbKs)
[![pCRvdTs.md.png](https://s1.ax1x.com/2023/07/11/pCRvdTs.md.png)](https://imgse.com/i/pCRvdTs)
{{< /expand >}}

## 课后习题

---

todo 习题
