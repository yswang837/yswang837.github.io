---
weight: 4
title: 3.4 计算机网络
---

## 目录 ✌

&emsp;&emsp;本章内容在仅上午的选择题会涉及到，正常约占3~6分，占比4%~8%

## 1 TCP/IP协议族 ✅✅✅

---

&emsp;&emsp;HTTP协议是一种使用**明文数据传输**的网络协议，**缺省端口80**。HTTPS协议可以理解为HTTP协议的升级,就是在HTTP的基础上增加了**数据加密SSL/TLS**，所有的数据在传输过程中都是加密的，**缺省端口443**。

&emsp;&emsp;SSL(Secure Sockets Layer,安全套接层)及其继任者TLS(Transport Layer Security,传输层安全) 是为网络通信提供安全及数据完整性的一种安全协议，**在传输层对网络连接进行加密**。在设置电子邮箱时使用SSL/TLS协议，会保障邮箱更安全。

&emsp;&emsp;在客户机上运行nslookup查询某服务器名称时能解析出IP地址，查询IP地址时却不能解析出服务器名称，解决这问题的方法是 (为该服务器创建PTR记录，即反向地址解析协议)。

&emsp;&emsp;MIME(Multipurpose Internet Mail Extensions)多用途互联网邮件扩展类型；**它就是http的数据类型，格式是：大类型/小类型；MIME是设定某种扩展名的文件用一种应用程序来打开的方式类型，当该扩展名文件被访问的时候，浏览器会自动使用指定应用程序来打开。比如说：text/html、application/json、image/jpeg等**；它是一个互联网标准，扩展了电子邮件标准，使其能够支持:非ASCII字符文本，非文本格式附件 (二进制、声音、图像等);由多部分组成的消息体，包含非ASCII字符的头信息。

&emsp;&emsp;S/MIME在安全方面的功能又进行了扩展，它可以把MIME实体 (比如数字签名和加密信息等) 封装成安全对象。RFC2634定义了增强的安全服务，**例如具有接收方确认签收的功能，这样就可以确保接收者不能否认已经收到过的邮件**。

&emsp;&emsp;**PGP是安全的电子邮件协议**。它是一套用于消息加密、验证的应用程序，采用IDEA的散列算法作为加密与验证之用。每个公钥均绑定唯一的用户名或者E-mail地址。

&emsp;&emsp;**IPSec对IP数据包进行分组加密，IPSec主要用于开发新一代的VPN**。

&emsp;&emsp;**L2TP是创建VPN是需要用到的一个协议，主要是对传统拨号协议PPP的扩展，经常和IPSec协议连用**。

&emsp;&emsp;**PAP协议是PPP协议的一种握手协议，以保证PPP链接安全性**。

[![pCebHj1.md.png](https://s1.ax1x.com/2023/06/13/pCebHj1.md.png)](https://imgse.com/i/pCebHj1)
[![pCebqnx.md.png](https://s1.ax1x.com/2023/06/13/pCebqnx.md.png)](https://imgse.com/i/pCebqnx)

&emsp;&emsp;ARP攻击造成网络无法跨网段通信的原因是：伪造网关ARP报文使得数据包无法发送到网关。

### 1.1 TCP与UDP ✅✅✅

&emsp;&emsp;internet网的网络层核心协议是IP协议，而IP协议是一种分组交换的协议。

&emsp;&emsp;TCP端口号的作用是：应用层进程的寻址依据。

[![pCebvND.md.png](https://s1.ax1x.com/2023/06/13/pCebvND.md.png)](https://imgse.com/i/pCebvND)

>例题
[![pCeqp3d.md.png](https://s1.ax1x.com/2023/06/13/pCeqp3d.md.png)](https://imgse.com/i/pCeqp3d)
{{< expand "学霸肯定对了">}}C\
A项窗口大小不是固定的，B项前项纠错一般自行纠错，后项纠错一般才要求重发；D项IP不是虚电路，而是走路由器。所以选C{{< /expand >}}

### 1.2 DHCP与DNS ✅✅✅

- DNS(Domain Name System)

&emsp;&emsp;在Linux中，DNS的配置文件保存在/etc/resolv.conf。/etc/resolv.conf是DNS客户机的配置文件，用于设置DNS服务器的IP地址及DNS城名，还包含了主机的城名搜索顺序。该文件是由域名解析器 (一个根据主机名解析IP地址的库)使用的配置文件。它的格式比较简单，每行以一个关键字开头，后接一个或多个由空格隔开的参数（一般情况下，系统不会去回写用户程序、用户数据，即便系统去写了这两部分也不会对系统本身造成较大的影响。只有系统对系统本身的目录或关键文件回写异常，才有可能导致较大的影响，严重的会导致系统崩溃。举个例子，linux系统下root账号回写/etc/resolv.conf异常时，可能会导致系统DNS服务异常）。

[![pCmCD41.md.png](https://s1.ax1x.com/2023/06/13/pCmCD41.md.png)](https://imgse.com/i/pCmCD41)
[![pCmxskq.md.png](https://s1.ax1x.com/2023/06/14/pCmxskq.md.png)](https://imgse.com/i/pCmxskq)

>例题
[![pCmxhnJ.md.png](https://s1.ax1x.com/2023/06/14/pCmxhnJ.md.png)](https://imgse.com/i/pCmxhnJ)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCmx7h6.md.png](https://s1.ax1x.com/2023/06/14/pCmx7h6.md.png)](https://imgse.com/i/pCmx7h6)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

- DHCP(Dynamic Host Configuration Protocol)

&emsp;&emsp;DHCP客户端接收到服务器的DhcpOffer后，需要请求地址时发送DhcpRequest报文，如果服务器同意则发送DhcpAck,否则发送DhcpNack;当客户方接收到服务器的DhcpAck报文后，发现提供的地址存问题时发送DhcpDecline拒绝该地址。如：发送给DHCP客户端的地址已经被其他DHCP客户端使用，客户端会向服务器发送(DhcpDecline)信息包拒绝接受已经分配的地址信息。

&emsp;&emsp;可提供域名服务的包括本地缓存、本地域名服务器、权限域名服务器、顶级域名服务器以及根域名服务器。DNS主机名解析的查找顺序是，先查找客户端本地缓存，如果没有成功，则向DNS服务器发出解析请求。

&emsp;&emsp;本地缓存是内存中的一块区域，保存着最近被解析的主机名及其IP地址映像。由于解析程序缓存常驻内存中，所以比其他解析方法速度快。

&emsp;&emsp;当一个主机发出DNS查询报文时，这个查询报文就首先被送往该主机的本地域名服务器。本地域名服务器离用户较近，当所要查询的主机也属于同一个本地ISP时，该本地域名服务器立即就能将所查询的主机名转换为它的IP地址，而不需要再去询问其他的域名服务器。

&emsp;&emsp;每一个区都设置有域名服务器，即权限服务器，它负责将其管辖区内的主机域名转换为该主机的IP地址。在其上保存有所管辖区内的所有主机域名到IP地址的映射。

&emsp;&emsp;顶级域名服务器负责管理在本顶级域名服务器上注册的所有二级域名。当收到DNS查询请求时，能够将其管辖的二级域名转换为该二级域名的IP地址。或者是下一步应该找寻的域名服务器的IP地址。

&emsp;&emsp;根域名服务器是最高层次的域名服务器。每一个根域名服务器都要存有所有顶级域名服务器的IP地址和域名。当一个本地域名服务器对一个域名无法解析时，就会直接找到根域名服务器，然后根域名服务器会告知它应该去找哪一个顶级域名服务器进行查询。

[![pCmxOje.md.png](https://s1.ax1x.com/2023/06/14/pCmxOje.md.png)](https://imgse.com/i/pCmxOje)

>例题
[![pCmzP9f.md.png](https://s1.ax1x.com/2023/06/14/pCmzP9f.md.png)](https://imgse.com/i/pCmzP9f)
{{< expand "学霸肯定对了">}}A{{< /expand >}}

## 2 网络规划与设计 ✅✅✅✅

---

&emsp;&emsp;网络规划与设计包含5个阶段，它们分别是：需求分析、通信规范分析、逻辑网络设计、物理网络设计、实施阶段。这里重点看逻辑网络设计和物理网络设计，需求分析和通信规范分析的产物需要知道。工程造价估算是需求分析中的一个重要环节。

&emsp;&emsp;应用架构建模中要绘制的第一个物理数据流图 (PDFD)是网络架构DFD，它们不显示单位时间的数据流量，需要显示的信息包括服务器及其物理位置，客户端及其物理位置，处理器说明，传输协议。

[![pCmz8u4.md.png](https://s1.ax1x.com/2023/06/14/pCmz8u4.md.png)](https://imgse.com/i/pCmz8u4)

### 2.1 逻辑网络设计 ✅✅✅✅

[![pCmzw8K.md.png](https://s1.ax1x.com/2023/06/14/pCmzw8K.md.png)](https://imgse.com/i/pCmzw8K)

### 2.2 物理网络设计 ✅✅✅✅

[![pCmz25t.md.png](https://s1.ax1x.com/2023/06/14/pCmz25t.md.png)](https://imgse.com/i/pCmz25t)

>例题
[![pCmzIKg.md.png](https://s1.ax1x.com/2023/06/14/pCmzIKg.md.png)](https://imgse.com/i/pCmzIKg)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCmzban.md.png](https://s1.ax1x.com/2023/06/14/pCmzban.md.png)](https://imgse.com/i/pCmzban)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCmzq5q.md.png](https://s1.ax1x.com/2023/06/14/pCmzq5q.md.png)](https://imgse.com/i/pCmzq5q)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCmzzMF.md.png](https://s1.ax1x.com/2023/06/14/pCmzzMF.md.png)](https://imgse.com/i/pCmzzMF)
{{< expand "学霸肯定对了">}}D{{< /expand >}}

### 2.3 常见的网络设计 ✅✅✅

#### 2.3.1 层次网络设计 ✅✅✅

&emsp;&emsp;层次化网络设计应该遵循一些简单的原则，这些原则可以保证设计出来的网络更加具有层次的特性:

&emsp;&emsp;1、在设计时，设计者应该尽量控制层次化的程度，一般情况下，由核心层、汇聚层、接入层三个层次就足够了，过多的层次会导致整体网络性能的下降，并且会提高网络的延迟，但是方便网络故障排查和文档编写。

&emsp;&emsp;2、在接入层应当保持对网络结构的严格控制，接入层的用户总是为了获得更大的外部网络访问带宽，而随意申请其他的渠道访问外部网络是不允许的。

&emsp;&emsp;3、为了保证网络的层次性，不能在设计中随意加入额外连接，额外连接是指打破层次性，在不相邻层次间的连接，这些连接会导致网络中的各种问题，例如缺乏汇聚层的访问控制和数据报过滤等。

&emsp;&emsp;4、在进行设计时，应当首先设计接入层，根据流量负载、流量和行为的分析，对上层进行更精细的容量规划，再依次完成各上层的设计。

&emsp;&emsp;5、除去接入层的其他层次，应尽量采用模块化方式，每个层次由多个模块或者设备集合构成，每个模块间的边界应非常清晰。

[![pCnSpqJ.md.png](https://s1.ax1x.com/2023/06/14/pCnSpqJ.md.png)](https://imgse.com/i/pCnSpqJ)

>例题
[![pCnSAG6.md.png](https://s1.ax1x.com/2023/06/14/pCnSAG6.md.png)](https://imgse.com/i/pCnSAG6)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCnSERK.md.png](https://s1.ax1x.com/2023/06/14/pCnSERK.md.png)](https://imgse.com/i/pCnSERK)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

#### 2.3.2 网络冗余设计 ✅

[![pCnPdXT.md.png](https://s1.ax1x.com/2023/06/14/pCnPdXT.md.png)](https://imgse.com/i/pCnPdXT)

>例题
[![pCnFcy6.md.png](https://s1.ax1x.com/2023/06/14/pCnFcy6.md.png)](https://imgse.com/i/pCnFcy6)
{{< expand "学霸肯定对了">}}B{{< /expand >}}

#### 2.3.3 集成服务与区分服务 ✅✅

- 集成服务

&emsp;&emsp;IETF集成服务(IntServ)工作组根据服务质量的不同，把Internet服务分成了三种类型:

&emsp;&emsp;1、保证质量的服务(Guranteed Services):对带宽、时延抖动和丢包率提供定量的保证;

&emsp;&emsp;2、负载受控的服务 (Comrolled-load Services):提供一种类似于网络欠载情况下的服务，这是一种定性的指标;

&emsp;&emsp;3、尽力而为的服务(Best-Effort):这是Internet提供的一般服务，基本上无任何质量保证。

- 区分服务

&emsp;&emsp;区分服务要求每个IP分组都要根据IPv4协议头中的服务类型 (在IPv6中是通信类型)字段加上一个DS码点，然后内部路由器根据DS码点的值对分组进行调度和转发。

#### 2.3.4 软件定义网络 SDN ✅

&emsp;&emsp;SDN(Software Defined Netwok)的网络架构中包含:控制层、转发层和应用层，没有逻辑层。

## 3 网络存储 ✅✅

---

- 各式网络存储架构

[![pCneIfg.md.png](https://s1.ax1x.com/2023/06/14/pCneIfg.md.png)](https://imgse.com/i/pCneIfg)
[![pCneH6s.md.png](https://s1.ax1x.com/2023/06/14/pCneH6s.md.png)](https://imgse.com/i/pCneH6s)

- 磁盘阵列容量计算

&emsp;&emsp;会计算Raid3和5的磁盘容量就行

[![pCnn2If.md.png](https://s1.ax1x.com/2023/06/14/pCnn2If.md.png)](https://imgse.com/i/pCnn2If)

>例题
[![pCneX7V.md.png](https://s1.ax1x.com/2023/06/14/pCneX7V.md.png)](https://imgse.com/i/pCneX7V)
{{< expand "学霸肯定对了">}}C{{< /expand >}}
[![pCnnhRg.md.png](https://s1.ax1x.com/2023/06/14/pCnnhRg.md.png)](https://imgse.com/i/pCnnhRg)
{{< expand "学霸肯定对了">}}B B

3块80G的Raid5的容量=(3-1) * 80=160G，2块80G和1块40G的磁盘做Raid5的容量=(3-1) * 40=80G{{< /expand >}}

## 4 IPV6 ✅

---

- IPV6的特点

[![pCnuCe1.md.png](https://s1.ax1x.com/2023/06/14/pCnuCe1.md.png)](https://imgse.com/i/pCnuCe1)
[![pCnumyd.md.png](https://s1.ax1x.com/2023/06/14/pCnumyd.md.png)](https://imgse.com/i/pCnumyd)
[![pCKQiFI.md.png](https://s1.ax1x.com/2023/06/15/pCKQiFI.md.png)](https://imgse.com/i/pCKQiFI)

- IPV4->IPV6

[![pCnukFK.md.png](https://s1.ax1x.com/2023/06/14/pCnukFK.md.png)](https://imgse.com/i/pCnukFK)

- IPV6地址合法性判断

[![pCnuZSe.md.png](https://s1.ax1x.com/2023/06/14/pCnuZSe.md.png)](https://imgse.com/i/pCnuZSe)

>例题
[![pCKQkfP.md.png](https://s1.ax1x.com/2023/06/15/pCKQkfP.md.png)](https://imgse.com/i/pCKQkfP)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 5 网络接入技术 ✅

---

[![pCKQVl8.md.png](https://s1.ax1x.com/2023/06/15/pCKQVl8.md.png)](https://imgse.com/i/pCKQVl8)

&emsp;&emsp;5G网络的切片技术是将5G网络分割成多张虚拟网络，从而支持更多的应用。就是将一个物理网络切割成多个虚拟的端到端的网络,每个虚拟网络之间，包括网络内的设备、接入、传输和核心网,是逻辑独立的,任何一个虚拟网络发生故障都不会影响到其它虚拟网络。

[![pCKQ8pV.md.png](https://s1.ax1x.com/2023/06/15/pCKQ8pV.md.png)](https://imgse.com/i/pCKQ8pV)

## 6 综合布线 ✅✅

---

[![pCKQNm4.md.png](https://s1.ax1x.com/2023/06/15/pCKQNm4.md.png)](https://imgse.com/i/pCKQNm4)
[![pCKQwkR.md.png](https://s1.ax1x.com/2023/06/15/pCKQwkR.md.png)](https://imgse.com/i/pCKQwkR)
>例题
[![pCKQBfx.md.png](https://s1.ax1x.com/2023/06/15/pCKQBfx.md.png)](https://imgse.com/i/pCKQBfx)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 7 网络技术扩展 ✅

---

### 7.1 物联网 ✅

&emsp;&emsp;物联网属于层次型架构风格。

[![pCKQI9P.md.png](https://s1.ax1x.com/2023/06/15/pCKQI9P.md.png)](https://imgse.com/i/pCKQI9P)
[![pCKQgne.md.png](https://s1.ax1x.com/2023/06/15/pCKQgne.md.png)](https://imgse.com/i/pCKQgne)

- 感知层的关键技术

[![pCKQ7jS.md.png](https://s1.ax1x.com/2023/06/15/pCKQ7jS.md.png)](https://imgse.com/i/pCKQ7jS)
[![pCKQbng.md.png](https://s1.ax1x.com/2023/06/15/pCKQbng.md.png)](https://imgse.com/i/pCKQbng)

>例题
[![pCKQqBQ.md.png](https://s1.ax1x.com/2023/06/15/pCKQqBQ.md.png)](https://imgse.com/i/pCKQqBQ)
{{< expand "学霸肯定对了">}}D{{< /expand >}}

### 7.2 云计算 ✅

[![pCKllHH.md.png](https://s1.ax1x.com/2023/06/15/pCKllHH.md.png)](https://imgse.com/i/pCKllHH)

>例题
[![pCKldKS.md.png](https://s1.ax1x.com/2023/06/15/pCKldKS.md.png)](https://imgse.com/i/pCKldKS)
{{< expand "学霸肯定对了">}}A{{< /expand >}}

## 8 常见网络设备的原理或作用 ✅✅

---

### 8.1 交换机 ✅✅

&emsp;&emsp;交换机的初始mac地址表为空。

&emsp;&emsp;交换机接收到数据后，如果没有相应的表项，则采用ARP洪泛操作（即通过广播的方式转发）。

&emsp;&emsp;交换机通过读取输入帧中的源地址添加相应的MAC地址表项。

&emsp;&emsp;交换机的MAC地址表项是动态增长的。

### 8.2 路由器 ✅

&emsp;&emsp;路由器一般采取存储转发方式，需要对待转发的数据包进行重新拆包，分析其源地址和目的地址，再根据路由表对其进行路由和转发，而交换机采取的是直接转发方式，不对数据包的三层地址进行分析，因此路由器转发所带来的延迟要小于交换机。

### 8.3 网闸 ✅✅

&emsp;&emsp;网闸是使用带有多种控制功能的固态开关读写介质连接两个独立主机系统的信息安全设备。由于物理隔离，网闸所连接的两个独立主机系统之间不存在通信的物理连接、逻辑连接、信息传输命令、信息传输协议，不存在依据协议的信息包转发，只有数据文件的无协议“摆渡”，且对固态存储介质只有“读”和“写”两个命令。所以，物理隔离网闸从物理上隔离、阻断了具有潜在攻击可能的一切连接，使“黑客”无法入侵、无法攻击、无法破坏，实现了真正的安全。

&emsp;&emsp;使用安全隔离网闸的意义如下所述。

&emsp;&emsp;1.当用户的网络需要保证高强度的安全，同时又与其他不信任网络进行信息交换的情况下，如果采用物理隔离卡，用户必须使用开关在内外网之间来回切换，不仅管理起来非常麻烦，使用起来也非常不方便。如果采用防火墙，由于防火墙自身的安全很难保证，所以防火墙也无法防止内部信息泄漏和外部病毒、黑客程序的渗入，安全性无法保证。在这种情况下，安全隔离网闸能够同时满足这两个要求，弥补了物理隔离卡和防火墙的不足之处，是最好的选择。

&emsp;&emsp;2.对网络的隔离是通过网闸隔离硬件实现两个网络在链路层断开，但是为了交换数据，通过设计的隔离硬件在两个网络对应层次上进行切换，通过对硬件上的存储芯片的读写，完成数据的交换。

&emsp;&emsp;3.安装了相应的应用模块之后，安全隔离网闸可以在保证安全的前提下，使用户可以浏览网页、收发电子邮件、在不同网络上的数据库之间交换数据，并可以在网络之间交换定制的文件。

## 9 路由的管理距离 ✅

---

&emsp;&emsp;若管理距离为15，则这个路由的管理距离小于外部BGP的管理距离，所以该路由信息比较可靠。

[![pCr61mV.md.png](https://s1.ax1x.com/2023/07/03/pCr61mV.md.png)](https://imgse.com/i/pCr61mV)

## 10 网络延迟 ✅✅

---

&emsp;&emsp;网络中的延迟产生与以下几个方面有关:运算、读取和写入、数据传输以及数据传输过程中的拥塞所带来的延迟。在网络中，数据读写的速率较之于数据计算和传输的速率要大得多，所以数据读写的延迟是影响网络延迟的最大的因素。

&emsp;&emsp;在对等网络中，由于采用总线式的连接，因此网络中的终端数量越多，终端所能够分配到的转发时隙就越小，所带来的延迟也就越大。

&emsp;&emsp;路由器一般采取存储转发方式，需要对待转发的数据包进行重新拆包，分析其源地址和目的地址，再根据路由表对其进行路由和转发，而交换机采取的是直接转发方式，不对数据包的三层地址进行分析，因此路由器转发所带来的延迟要小于交换机。

&emsp;&emsp;数据在Internet中传输时，由于互联网中的转发数据量大且所需经过的点多，势必会带来更大的延迟。

## 11 层次化网络编址 ✅

---

&emsp;&emsp;层次化编址是一种对地址进行结构化设计的模型，使用地址的左半部的号码可以体现大块的网络或者节点群，而才半部可以体现单个网络或节点。层次化编址的主要优点在于可以实现层次化的路由选择，有利于在网络互联路由设备之间发现网络拓扑。

&emsp;&emsp;设计人员在进行地址分配时，为了配合实现层次化的路由器，必须遵守一条简单的规则:如果网络中存在分支管理，而且一台路由器负责连接上级和下级机构，则分配给这些下级机构网段应该属于一个连续的地址空间，并且这些连续的地址空间可以用一个子网或者超网段表示。

## 12 Kerberos协议 ✅

---

&emsp;&emsp;采用Kerberos系统进行认证时，可以在报文中加入时间戳来防止重放攻击。

&emsp;&emsp;Kerberos提供了一种单点登录 (SSO)的方法。考虑这样-个场景，在一个网络中有不同的服务器，比如，打印服务器、邮件服务器和文件服务器。这些服务器都有认证的需求。很自然的，让每个服务器自己实现一套认证系统是不合理的，而是提供一个中心认证服务器(AS-AuthenticationServer)供所有应用服务器使用。这样任何客户端就只需维护，一个密码就能登录所有服务器。因此，在Kerberos系统中至少有三个角色:认证服务器(AS)，客户端(Client)和应用服务器 (Server)。客户端和应用服务器将在AS的帮助下完成相互认证。在Kerberos系统中，客户端和应用服务器都有一个唯一的名字。同时，客户端和服务器都有自己的密码，并且它们的密码只有自己和认证服务器AS知道。客户端在进行认证时，需首先向密钥分发中心(注意不是CA)来申请初始票据。

&emsp;&emsp;第三方认证服务的两种体制分别是Kerberos和PKI

## 课后习题

---

todo 计算机网络习题
