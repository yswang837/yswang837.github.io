# 软件测试与调试

## 1 软件测试方法

---

- 测试的原则
  - 尽早、不断的进行测试
  - 程序员避免测试自己设计的程序
  - 既要选择有效、合理的数据，也要选择无效、不合理的数据
  - 修改后应进行回归测试
  - 尚未发现的错误数量与该程序已发现错误数成正比

### 1.1 测试类型的划分

[![pCaGbdg.md.png](https://s1.ax1x.com/2023/06/27/pCaGbdg.md.png)](https://imgse.com/i/pCaGbdg)

- 动态测试

&emsp;&emsp;等价类划分：各个阶段的测试用例各选一个，如1-1000分为普卡用户，1001-3000为金卡用户，大于等于3001为砖石卡。无效等价类也需要给测试用例。

&emsp;&emsp;边界值分析通过选择等价类边界作为测试用例，不仅重视输入条件边界，而且也必须考虑输出域边界。

&emsp;&emsp;因果图方法是从用自然语言书写的程序规格说明的摧述中找出因 (输入条件)和果 (输出或程序状态的改变)，可以通过因果图转换为判定表。

&emsp;&emsp;正交试验设计法，就是使用已经造好了的正交表格来安排试验并进行数据分析的一种方法，目的是用最少的测试用例达到最高的测试覆盖率。

&emsp;&emsp;白盒测试就是根据程序内部结构和内部逻辑，测试其功能是否正确。

&emsp;&emsp;语句覆盖要求设计足够多的测试用例，使程序中每多语句至少被执行一次。

&emsp;&emsp;判定/条件覆盖准则的缺点是未考虑条件的组合情况。

&emsp;&emsp;与判定覆盖相比，条件覆盖增加对符合判定情况的测试，增加了测试路径。

[![pCaJpLT.md.png](https://s1.ax1x.com/2023/06/27/pCaJpLT.md.png)](https://imgse.com/i/pCaJpLT)

>例题
[![pCaGvzq.md.png](https://s1.ax1x.com/2023/06/27/pCaGvzq.md.png)](https://imgse.com/i/pCaGvzq)
{{< expand "学霸肯定对了">}}A C{{< /expand >}}

### 1.2 结构化测试阶段

[![pCaJt6P.md.png](https://s1.ax1x.com/2023/06/27/pCaJt6P.md.png)](https://imgse.com/i/pCaJt6P)

- 单元测试

&emsp;&emsp;驱动模块用来调用被测模块，自顶向下的单元测试中不需要另外编写驱动模块。

&emsp;&emsp;桩模块用来模拟被测模块所调用的子模块，自顶向下的单元测试中需要另外编写桩模块。

&emsp;&emsp;驱动模块用来模拟被测模块所调用的子模块，自底向上的单元测试中需要另外编写驱动模块。

- 集成测试

&emsp;&emsp;程序模块单元测试通过后进行的集成测试，主要测试各模块之间的接口是否正常起作用。

[![pCaJypn.md.png](https://s1.ax1x.com/2023/06/27/pCaJypn.md.png)](https://imgse.com/i/pCaJypn)

- 系统测试

&emsp;&emsp;对计算机进行负载测试就是运行某种诊断程序，加大负载，检查哪个设备会发生故障。

[![pCaJ6lq.md.png](https://s1.ax1x.com/2023/06/27/pCaJ6lq.md.png)](https://imgse.com/i/pCaJ6lq)

>例题
[![pCaJ4k4.md.png](https://s1.ax1x.com/2023/06/27/pCaJ4k4.md.png)](https://imgse.com/i/pCaJ4k4)
{{< expand "学霸肯定对了">}}A{{< /expand >}}
[![pCaJO0O.md.png](https://s1.ax1x.com/2023/06/27/pCaJO0O.md.png)](https://imgse.com/i/pCaJO0O)
{{< expand "学霸肯定对了">}}A D{{< /expand >}}

### 1.3 面向对象测试

&emsp;&emsp;和结构化测试基本上一一对应，但它只需要了解每个层大概有什么测试方法就行，不用掌握每一种方法。

[![pCaYp9A.md.png](https://s1.ax1x.com/2023/06/27/pCaYp9A.md.png)](https://imgse.com/i/pCaYp9A)

## 2 软件调试

---

### 2.1 软件调试方法

&emsp;&emsp;原因排除法：正向找错，回溯法：反向找错。

[![pCaYCct.md.png](https://s1.ax1x.com/2023/06/27/pCaYCct.md.png)](https://imgse.com/i/pCaYCct)

### 2.2 调试和测试的区别

[![pCaYkB8.md.png](https://s1.ax1x.com/2023/06/27/pCaYkB8.md.png)](https://imgse.com/i/pCaYkB8)
