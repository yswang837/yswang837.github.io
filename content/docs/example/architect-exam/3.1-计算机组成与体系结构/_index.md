## 课程内容提要 🏁

- 1. 计算机结构&emsp;&emsp;&emsp;&emsp;✅
- 2. 存储系统&emsp;&emsp;&emsp;&emsp;&emsp;✅✅✅✅
- 3. 数据传输控制方式&emsp;✅
- 4. 总线&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;✅✅
- 5. CISC与RISC  &emsp;  &emsp;&emsp;✅✅
- 6. 流水线&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;✅✅
- 7. 校验码&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;✅
- 8. 嵌入式&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;✅

## 1 计算机结构
&emsp;&emsp;计算机的硬件包含5大组成：**控制器**、**运算器**、**存储器**、**输入设备**和**输出设备**。**冯诺依曼**(一般用于pc处理器，指令和数据存储在一起、指令和数据都是通过相同的数据总线传输，通过不同的周期来区分数据和指令)，**哈佛结构**(一般用于嵌入式系统处理器DSP，指令和数据可并行分开存储与传输)，CPU依据指令周期的不同阶段来区分二进制的指令和数据，因为在指令周期的不同阶段指令会命令CPU分别去取指令或者数据。它们之间的交互如下图：
[![p9DeARs.md.png](https://s1.ax1x.com/2023/05/10/p9DeARs.md.png)](https://imgse.com/i/p9DeARs)\
&emsp;&emsp;别的部件会在后面的章节详细讲解，这里是说运算器和控制器。
### 1.1 运算器

&emsp;&emsp;算术逻辑单元ALU：实现对数据的算术和逻辑运算。\
&emsp;&emsp;累加寄存器AC：运算结果或源操作数的存放区。\
&emsp;&emsp;数据缓冲寄存器DR：暂时存放内存的指令或数据。\
&emsp;&emsp;状态条件寄存器PSW：保存指令运行结果的条件码内容，如溢出标志等。
### 1.2 控制器

&emsp;&emsp;**程序计数器PC**：存储下一条要执行指令的地址。\
&emsp;&emsp;指令寄存器IR：存储即将执行的指令。\
&emsp;&emsp;指令译码器ID：对指令中的操作码字段进行分析解释。\
&emsp;&emsp;时序部件：提供时序控制信号。
>例题
[![p9DnRPg.md.png](https://s1.ax1x.com/2023/05/10/p9DnRPg.md.png)](https://imgse.com/i/p9DnRPg)\
{{< expand "学霸肯定对了">}}答案：A\
计算机执行程序时，在一个指令周期的过程中，为了能够从内存中读指令操作码，首先是将程序计数器(PC)的内容送到地址总线上，PC->IR。{{< /expand >}}
## 2 存储系统
&emsp;&emsp;整体采用分层的思想，主要是解决速度、容量和成本之间的矛盾。如下图：
[![p9DutLq.md.png](https://s1.ax1x.com/2023/05/10/p9DutLq.md.png)](https://imgse.com/i/p9DutLq)
### 2.1 高速缓存Cache
&emsp;&emsp;高速缓存Cache用来存储当前最活跃的程序和数据，直接与CPU交互，位于CPU和主存之间,容量小，速度为内存的5-10倍，其内容是主存(内存)的拷贝，对于**程序员来说是透明的**。Cache由控制部分和存储器组成，存储器存储数据，控制部分判断CPU要访问的数据是否在Cache中，在则命中不在则依据一定的算法从主存中替换。\
地址映射：在CPU工作时，送出的是主存单元的地址，而应从Cache存储器中读/写信息。这就需要将主存地址转换为Cache存储器地址，这种地址的转换称为地址映像，由硬件自动完成映射。\
Cache的功能：\
&emsp;&emsp;1.提高CPU数据输入输出的速率，突破冯·诺依曼瓶颈，即突破CPU与存储系统间数据传送带宽限制。\
&emsp;&emsp;2.在计算机的存储系统体系中(除cpu中的寄存器外)，Cache是访问速度最快的层次。\
&emsp;&emsp;3.Cache对程序员来说是透明的。\
&emsp;&emsp;4.使用Cache改善系统性能的依据是程序的局部性原理(总的来说，在CPU运行时，所访问的数据会趋向于一个较小的局部时空内。包括下面两个方面:
**时间局部性**原理:如果一个数据项正在被访问，那么在近期它很可能会被再次访问，即在相邻的时间里会访问同一个数据项。**空间局部性**原理:在最近的将来会用到的数据的地址和现在正在访问的数据地址很可能是相近的，即相邻的空间地址会被连续访问。)\
Cache的命中率：\
&emsp;&emsp;当CPU所访问的数据在Cache中时，命中，直接丛Cache中读取数据，设读取一次Cache时间为1ns，若CPU访问的数据不在Cache中，则需要从内存中读取，设读取一次内存的时间为1000ns，若在CPU多次读取数据过程中，有90%命中Cache，则CPU读取一次的平均时间为(90% * 1 + 10% * 1000)ns
>例题
[![p9D4n8x.md.png](https://s1.ax1x.com/2023/05/10/p9D4n8x.md.png)](https://imgse.com/i/p9D4n8x)\
{{< expand "学霸肯定对了">}}B{{< /expand >}}
[![p9D4JIA.md.png](https://s1.ax1x.com/2023/05/10/p9D4JIA.md.png)](https://imgse.com/i/p9D4JIA)\
{{< expand "学霸肯定对了">}}D{{< /expand >}}
### 2.2 主存(内存)编址计算
&emsp;&emsp;主存如图所示，可以看图试着回答红色框线里面的问题，看完应该知道32位机器和64位机器大概是啥意思了。
[![p9D5gTH.md.png](https://s1.ax1x.com/2023/05/10/p9D5gTH.md.png)](https://imgse.com/i/p9D5gTH)\
**特别提醒**：不要硬算，要化简为二进制或者十进制来算。
**存储单元个数**=最大地址-最小地址+1
- 编址方式
  - 按字编址：一个存储单元存储的是一个字，最小寻址单位是一个字。
  - 按字节编址：一个存储单元存储的是一个字节，最小寻址单位是一个字节。

**总容量**=存储单元个数*单个存储单元所占大小\
**单位换算**：1GB=1024MB，1MB=1024KB，1KB=1024Byte，1Byte=8bit。
>例题
[![p9h0daQ.md.png](https://s1.ax1x.com/2023/05/19/p9h0daQ.md.png)](https://imgse.com/i/p9h0daQ)\
{{< expand "学霸肯定对了">}}答案：B C\
总容量=BFFFFH+1-80000H=40000H，转换为十进制为：4 * 16^4=262144，因为按字节编址，所以总容量为262144字节，即262144/1024=256KB，16k * 4bit = 8k * 8bit(1字节=8bit)，所以用这种芯片存这些数据，所需的芯片数量为：256/8=32片
{{< /expand >}}
### 2.3 磁盘管理
&emsp;&emsp;磁盘有正反两个盘面，每个盘面有多个同心圆，每个同心圆是一个磁道，每个同心圆又被划分为多个扇区，数据就被存放在一个个扇区中。\
[![p9hrBPH.png](https://s1.ax1x.com/2023/05/19/p9hrBPH.png)](https://imgse.com/i/p9hrBPH)\
&emsp;&emsp;磁头首先要寻找到对应的磁道，然后等待磁盘进行周期旋转，旋转到指定的扇区，才能读取到对应的数据，因此，会产生寻道时间和等待时间。其**公式**为：
存取时间=寻道时间+等待时间(平均定位时间+转动延迟)
- 磁盘调度算法
  - 先来先服务FCFS:根据进程请求访问磁盘的先后顺序进行调度。
  - 最短寻道时间优先SSTF:请求访问的磁道与当前磁道最进的进程优先调度，使得每次的寻道时间最短。会产生“饥饿”现象，即远处进程可能永远无法访问。
  - 扫描算法SCAN:又称“电梯算法”，磁头在磁盘上双向移动，其会选择离磁头当前所在磁道最近的请求访问的磁道，并且与磁头移动方向一致，磁头永远都是从里向外或者从外向里一直移动完才掉头。
  - 单向扫描调度算法CSCAN: 与电梯算法类似，与SCAN不同的是，其只做单向移动，即只能从里向外或者从外向里。
>例题
[![p9hsNSs.md.png](https://s1.ax1x.com/2023/05/19/p9hsNSs.md.png)](https://imgse.com/i/p9hsNSs)\
{{< expand "学霸肯定对了">}}答案：D{{< /expand >}}
[![p9hsWOx.md.png](https://s1.ax1x.com/2023/05/19/p9hsWOx.md.png)](https://imgse.com/i/p9hsWOx)\
{{< expand "学霸肯定对了">}}答案：D\
读取一个块需要的时间：10*10ms(移动)+100ms(延迟)+2ms(传输)=202ms，读取100个块需要的时间：100ms * 202ms = 20200ms
{{< /expand >}}
>例题
[![p9xx6hT.md.png](https://s1.ax1x.com/2023/06/01/p9xx6hT.md.png)](https://imgse.com/i/p9xx6hT)
{{< expand "学霸肯定对了">}}答案：C B\
由题意可知每个扇区存放逻辑记录，处理单个记录的延时为：33/11+3=6ms，由于磁头处于r0的开始处，且是单缓冲区顺序处理这些记录，所以6+10*(33+3)=366；若对存储信息进行优化，优化后为：r0r6r1r7r2r8r3r9r4r10r5，r0和r5收尾相接形成一个完整的磁道。此时只需要转2圈就可以把数据处理完。

{{< /expand >}}
## 3 数据传输控制方式
### 3.1 程序查询方式
**程序控制(查询)方式**:CPU主动查询外设是否完成数据传输，效率极低。
### 3.2 程序中断方式
**程序中断方式**: 外设完成数据传输后，向CPU发送中断，等待CPU处理数据，效率相对较高，中断响应时间指的是从发出中断请求到开始进入中断处理程序;中断处理时间指的是从中断处理开始到中断处理结束。中断向量提供中断服务程序的入口地址。多级中断嵌套，使用堆栈来保护断点和现场。
### 3.3 DMA方式
**DMA方式(直接主存存取)**:CPU只需完成必要的初始化等操作，数据传输的整个过程都申。
DMA控制器来完成，在主存和外设之间建立直接的数据通路，效率很高。
>例题
[![p9hyPpj.md.png](https://s1.ax1x.com/2023/05/19/p9hyPpj.md.png)](https://imgse.com/i/p9hyPpj)\
{{< expand "学霸肯定对了">}}答案：D C{{< /expand >}}
[![p9hyFcn.md.png](https://s1.ax1x.com/2023/05/19/p9hyFcn.md.png)](https://imgse.com/i/p9hyFcn)\
{{< expand "学霸肯定对了">}}答案：D{{< /expand >}}
## 4 总线
&emsp;&emsp;总线(Bus)，是指计算机设备和设备之间传输信息的公共数据通道。总线是连接计算机硬件系统内多种设备的通信线路，它的一个重要特征是由总线上的所有设备共享，因此可以将计算机系统内的多种设备连接到总线上。一条总线同一时刻仅允许一个设备发送，但允许多个设备接收，所以总线是半双工模式。\
&emsp;&emsp;总线具体分为数据总线(并行数据传输位数)、地址总线(系统可管理的内存空间的大小) 、控制总线(传送控制命令)。
>例题
[![p9h6vFS.md.png](https://s1.ax1x.com/2023/05/19/p9h6vFS.md.png)](https://imgse.com/i/p9h6vFS)\
{{< expand "学霸肯定对了">}}答案：B{{< /expand >}}
[![p9hcSzj.md.png](https://s1.ax1x.com/2023/05/19/p9hcSzj.md.png)](https://imgse.com/i/p9hcSzj)\
{{< expand "学霸肯定对了">}}答案：C{{< /expand >}}
## 5 CISC与RISC
[![p9hcPLq.md.png](https://s1.ax1x.com/2023/05/19/p9hcPLq.md.png)](https://imgse.com/i/p9hcPLq)
## 6 流水线
**流水线时间计算**\
**流水线周期**:指令分成不同执行段(取址、分析、执行)，其中执行时间最长的段为流水线周期。\
**流水线执行时间**:1条指令总执行时间+ (总指令条数-1)*流水线周期。\
**流水线吞吐率计算**:吞叶率即单位时间内执行的指今条数。即：指令条数/流水线执行时间\
**流水线的加速比计算**:加速比即使用流水线后的效率提升度，即比不使用流水线快了多少倍，越高表明流水线效率越高。即：不使用流水线执行时间/使用流水线执行时间。\
[![p9hcNSH.md.png](https://s1.ax1x.com/2023/05/19/p9hcNSH.md.png)](https://imgse.com/i/p9hcNSH)
>例题
[![p9hca6A.md.png](https://s1.ax1x.com/2023/05/19/p9hca6A.md.png)](https://imgse.com/i/p9hca6A)\
{{< expand "学霸肯定对了">}}答案：D C B C\
&emsp;&emsp;解析：设每个盘块儿读入缓冲区的时间为t1、缓冲区送入用户区的时间为t2、用户区处理每个盘块儿的时间为t3，为了能够代入**流水线执行时间**的公式，需要将题目转成标准的流水线。\
&emsp;&emsp;对于单缓冲区而言，需要将3阶段流水线转换成2阶段流水线，即第一阶段为t1+t2，第二阶段为t3，所以：流水线执行时间=1条指令总执行时间+ (总指令条数-1)*流水线周期 = (t1+t2)+t3 + (10-1) * 20 = 201\
&emsp;&emsp;对于双缓冲区而言，题目已经是标准流水线了，可以直接带入公式，所以：流水线执行时间=1条指令总执行时间+ (总指令条数-1)*流水线周期 = t1+t2+t3 + (10 - 1) * 15 = 156\
&emsp;&emsp;流水线的吞吐率，由题目可知，已是标准流水线，可直接带入公式算吞吐率，设执行了N条指令，n/9t+(n-1)*3t，即(n/(3n+6)) * (1/t)，当n趋于无穷大时，得到最大吞吐率为1/3t\
&emsp;&emsp;流水线的加速比=不使用流水线执行时间/使用流水线执行时间，不使用流水线执行时间=10*(2+1+3+1+2)=90，使用流水线执行时间=9+(10-1)*3=36，即90/36=5/2
{{< /expand >}}
## 7 校验码
### 7.1 奇偶校验码
&emsp;&emsp;奇偶校验码:在编码中增加1位校验位来使编码中1的个数为奇数(奇校验)或者偶数(偶校验)，编码中，含有奇数个1，发送给接收方，接收方收到后，会计算收到的编码有多少个1，如果是奇数个，则无误，是偶数个，则有误。
### 7.2 循环冗余码
[![p9hcq1J.md.png](https://s1.ax1x.com/2023/05/19/p9hcq1J.md.png)](https://imgse.com/i/p9hcq1J)
>例题
[![p9hgu4S.md.png](https://s1.ax1x.com/2023/05/19/p9hgu4S.md.png)](https://imgse.com/i/p9hgu4S)\
{{< expand "学霸肯定对了">}}答案：A\
&emsp;&emsp;解析：补零：原始信息串为1100，生成多项式为3阶，则补3个0，即被除数为：1100000，除数也是根据生成多项式来的，幂指数存在的为1，不存在的为0，即1011(题目已经给出了，未给出的时候要知道是这样算的)，异或相除将余数010(不足3位的在左边补0)添加到原始信息串1100后面得到1100010，即选A
{{< /expand >}}

### 7.3 海明码
[![p9hg8un.md.png](https://s1.ax1x.com/2023/05/19/p9hg8un.md.png)](https://imgse.com/i/p9hg8un)
[![p9hgGBq.md.png](https://s1.ax1x.com/2023/05/19/p9hgGBq.md.png)](https://imgse.com/i/p9hgGBq)
>例题
[![p9hgU4U.md.png](https://s1.ax1x.com/2023/05/19/p9hgU4U.md.png)](https://imgse.com/i/p9hgU4U)\
{{< expand "学霸肯定对了">}}答案：D B\
&emsp;&emsp;解析：32 16 8 4 2 1 需要6位。读题目可知D5是第10位，用8+2校验，故选B
{{< /expand >}}
## 8 嵌入式
&emsp;&emsp;**DSP**：也称数字信号处理器，是一种特别适合于进行数字信号处理运算的微处理器，其主要应用是实时快速地实现各种数字信号处理算法。\
&emsp;&emsp;**SOC**：System on Chip，简称SoC，也即片上系统。从狭义角度讲，它是信息系统核心的芯片集成是将系统关键部件集成在一块芯片上，从广义角度讲，SoC是一个微小型系统，如果说中央处理器 (CPU) 是大脑，那么SoC就是包括大脑、心脏、眼睛和手的系统。\
&emsp;&emsp;**MPU**：微机中的中央处理器 (CPU)称为微处理器 (MPU)，是构成微机的核心部件，也可以说是微机的心脏。它起到控制整个微型计算机工作的作用，产生控制信号对相应的部件进行控制.并执行相应的操作。\
&emsp;&emsp;**MCU**：微控制单元 (Microcontroller Unit;MCU)，又称单片微型计算机(Single ChipMicrocomputer) 或者单片机，是把中央处理器(Central Process Unit;CPU) 的频率与规(Timer) 、USB、A/D转换、UART、PLC格做适当缩减，并将内存(memory) 、计数器DMA等周边接口，甚至LCD驱动电路都整合在单一芯片上，形成芯片级的计算机，为不同的应用场合做不同组合控制。
>例题
[![p9Ten76.md.png](https://s1.ax1x.com/2023/05/23/p9Ten76.md.png)](https://imgse.com/i/p9Ten76)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
&emsp;&emsp;嵌入式系统的初始化过程：片级初始化->版级初始化->系统初始化

## 章节习题

[![p9zGrQO.md.png](https://s1.ax1x.com/2023/06/01/p9zGrQO.md.png)](https://imgse.com/i/p9zGrQO)
[![p9zGsyD.md.png](https://s1.ax1x.com/2023/06/01/p9zGsyD.md.png)](https://imgse.com/i/p9zGsyD)
[![p9zGIl8.md.png](https://s1.ax1x.com/2023/06/01/p9zGIl8.md.png)](https://imgse.com/i/p9zGIl8)
[![p9zGIl8.md.png](https://s1.ax1x.com/2023/06/01/p9zGIl8.md.png)](https://imgse.com/i/p9zGIl8)
[![p9zJpXF.png](https://s1.ax1x.com/2023/06/01/p9zJpXF.png)](https://imgse.com/i/p9zJpXF)
[![p9zJEfx.png](https://s1.ax1x.com/2023/06/01/p9zJEfx.png)](https://imgse.com/i/p9zJEfx)
[![p9zJ8ht.md.png](https://s1.ax1x.com/2023/06/01/p9zJ8ht.md.png)](https://imgse.com/i/p9zJ8ht)
[![p9zJdBQ.md.png](https://s1.ax1x.com/2023/06/01/p9zJdBQ.md.png)](https://imgse.com/i/p9zJdBQ)
[![p9zJRuF.png](https://s1.ax1x.com/2023/06/01/p9zJRuF.png)](https://imgse.com/i/p9zJRuF)
### 第10题
[![p9zJvEd.md.png](https://s1.ax1x.com/2023/06/01/p9zJvEd.md.png)](https://imgse.com/i/p9zJvEd)
//todo 嵌入式的题目


### 前沿题
[![p9zJz4I.md.png](https://s1.ax1x.com/2023/06/01/p9zJz4I.md.png)](https://imgse.com/i/p9zJz4I)
[![p9zYCgf.md.png](https://s1.ax1x.com/2023/06/01/p9zYCgf.md.png)](https://imgse.com/i/p9zYCgf)
[![p9zYMvT.md.png](https://s1.ax1x.com/2023/06/01/p9zYMvT.md.png)](https://imgse.com/i/p9zYMvT)



