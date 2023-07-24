# 系统设计

## 1 界面设计

---

- 界面设计的三个原则
  - 置于用户控制之下
  - 减少用户的记忆负担
  - 保持界面的一致性

&emsp;&emsp;系统输入设计应该属于界面设计的一种。人的因素在系统输入设计中扮演了很重要的角色。输入应该尽可能地简单，以降低错误发生的可能性，如对于范围可控的数据，使用选择的方式替代用户输入，只输入变化的数据等。输入应该尽可能使用已有含义明确的设计，需要采用模仿的方式而非创新。为了避免用户理解的二义性，应该对表格中输入的数据给出提示信息。数据类型检查确保输入了正确的数据类型，自检位用于对主关键字进行基于校验位的检查；城检查用于验证数据是否位于合法的取值范围；格式检查按照已知的数据格式对照检查输入数据的格式。

>例题
[![pCUA8yt.md.png](https://s1.ax1x.com/2023/06/26/pCUA8yt.md.png)](https://imgse.com/i/pCUA8yt)
{{< expand "学霸肯定对了">}}A{{< /expand >}}

## 2 软件设计

---
  
&emsp;&emsp;体系结构设计就是架构设计，软件设计包含4个方面：接口架构过程数据。

[![pCUEKBV.md.png](https://s1.ax1x.com/2023/06/26/pCUEKBV.md.png)](https://imgse.com/i/pCUEKBV)

>例题
[![pCU3J8P.md.png](https://s1.ax1x.com/2023/06/26/pCU3J8P.md.png)](https://imgse.com/i/pCU3J8P)
{{< expand "学霸肯定对了">}}B A D{{< /expand >}}

### 2.1 结构化设计 SD

&emsp;&emsp;外部和内部、高内聚和低耦合的角度都是模块(模块是指执行某一特定任务的数据结构和程序代码；每个模块完成相对独立的特定子功能，与其他模块之间的关系最简单；)，符合自顶向下的原则。扇入：别人调自己，扇出：自己调别人。

- 概要设计(外部设计)
  
&emsp;&emsp;外部设计(高层设计/总体设计)处于软件设计的开始阶段，主要是将软件需求转化为**数据结构**和**软件的系统结构**，设计出各个功能部分的功能和接口，确定系统功能模块及其相互关系，主要采用**模块结构图**、**层次图**、**HIPO图**描述程序的结构。

- 详细设计(内部设计)

&emsp;&emsp;内部设计(底层设计)处于软件工程中的详细设计阶段，按照外部设计中确立的系统软件结构，来细化此系统各个功能部件以及各个部件接口的设计，并且详细给出各个功能部件详细的数据结构与算法。

[![pCU3dbQ.md.png](https://s1.ax1x.com/2023/06/26/pCU3dbQ.md.png)](https://imgse.com/i/pCU3dbQ)

&emsp;&emsp;需要知道内聚和耦合的两个极端。最高内聚为：功能内聚；最低内聚为：偶然内聚。最高耦合：内容/内部耦合；最低耦合：非直接耦合和数据耦合。

[![pCU3Oqe.md.png](https://s1.ax1x.com/2023/06/26/pCU3Oqe.md.png)](https://imgse.com/i/pCU3Oqe)

### 2.2 面向对象设计 OOD

&emsp;&emsp;面向对象设计OOD的基本任务是把面向对象分析模型(**顶层架构图、用例与用例图、领域概念模型构成**)转换为面向对象设计模型(以**包图表示的软件体系结构图**、以**交互图表示的用例实现图**，**完整精确的类图**，**针对复杂对象的状态图和用以描述流程化处理的活动图**等)。

[![pCU8tiR.md.png](https://s1.ax1x.com/2023/06/26/pCU8tiR.md.png)](https://imgse.com/i/pCU8tiR)

- 面向对象的设计原则如下：

&emsp;&emsp;对于违反里氏替换原则的两个类A和B，可以采用：尽量将一些需要扩展的类或者存在变化的类设计为抽象类或者接口，并将其作为基类，在程序中尽量使用基类对象进行编程。

&emsp;&emsp;信息隐蔽是开发整体程序结构时使用的法则，即将每个程序的成分隐蔽或封装在一个单的设计模块中，并且尽可能少地暴露其内部的处理过程。通过信息隐蔽可以提高软件的**可修改性、可测试性和可移植性**，它也是现代软件设计的一个关键性原则。

[![pCU8OS0.md.png](https://s1.ax1x.com/2023/06/26/pCU8OS0.md.png)](https://imgse.com/i/pCU8OS0)

>例题
[![pCU8jyT.md.png](https://s1.ax1x.com/2023/06/26/pCU8jyT.md.png)](https://imgse.com/i/pCU8jyT)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

- 设计模式

&emsp;&emsp;[设计模式-github代码](https://github.com/yswang837/golang-design-pattern)

&emsp;&emsp;设计模式属于OOD里面的内容，详情见 3 设计模式

### 2.3 软件架构设计

&emsp;&emsp;见“软件架构设计“章节。

## 3 23种设计模式

---

&emsp;&emsp;设计模式属于面向对象设计里面的一个点，设计模式放大一层就是架构风格。

&emsp;&emsp;学习设计模式需要关注的点：

&emsp;&emsp;1、模式的三种类型的定位

&emsp;&emsp;2、设计模式的分类

&emsp;&emsp;3、设计模式应用场景(能解决什么样的问题)及特点

### 3.1 模式的种类

[![pCUGSw4.md.png](https://s1.ax1x.com/2023/06/26/pCUGSw4.md.png)](https://imgse.com/i/pCUGSw4)

>例题
[![pCUGif1.md.png](https://s1.ax1x.com/2023/06/26/pCUGif1.md.png)](https://imgse.com/i/pCUGif1)
{{< expand "学霸肯定对了">}}A B B{{< /expand >}}

### 3.2 设计模式的分类

- 创建型模式：用于创建对象，为设计类实例化新对象提供指南。
- 结构型模式：用于处理类或对象的组合，对类如何设计以形成更大的结构提供指南。
- 行为型模式：用于描述类或对象的交互以及职责的分配，对类之间交互以及分配责任的方式提供指南。
  
&emsp;&emsp;也可分为：类模式（类似于类的静态方法，不用初始化对象，直接通过类名来调用）和对象模式。

[![pCUGMtA.md.png](https://s1.ax1x.com/2023/06/26/pCUGMtA.md.png)](https://imgse.com/i/pCUGMtA)

### 3.3 创建型模式

[![pCUJ9u8.md.png](https://s1.ax1x.com/2023/06/26/pCUJ9u8.md.png)](https://imgse.com/i/pCUJ9u8)

#### 1) 工厂方法模式(Factory Method)

[![pCaZIM9.md.png](https://s1.ax1x.com/2023/06/27/pCaZIM9.md.png)](https://imgse.com/i/pCaZIM9)

#### 2) 抽象工厂模式(Abstract Factory)

&emsp;&emsp;创建一系列相关的对象。

[![pCaZorR.md.png](https://s1.ax1x.com/2023/06/27/pCaZorR.md.png)](https://imgse.com/i/pCaZorR)

#### 3) 构建器模式(Builder)

&emsp;&emsp;创建复杂对象。

[![pCaZOPO.md.png](https://s1.ax1x.com/2023/06/27/pCaZOPO.md.png)](https://imgse.com/i/pCaZOPO)

#### 4) 原型模式(Prototype)

&emsp;&emsp;允许对象在不了解要创建对象的确切类以及如何创建等细节的情况下创建自定义对象。如对象的直接克隆。

#### 5) 单例模式(Singleton)

&emsp;&emsp;确保一个类只有一个实例。例如数据库的连接。

### 3.4 结构型模式

[![pCaeVzQ.md.png](https://s1.ax1x.com/2023/06/27/pCaeVzQ.md.png)](https://imgse.com/i/pCaeVzQ)

#### 6) 适配器模式(Adapter)

[![pCaeeMj.md.png](https://s1.ax1x.com/2023/06/27/pCaeeMj.md.png)](https://imgse.com/i/pCaeeMj)

#### 7) 桥接模式(Bridge)

&emsp;&emsp;将类的抽象部分和它的实现部分分离开来，使它们可以独立变化。跟docker网络的桥接模式不一样。

[![pCaenLn.md.png](https://s1.ax1x.com/2023/06/27/pCaenLn.md.png)](https://imgse.com/i/pCaenLn)

#### 8) 组合模式(Composite)

[![pCaeQoV.md.png](https://s1.ax1x.com/2023/06/27/pCaeQoV.md.png)](https://imgse.com/i/pCaeQoV)

#### 9) 代理模式(Proxy)

&emsp;&emsp;应用程序的快捷方式。房东房子很多，需要卖房的时候，他把房子全权代理给房屋代理机构，让该机构负责，它可决定介绍哪些买家给买家。注意跟中介模式、适配器模式区分。

[![pCaety9.md.png](https://s1.ax1x.com/2023/06/27/pCaety9.md.png)](https://imgse.com/i/pCaety9)

#### 10) 装饰模式(Decorator)

&emsp;&emsp;动态的附加、补充、扩展一些简单的职能，比静态继承具有更大的灵活性。原始的咖啡加糖，加冰等等。

#### 11) 外观模式(Facade)

&emsp;&emsp;子系统的一组接口对外提供一个统一的接口。比如说：一键开会(拉下幕布，打开投影仪，灯光降低，关闭窗帘)，一键开会这个接口使得子系统更易使用。

#### 12) 享元模式(Flyweight)

&emsp;&emsp;汉字编码。常用汉字也就几千字，如果在word中有几十万字，那么大多数都是重复的常用汉字，那么这些常用汉字可以共享空间。

### 3.5 行为型模式

[![pCamC6J.md.png](https://s1.ax1x.com/2023/06/27/pCamC6J.md.png)](https://imgse.com/i/pCamC6J)
[![pCanZbn.md.png](https://s1.ax1x.com/2023/06/27/pCanZbn.md.png)](https://imgse.com/i/pCanZbn)

#### 13) 中介模式(Mediator)

&emsp;&emsp;解决买房和卖房信息不对称的矛盾，两个对象之间的两两交互过于麻烦，中介可以屏蔽双方的差异，简化流程。比如银联、央行。

[![pCamU1g.md.png](https://s1.ax1x.com/2023/06/27/pCamU1g.md.png)](https://imgse.com/i/pCamU1g)

#### 14) 职责链模式(Chain of Responsibility)

&emsp;&emsp;提交的请假如果本层解决不了，则层层网上传递(有一定顺序)，这就形成一个职责链(看做是踢皮球就好理解了)。

[![pCamg9U.md.png](https://s1.ax1x.com/2023/06/27/pCamg9U.md.png)](https://imgse.com/i/pCamg9U)

#### 15) 命令模式(Command)

&emsp;&emsp;日志记录，**可撤销**。将命令封装在对象里面，如word的各种撤销(及时性的东西)等等。

#### 16) 解释器模式(Interpreter)

&emsp;&emsp;如架构风格里面的虚拟机风格。可为特定的、自定义的场景做出解释，如迷宫。

#### 17) 迭代器模式(Iterator)

&emsp;&emsp;若高级语言里面的可迭代对象。数据的某些迭代操作。

#### 18) 备忘录模式(Memento)

&emsp;&emsp;快照。可以在不向外界公开具体细节的时候恢复到最初的状态，游戏存档，git版本存档。命令模式是撤销一些及时性的东西。

#### 19) 观察者模式(Observer)

&emsp;&emsp;订阅、广播、联动。在Execl中，A1=10,A2=20,A3=A1+A2，当A1或A2变化时A3也会随之变化。

#### 20) 状态模式(State)

&emsp;&emsp;将状态变成类，可以很好地管理状态之间的变迁。不同的状态对应不同的复杂的行为和属性。订酒店：房间有空闲状态，入住状态，待清洁状态等等。会员的升级等。

#### 21) 策略模式(Strategy)

&emsp;&emsp;多方案、多策略的切换。随着场景变化而变化。如商场打折。

[![pCanw8O.md.png](https://s1.ax1x.com/2023/06/27/pCanw8O.md.png)](https://imgse.com/i/pCanw8O)

#### 22) 模板方法模式(Template Method)

&emsp;&emsp;PPT模板、简历模板等。如软件开发里面的框架。

#### 23) 访问者模式(Visitor)

&emsp;&emsp;数据与操作分离，将变的和不变的分离开来。因为操作老是会变，而数据基本不变。

>例题
[![pCanyqA.md.png](https://s1.ax1x.com/2023/06/27/pCanyqA.md.png)](https://imgse.com/i/pCanyqA)
{{< expand "学霸肯定对了">}}A D C B{{< /expand >}}
>案例分析例题
[![pC6MdH0.md.png](https://s1.ax1x.com/2023/07/06/pC6MdH0.md.png)](https://imgse.com/i/pC6MdH0)
[![pC45701.md.png](https://s1.ax1x.com/2023/07/14/pC45701.md.png)](https://imgse.com/i/pC45701)
{{< expand "学霸肯定对了">}}
[![pC6MhE6.md.png](https://s1.ax1x.com/2023/07/06/pC6MhE6.md.png)](https://imgse.com/i/pC6MhE6)
{{< /expand >}}
