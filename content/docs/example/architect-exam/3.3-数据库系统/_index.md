---
weight: 3
title: 3.3 数据库系统
---

## 课程内容提要
- 1. 数据库模式✅
- 2. 分布式数据库✅✅✅
  - 分布式数据库的特点
  - 分布式数据库的层次
  - 分布透明性
  - 分布式数据库的两阶段提交协议
- 3. 数据库设计阶段✅✅
  - 需求分析✅
  - 概念结构设计-ER模型✅
  - 逻辑结构设计-关系模型✅✅
  - 物理设计✅
- 4. 关系代数✅✅✅✅
- 5. 规范化理论✅✅✅✅✅
  - 函数依赖
  - 求候选键
  - Armstrong公理
  - 范式判断
- 8. 并发控制✅
- 9. 数据库的安全性✅
- 10. 数据库的备份与恢复技术✅
- 11. 数据库性能优化✅
- 12. 专项练习

### 在讲义56、296页

## 1 数据库模式
数据库的三级模式两级映像可以保证数据的逻辑独立性和物理独立性。
[![pCEowtI.md.png](https://s1.ax1x.com/2023/06/10/pCEowtI.md.png)](https://imgse.com/i/pCEowtI)
- 关系的3种类型\
**基本关系** (通常又称为基本表或基表) : 实际存在的表，实际存储数据的逻辑表示。
**查询表**:查询结果对应的表。
**视图表**:由基表或其他视图表导出的表，本身不独立存储，数据库只存放它的定义，常称为虚表。

- 视图表\
**数据库视图**:它一个虚拟表 (逻辑上的表)，其内容由查询定义(仅保存SOL查询语句)同真实的表一样，视图包含一系列带有名称的列和行数据。但是，视图并没有真正存储这些数据，而是通过查询原始表动态生成所需要的数据。\
**视图的优点**:\
&emsp;&emsp;1、视图能简化用户操作\
&emsp;&emsp;2、视图使用户能以多种角度看待同一数据\
&emsp;&emsp;3、视图对重构数据库提供了一定程度的逻辑独立性\
&emsp;&emsp;4、视图可以对机密数据提供安全保护\
**物化视图**:它不是传统意义上虚拟视图，是实体化视图，其本身会存储数据。同时当原始表中的数据更新时，物化视图也会更新。适合于多查询少更新的场景。

## 2 分布式数据库
&emsp;&emsp;分布式数据对应于集中式数据库而言的，平时所用到的SQL Server等都是集中式数据库，分布式会考虑物理上把数据放在不同的物理节点上。
### 2.1 分布式数据库的特点
- 1) 数据独立性\
&emsp;&emsp;除了数据的逻辑独立性与物理独立性外，还有数据**分布独立性** (**分布透明性**)。

- 2) 集中与自治共享结合的控制结构\
&emsp;&emsp;各局部的DBMS可以独立地管理局部数据库，具有自治的功能。同时，系统又设有集中控制机制，协调各局部DBMS的工作，执行全局应用。

- 3) 适当增加数据冗余度\
&emsp;&emsp;在不同的场地存储同一数据的多个副本可以提高系统的可靠性和可用性，同时也能提高系统性能。提高系统的**可用性**，即当系统中某个节点发生故障时，因为数据有其他副本在非故障场地上，对其他所有场地来说，数据仍然是可用的，从而保证数据的完备性。

- 4) 全局的一致性、可串行性和可恢复性\
&emsp;&emsp;该点和集中式数据库的特点一致。

### 2.2 分布式数据库的层次
&emsp;&emsp;分布式数据库的层次和数据库的三级模式两级映像大致相似，只不过在原有的“外模式”、“概念模式”、“内模式”上增加了一些具体的特性，如分片模式有(垂直分片、水平分片、混合分片)，分布模式(表示具体放在哪个物理节点)，分布式数据库的全局外模式和集中式数据库的外模式一样，都直接用于用户程序，分布式数据库的局部概念模式和集中式数据库的概念模式一样，都是库表，局部内模式同集中式数据库的内模式一样，其具体情况如下图：
[![pCETwb4.md.png](https://s1.ax1x.com/2023/06/10/pCETwb4.md.png)](https://imgse.com/i/pCETwb4)\
&emsp;&emsp;分布式数据库管理系统(DDBMS, Distributed Database Management System)由局部数据库管理系统(LDBMS, Local Database Management System)、全局数据库管理系统(GDBMS, Global Database Management System)、数据字典和通信管理(CM, Communication Management)组成。
&emsp;&emsp;分布式数据库管理系统的结构有：(1)全局控制集中的DDBMS (2)全局控制分散的DDBMS (3)全局控制部分分散的DDBMS。

### 2.3 分布透明性
&emsp;&emsp;分布透明性分为：分片透明性、复制透明性、位置透明性、局部数据模型透明性；其中分片透明性又分为：水平分片、垂直分片、混合分片。
- 1) 分片透明：\
&emsp;&emsp;是指用户不必关心数据是如何分片的，它们对数据的操作在全局关系上进行，即如何分片对用户是透明的。
- 2) 复制透明：\
&emsp;&emsp;用户不用关心数据库在网络中各个节点的复制情况，被复制的数据的更新都由系统自动完成。
- 3) 位置透明：\
&emsp;&emsp;是指用户不必知道所操作的数据放在何处，即数据分配到哪个或哪些站点存储对用户是透明的。
- 4) 局部映像透明性(逻辑透明)：\
&emsp;&emsp;是最低层次的透明性，该透明性提供数据到局部数据库的映像，即用户不必关心局部DBMS支持哪种数据模型使用哪种数据操纵语言，数据模型和操纵语言的转换是由系统完成的。因此，局部映像透明性对异构型和同构异质的分布式数据库系统是非常重要的。
### 2.4 分布式数据库的两阶段提交协议
&emsp;&emsp;1、表决阶段：目的是形成一个共同的决定。\
&emsp;&emsp;2、执行阶段：目的是实现这个协调者的决定。
- 两条全局提交规则\
&emsp;&emsp;1、只要有一个参与者撤销事务，协调者就必须做出全局撤销决定。\
&emsp;&emsp;2、只有所有参与者都同意提交事务，协调者才能做出全局提交决定。
例题>
[![pCEHMkj.md.png](https://s1.ax1x.com/2023/06/10/pCEHMkj.md.png)](https://imgse.com/i/pCEHMkj)
{{< expand "学霸肯定对了">}}D{{< /expand >}}
[![pCEHQts.md.png](https://s1.ax1x.com/2023/06/10/pCEHQts.md.png)](https://imgse.com/i/pCEHQts)
{{< expand "学霸肯定对了">}}D{{< /expand >}}
[![pCEH3pq.md.png](https://s1.ax1x.com/2023/06/10/pCEH3pq.md.png)](https://imgse.com/i/pCEH3pq)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

## 3 数据库设计阶段
&emsp;&emsp;数据库设计包含需求分析->概念结构设计->逻辑结构设计->物理设计阶段，每阶段的产物需要知道。\
[![pCVdeYR.md.png](https://s1.ax1x.com/2023/06/11/pCVdeYR.md.png)](https://imgse.com/i/pCVdeYR)
>例题
[![pCVdmf1.md.png](https://s1.ax1x.com/2023/06/11/pCVdmf1.md.png)](https://imgse.com/i/pCVdmf1)
{{< expand "学霸肯定对了">}}C\
需求分析产物有：数据流图、数据字典、需求说明书，概念结构设计的产物有：ER图，逻辑结构设计的产物有：关系模式，还需要考虑ER图转关系模式的转换规则和规范化相关的一些东西，物理设计考虑的是具体的物理存储、物理分布等，故选C{{< /expand >}}
[![pCVdKl6.md.png](https://s1.ax1x.com/2023/06/11/pCVdKl6.md.png)](https://imgse.com/i/pCVdKl6)
{{< expand "学霸肯定对了">}}C{{< /expand >}}
### 3.1 需求分析
&emsp;&emsp;根据当前和未来应用的数据要求、数据处理要求来进行需求分析，此阶段的产物有：数据流图、数据字典、需求说明书。
### 3.2 概念结构设计
&emsp;&emsp;概念结构设计也就是通过需求分析的结果来获得ER图的过程。下图是示例的ER图：\
[![pCVdtfI.md.png](https://s1.ax1x.com/2023/06/11/pCVdtfI.md.png)](https://imgse.com/i/pCVdtfI)\
&emsp;&emsp;ER图就是实体联系图，两个不同的实体集之间有三种联系，分别是1:1,1:m,m:n。上图是m:n的多对多关系(联系的类型需要会判断)。
- E-R图具体的建立过程
[![pCVdR10.md.png](https://s1.ax1x.com/2023/06/11/pCVdR10.md.png)](https://imgse.com/i/pCVdR10)\
**合并的方法**：多个局部E-R图一次集成。逐步集成，用累加的方式一次集成两个局部E-R。\
**合并产生的冲突及解决办法**：属性冲突:包括属性域冲突和属性取值冲突；命名冲突:包括同名异义和异名同义；结构冲突:包括同一对象在不同应用中具有不同的抽象，以及同一实体在不同局部E-R图中所包含的属性个数和属性排列次序不完全相同。
### 3.3 逻辑结构设计
&emsp;&emsp;逻辑结构设计的产物是关系模式，ER图+转换规则和规范化理论=关系模式(关系模型)。数据模型三要素：数据结构、数据操作、数据的约束条件。数据模型包括层次模型、网状模型、面向对象模型、关系模型。\
&emsp;&emsp;以下的几种形式都是关系模型。
[![pCVdHhR.md.png](https://s1.ax1x.com/2023/06/11/pCVdHhR.md.png)](https://imgse.com/i/pCVdHhR)

- 关系模型的相关概念\
&emsp;&emsp;以学生、选课关系为例，说明关系模型中的相关概念。其中：学生(学号，姓名，年龄，班级编号)和选课(学号，课程号，课程名)。\
&emsp;&emsp;1、学生关系是一个4目关系；选课关系是一个3目关系。\
&emsp;&emsp;2、学生关系的候选码只有一个，是学号；选课关系的候选码也只有一个，是(学号，课程号)。\
&emsp;&emsp;3、学生关系的主键是学号；选课关系的主键是(学号，课程号)。\
&emsp;&emsp;4、学生关系的主属性有学号，非主属性有姓名，年龄，班级编号；选课关系的主属性有学号和课程号，非主属性有课程名。\
&emsp;&emsp;5、学生关系没有外键；选课关系的外键是学号，学号是学生关系的主键。\
&emsp;&emsp;6、学生关系没有全码，选课关系也没有全码。全码(全部属性都是候选码，即选课关系去掉课程名之后，剩下的就是全码)\
[![pCVdL1x.md.png](https://s1.ax1x.com/2023/06/11/pCVdL1x.md.png)](https://imgse.com/i/pCVdL1x)

- 完整性约束
  - 实体完整性：规定基本关系的主属性不能取空值。跟主键相关
  - 参照完整性：关系与关系之间的引用。跟外键相关
  - 用户自定义完整性：应用环境决定。如年龄取值范围等。
  - 触发器：复杂的完整性约束，可做逻辑判断等功能。

>例题
[![pCVwVu8.md.png](https://s1.ax1x.com/2023/06/11/pCVwVu8.md.png)](https://imgse.com/i/pCVwVu8)
{{< expand "学霸肯定对了">}}B{{< /expand >}}

- 关系模式的具体的建立过程
[![pCVwK4s.md.png](https://s1.ax1x.com/2023/06/11/pCVwK4s.md.png)](https://imgse.com/i/pCVwK4s)
&emsp;&emsp;1、ER图向关系模式转换：实体向关系模式转换；联系向关系模式转换。\
&emsp;&emsp;2、关系模式的规范化。\
&emsp;&emsp;3、确定完整性约束(保证数据的正确性)。\
&emsp;&emsp;4、用户视图的确定(提高数据的安全性和独立性)：根据数据流图确定处理过程使用的视图；根据用户类别确定不用用户使用的使用。\
&emsp;&emsp;5、应用程序设计。

- 1. ER图向关系模式转换\
&emsp;&emsp;其余的放在后续章节介绍。
[![pCV0mM6.md.png](https://s1.ax1x.com/2023/06/11/pCV0mM6.md.png)](https://imgse.com/i/pCV0mM6)
[![pCV08JA.md.png](https://s1.ax1x.com/2023/06/11/pCV08JA.md.png)](https://imgse.com/i/pCV08JA)
>例题
[![pCV0tQP.md.png](https://s1.ax1x.com/2023/06/11/pCV0tQP.md.png)](https://imgse.com/i/pCV0tQP)
{{< expand "学霸肯定对了">}}C{{< /expand >}}
[![pCV0wdg.md.png](https://s1.ax1x.com/2023/06/11/pCV0wdg.md.png)](https://imgse.com/i/pCV0wdg)
{{< expand "学霸肯定对了">}}D C A{{< /expand >}}
### 3.4 物理设计
&emsp;&emsp;物理设计考虑具体的物理存储、物理分布情况。
## 4 关系代数
&emsp;&emsp;关系代数是针对关系模式进行的代数运算。\
&emsp;&emsp;并交差是同构的二元运算。
[![pCVBkm8.md.png](https://s1.ax1x.com/2023/06/11/pCVBkm8.md.png)](https://imgse.com/i/pCVBkm8)\
&emsp;&emsp;笛卡尔积、投影选择可是同构，也可异构；笛卡尔积是二元运算，投影、选择都是一元运算；它们都可用1，2，3...来代替列名，有同名的情况需要加上“表名.”。经常会出现这样的sql考察形式：select 投影 from 笛卡尔积 where 选择。\
[![pCVBmfs.md.png](https://s1.ax1x.com/2023/06/11/pCVBmfs.md.png)](https://imgse.com/i/pCVBmfs)\
&emsp;&emsp;连接有多种，考试基本上只考自然连接。有同名的情况需要加上“表名.”。笛卡尔积的结果非常庞大，将笛卡尔积进行适当的选择、投影(注意顺序，下面两个式子中，第一个是对的)就可以得到自然连接的结果，所以也会考察它们相等的情况。如果考虑性能情况，一般需要先投影选择之后再做笛卡尔积或自然连接的性能最高。\
[![pCVB29A.md.png](https://s1.ax1x.com/2023/06/11/pCVB29A.md.png)](https://imgse.com/i/pCVB29A)
>例题
[![pCVDQCd.md.png](https://s1.ax1x.com/2023/06/11/pCVDQCd.md.png)](https://imgse.com/i/pCVDQCd)
{{< expand "学霸肯定对了">}}D C{{< /expand >}}
[![pCVDXPH.md.png](https://s1.ax1x.com/2023/06/11/pCVDXPH.md.png)](https://imgse.com/i/pCVDXPH)
{{< expand "学霸肯定对了">}}B C{{< /expand >}}

## 5 规范化理论
- 规范的必要性\
&emsp;&emsp;非规范化的关系模式可能存在的问题包括：数据冗余、更新异常(修改操作一致性问题)、插入异常、删除异常。
[![pCVrGW9.md.png](https://s1.ax1x.com/2023/06/11/pCVrGW9.md.png)](https://imgse.com/i/pCVrGW9)\
经常考察的点：\
1、给你一个关系模式，让你看看有啥问题，做法：先看该关系模式达到第几范式，再说出对应范式的问题就行；\
2、让你修改关系模式来消除这些问题。一般来说没达到第三范式都有问题。
### 5.1 函数依赖
&emsp;&emsp;函数依赖是一个语义概念，是一个自然而然的概念。如果x能唯一决定y，则称x函数决定y，或者是y函数依赖于x，记作x->y。
- 特殊的函数依赖关系
  - 部分函数依赖
[![pCVcU9e.md.png](https://s1.ax1x.com/2023/06/11/pCVcU9e.md.png)](https://imgse.com/i/pCVcU9e)
  - 传递函数依赖
[![pCVca1H.md.png](https://s1.ax1x.com/2023/06/11/pCVca1H.md.png)](https://imgse.com/i/pCVca1H)
### 5.2 求候选键
&emsp;&emsp;候选键可以有多个，每个候选键可以由多个属性构成。知道候选键了以后，其余的情况都知道了，现在介绍如何求取候选键。\
&emsp;&emsp;1、在关系模式中，一般用R(U,F)表示，U是属性，表示节点；F是函数依赖，表示边；所以将关系模式转换为一个有向图（可选）。\
&emsp;&emsp;2、找入度为0的属性(只在箭头左边出现过的属性就是入度为0的属性；箭头指入为入度，箭头指出为出度)，并以该属性集合为起点，尝试遍历有向图，若能正常遍历图中所有结点，则该属性集即为关系模式的候选键。\
&emsp;&emsp;3、若入度为0的属性集不能遍历图中所有结点，则需要尝试性的将一些中间结点(既有入度，也有出度的结点)并入入度为0的属性集中，直至该集合能遍历所有结点，集合为候选键。
>例题
[![pCV67SH.md.png](https://s1.ax1x.com/2023/06/11/pCV67SH.md.png)](https://imgse.com/i/pCV67SH)
{{< expand "学霸肯定对了">}}A ABCD B{{< /expand >}}
### 5.3 Armstrong公理
&emsp;&emsp;函数依赖在题目中一般都给的不全，但是我们可以通过题目给的函数依赖推导出所有的属性，期间推导的依据就是Armstrong公理。
[![pCVczHx.md.png](https://s1.ax1x.com/2023/06/11/pCVczHx.md.png)](https://imgse.com/i/pCVczHx)
[![pCVgZDI.md.png](https://s1.ax1x.com/2023/06/11/pCVgZDI.md.png)](https://imgse.com/i/pCVgZDI)
>例题
[![pCVgQPS.md.png](https://s1.ax1x.com/2023/06/11/pCVgQPS.md.png)](https://imgse.com/i/pCVgQPS)
{{< expand "学霸肯定对了">}}C{{< /expand >}}
### 5.4 范式判断

