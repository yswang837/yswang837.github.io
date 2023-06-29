---
weight: 11
title: 3.11 系统安全分析与设计
---
## 课程内容提要

- 1. 安全基础技术
  - 对称与非对称加密&emsp;✅✅✅
  - 数字签名&emsp;&emsp;&emsp;&emsp;&emsp;✅✅✅
  - 信息摘要&emsp;&emsp;&emsp;&emsp;&emsp;✅✅✅
- 2. 网络安全
  - 安全协议&emsp;&emsp;&emsp;&emsp;&emsp;✅✅✅
  - 网络攻击&emsp;&emsp;&emsp;&emsp;&emsp;✅✅
  - 等级保护标准&emsp;&emsp;&emsp;✅✅

## 1 安全基础基础

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
{{< expand "学霸肯定对了">}}{{< /expand >}}

## 课后习题

---

todo 习题