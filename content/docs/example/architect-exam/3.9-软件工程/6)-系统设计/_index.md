# 系统设计

## 1 界面设计

---

[![pCUAeeK.md.png](https://s1.ax1x.com/2023/06/26/pCUAeeK.md.png)](https://imgse.com/i/pCUAeeK)

>例题
[![pCUA8yt.md.png](https://s1.ax1x.com/2023/06/26/pCUA8yt.md.png)](https://imgse.com/i/pCUA8yt)
{{< expand "学霸肯定对了">}}A{{< /expand >}}

## 2 软件设计

---

&emsp;&emsp;体系结构设计就是架构设计。

[![pCUEKBV.md.png](https://s1.ax1x.com/2023/06/26/pCUEKBV.md.png)](https://imgse.com/i/pCUEKBV)

>例题
[![pCU3J8P.md.png](https://s1.ax1x.com/2023/06/26/pCU3J8P.md.png)](https://imgse.com/i/pCU3J8P)
{{< expand "学霸肯定对了">}}B A D{{< /expand >}}

### 6.2.1 结构化设计

&emsp;&emsp;外部和内部、高内聚和低耦合的角度都是模块，符合自顶向下的原则。扇入：别人调自己，扇出：自己调别人。

[![pCU3dbQ.md.png](https://s1.ax1x.com/2023/06/26/pCU3dbQ.md.png)](https://imgse.com/i/pCU3dbQ)

[![pCU3Oqe.md.png](https://s1.ax1x.com/2023/06/26/pCU3Oqe.md.png)](https://imgse.com/i/pCU3Oqe)

### 6.2.2 面向对象设计

&emsp;&emsp;面向对象设计的上一步是面向对象分析OOA；它所包含的总体任务如下：

[![pCU8tiR.md.png](https://s1.ax1x.com/2023/06/26/pCU8tiR.md.png)](https://imgse.com/i/pCU8tiR)

- 面向对象的设计原则如下：

[![pCU8OS0.md.png](https://s1.ax1x.com/2023/06/26/pCU8OS0.md.png)](https://imgse.com/i/pCU8OS0)

>例题
[![pCU8jyT.md.png](https://s1.ax1x.com/2023/06/26/pCU8jyT.md.png)](https://imgse.com/i/pCU8jyT)
{{< expand "学霸肯定对了">}}C{{< /expand >}}

- 设计模式

&emsp;&emsp;[设计模式-github代码](https://github.com/yswang837/golang-design-pattern)

&emsp;&emsp;设计模式属于面向对象设计里面的一个点，详情见 6.3 设计模式

## 6.3 设计模式

---

&emsp;&emsp;学习设计模式需要关注的点：

&emsp;&emsp;1、设计模式三种类型的定位

&emsp;&emsp;2、设计模式的分类

&emsp;&emsp;3、设计模式应用场景及特点

- 设计模式的三种类型

[![pCUGSw4.md.png](https://s1.ax1x.com/2023/06/26/pCUGSw4.md.png)](https://imgse.com/i/pCUGSw4)

>例题
[![pCUGif1.md.png](https://s1.ax1x.com/2023/06/26/pCUGif1.md.png)](https://imgse.com/i/pCUGif1)
{{< expand "学霸肯定对了">}}A B B{{< /expand >}}

- 设计模式的分类
  - 创建型模式：创建对象(目标)
  - 结构型模式：更大的结构(目标)
  - 行为型模式：交互及指责分配(目标)
  
&emsp;&emsp;类模式（类似于类的静态方法，不用初始化对象，直接通过类名来调用）

[![pCUGMtA.md.png](https://s1.ax1x.com/2023/06/26/pCUGMtA.md.png)](https://imgse.com/i/pCUGMtA)

### 6.3.1 创建型模式

[![pCUJ9u8.md.png](https://s1.ax1x.com/2023/06/26/pCUJ9u8.md.png)](https://imgse.com/i/pCUJ9u8)

- 工厂方法模式

[![pCaZIM9.md.png](https://s1.ax1x.com/2023/06/27/pCaZIM9.md.png)](https://imgse.com/i/pCaZIM9)

- 抽象工厂模式

[![pCaZorR.md.png](https://s1.ax1x.com/2023/06/27/pCaZorR.md.png)](https://imgse.com/i/pCaZorR)

- 构建器模式

[![pCaZOPO.md.png](https://s1.ax1x.com/2023/06/27/pCaZOPO.md.png)](https://imgse.com/i/pCaZOPO)

- 原型模式

&emsp;&emsp;对象的直接克隆。

- 单例模式

&emsp;&emsp;例如数据库的连接。

### 6.3.2 结构型模式

[![pCaeVzQ.md.png](https://s1.ax1x.com/2023/06/27/pCaeVzQ.md.png)](https://imgse.com/i/pCaeVzQ)

- 适配器模式

[![pCaeeMj.md.png](https://s1.ax1x.com/2023/06/27/pCaeeMj.md.png)](https://imgse.com/i/pCaeeMj)

- 桥接模式

[![pCaenLn.md.png](https://s1.ax1x.com/2023/06/27/pCaenLn.md.png)](https://imgse.com/i/pCaenLn)

- 组合模式

[![pCaeQoV.md.png](https://s1.ax1x.com/2023/06/27/pCaeQoV.md.png)](https://imgse.com/i/pCaeQoV)

- 代理模式

&emsp;&emsp;应用程序的快捷方式。房东房子很多，需要卖房的时候，他把房子全权代理给房屋代理机构，让该机构负责。注意跟中介模式、适配器模式区分。

[![pCaety9.md.png](https://s1.ax1x.com/2023/06/27/pCaety9.md.png)](https://imgse.com/i/pCaety9)

- 装饰模式

&emsp;&emsp;动态的附加一些简单的职能。原始的咖啡加糖，加冰等等。

- 外观模式

&emsp;&emsp;子系统的一组接口对外提供一个统一的接口。比如说：一键开会(拉下幕布，打开投影仪，灯光降低，关闭窗帘)。

- 享元模式

&emsp;&emsp;汉字编码。常用汉字也就几千字，如果在word中有几十万字，那么大多数都是重复的常用汉字，那么这些常用汉字可以共享空间。

### 6.3.3 行为型模式

[![pCamC6J.md.png](https://s1.ax1x.com/2023/06/27/pCamC6J.md.png)](https://imgse.com/i/pCamC6J)
[![pCanZbn.md.png](https://s1.ax1x.com/2023/06/27/pCanZbn.md.png)](https://imgse.com/i/pCanZbn)

- 中介模式

&emsp;&emsp;解决买房和卖房信息不对称的矛盾，两个对象之间的两两交互过于麻烦，简化流程。比如银联、央行。

[![pCamU1g.md.png](https://s1.ax1x.com/2023/06/27/pCamU1g.md.png)](https://imgse.com/i/pCamU1g)

- 职责链模式

&emsp;&emsp;提交的请假如果本层解决不了，则层层网上传递，这就形成一个职责链。跟某些部门踢皮球一样。

[![pCamg9U.md.png](https://s1.ax1x.com/2023/06/27/pCamg9U.md.png)](https://imgse.com/i/pCamg9U)

- 命令模式

&emsp;&emsp;日志记录，可撤销。将命令封装在对象里面，如word的各种撤销(及时性的东西)等等。

- 解释器模式

&emsp;&emsp;如架构风格里面的虚拟机风格。可为特定的、自定义的场景做出解释，如迷宫。

- 迭代器模式

&emsp;&emsp;若高级语言里面的可迭代对象。数据集的某些迭代操作。

- 备忘录模式

&emsp;&emsp;快照。可以在不向外界公开具体细节的时候恢复到最初的状态，游戏存档，git版本存档。命令模式是撤销一些及时性的东西。

- 观察者模式

&emsp;&emsp;订阅、广播、联动。在Execl中，A1=10,A2=20,A3=A1+A2，当A1或A2变化时A3也会随之变化。

- 状态模式

&emsp;&emsp;将状态变成类，可以很好地管理状态之间的变迁。不同的状态对应不同的行为和属性。订酒店：房间有空闲状态，入住状态，待清洁状态等等。会员的升级等。

- 策略模式

&emsp;&emsp;多方案、多策略的切换。如商场打折。

[![pCanw8O.md.png](https://s1.ax1x.com/2023/06/27/pCanw8O.md.png)](https://imgse.com/i/pCanw8O)

- 模板方法模式

&emsp;&emsp;PPT模板、简历模板等。如软件开发里面的框架。

- 访问者模式

&emsp;&emsp;数据与操作分离。因为操作老是会变，而数据基本不变。将变的和不变的分离开来。

>例题
[![pCanyqA.md.png](https://s1.ax1x.com/2023/06/27/pCanyqA.md.png)](https://imgse.com/i/pCanyqA)
{{< expand "学霸肯定对了">}}A D C B{{< /expand >}}
