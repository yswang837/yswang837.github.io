---
weight: 11
title: 3.11 系统安全性和可靠性
---

## 课程内容提要

- 1. 安全基础技术
  - 对称与非对称加密&emsp;✅✅✅
  - 数字签名&emsp;&emsp;&emsp;&emsp;&emsp;✅✅✅
  - 信息摘要&emsp;&emsp;&emsp;&emsp;&emsp;✅✅✅
  - 数字证书
- 2. 网络安全
  - 网络各层次的安全保障&emsp;&emsp;✅✅✅
  - 网络攻击&emsp;&emsp;&emsp;&emsp;&emsp;✅✅
  - 等级保护标准&emsp;&emsp;&emsp;✅✅
  - 安全防范体系的层次
  - 信息安全体系结构
- 3. 可靠性相关基本概念&emsp;✅✅
- 4. 系统可靠性分析&emsp;&emsp;&emsp;✅✅✅✅
- 5. 软件可靠性设计&emsp;&emsp;&emsp;✅✅✅✅

## 1 安全基础基础

---

### 1.1 对称与非对称加密

一般用对称加密原文，已到达高速、节省空间的目的，一般用非对称加密保证数据的安全性。

- 对称加密：公钥和秘钥一样，或者说公钥可以推导出秘钥。

[![pCwWn2R.md.png](https://s1.ax1x.com/2023/06/29/pCwWn2R.md.png)](https://imgse.com/i/pCwWn2R)

- 非对称加密：公钥和秘钥不一样，或者说公钥不能推导出秘钥。

[![pCwWMKx.md.png](https://s1.ax1x.com/2023/06/29/pCwWMKx.md.png)](https://imgse.com/i/pCwWMKx)

&emsp;&emsp;非对称加密：加密解密规则，用接收方的公钥加密。

&emsp;&emsp;pa加密sa可解密，sa加密pa可解密。

[![pCwWUxI.md.png](https://s1.ax1x.com/2023/06/29/pCwWUxI.md.png)](https://imgse.com/i/pCwWUxI)

### 1.2 数字签名

&emsp;&emsp;数字签名是采用非对称加密技术，具体用发送方A的私钥Sa加密信息后，接收方如果用发送方的公钥Pa能解密，那么这个信息就一定是A发送的。

[![pCwWhLV.md.png](https://s1.ax1x.com/2023/06/29/pCwWhLV.md.png)](https://imgse.com/i/pCwWhLV)

### 1.3 信息摘要

&emsp;&emsp;相当于做md5，原文发生一小点变化，那摘要信息将完全不一样(雪崩效应)，下载安装包的时候，也会有个校验md5，就是指的这个。

[![pCwWrdS.md.png](https://s1.ax1x.com/2023/06/29/pCwWrdS.md.png)](https://imgse.com/i/pCwWrdS)

>例题
[![pCwfEOP.md.png](https://s1.ax1x.com/2023/06/29/pCwfEOP.md.png)](https://imgse.com/i/pCwfEOP)
{{< expand "学霸肯定对了">}}对称加密压缩信息，非对称加密传递对称秘钥，数字签名发送者不可抵赖，信息摘要防止信息被篡改。
[![pC0wZWT.md.png](https://s1.ax1x.com/2023/06/30/pC0wZWT.md.png)](https://imgse.com/i/pC0wZWT)
{{< /expand >}}
[![pC0wKOJ.md.png](https://s1.ax1x.com/2023/06/30/pC0wKOJ.md.png)](https://imgse.com/i/pC0wKOJ)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pC0wJfK.md.png](https://s1.ax1x.com/2023/06/30/pC0wJfK.md.png)](https://imgse.com/i/pC0wJfK)
{{< expand "学霸肯定对了">}}C B{{< /expand >}}

### 1.4 数字证书CA

[![pC0wcp8.md.png](https://s1.ax1x.com/2023/06/30/pC0wcp8.md.png)](https://imgse.com/i/pC0wcp8)

- PKI公钥体系

[![pC0w47n.md.png](https://s1.ax1x.com/2023/06/30/pC0w47n.md.png)](https://imgse.com/i/pC0w47n)
[![pC0wIkq.md.png](https://s1.ax1x.com/2023/06/30/pC0wIkq.md.png)](https://imgse.com/i/pC0wIkq)

## 2 网络安全

---

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

## 3 可靠性相关基本概念

---

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
[![pC2bT2Q.md.png](https://s1.ax1x.com/2023/07/10/pC2bT2Q.md.png)](https://imgse.com/i/pC2bT2Q)
[![pCRvawj.md.png](https://s1.ax1x.com/2023/07/11/pCRvawj.md.png)](https://imgse.com/i/pCRvawj)
{{< expand "学霸肯定对了">}}
[![pC2bbKs.md.png](https://s1.ax1x.com/2023/07/10/pC2bbKs.md.png)](https://imgse.com/i/pC2bbKs)
[![pCRvdTs.md.png](https://s1.ax1x.com/2023/07/11/pCRvdTs.md.png)](https://imgse.com/i/pCRvdTs)
{{< /expand >}}

## 课后习题

---

todo 习题
