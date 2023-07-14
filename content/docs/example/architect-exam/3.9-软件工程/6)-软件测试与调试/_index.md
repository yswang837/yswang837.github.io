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

&emsp;&emsp;等价类划分：各个阶段的测试用例各选一个，如1-1000分为普卡用户，1001-3000为金卡用户，大于等于3001为砖石卡。

&emsp;&emsp;白盒测试就是根据程序内部结构和内部逻辑，测试其功能是否正确。

[![pCaJpLT.md.png](https://s1.ax1x.com/2023/06/27/pCaJpLT.md.png)](https://imgse.com/i/pCaJpLT)

>例题
[![pCaGvzq.md.png](https://s1.ax1x.com/2023/06/27/pCaGvzq.md.png)](https://imgse.com/i/pCaGvzq)
{{< expand "学霸肯定对了">}}A C{{< /expand >}}

### 1.2 结构化测试阶段

&emsp;&emsp;各种类型的计算机都具有自己的性能指标，计算机厂商当然希望自己研制的计算机有较高的性能。同样的计算机，如果采用不同的评价方法，所获得的性能指标也会不同。因此，用户希望能有一些公正的机构采用公认的评价方法来测试计算机的性能。这样的测试称为基准测试，基准测试采用的测试程序称为基准程序(Benchmark)，基准程序就是公认的标准程序，用它能测试多种计算机系统，比较和评价它们的性能，定期公布测试结果，供用户选购计算机时参考。

[![pCaJt6P.md.png](https://s1.ax1x.com/2023/06/27/pCaJt6P.md.png)](https://imgse.com/i/pCaJt6P)

- 集成测试

&emsp;&emsp;在程序模块测试后进行的集成测试，主要测试各模块之间的接口是否正常起作用。

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

&emsp;&emsp;和结构化测试基本上一一对应，只需要了解每个层大概有什么测试方法就行，不用掌握每一种方法。

[![pCaYp9A.md.png](https://s1.ax1x.com/2023/06/27/pCaYp9A.md.png)](https://imgse.com/i/pCaYp9A)

## 2 软件调试

---

### 2.1 软件调试方法

&emsp;&emsp;原因排除法：正向找错，回溯法：反向找错。

[![pCaYCct.md.png](https://s1.ax1x.com/2023/06/27/pCaYCct.md.png)](https://imgse.com/i/pCaYCct)

### 2.2 调试和测试的区别

[![pCaYkB8.md.png](https://s1.ax1x.com/2023/06/27/pCaYkB8.md.png)](https://imgse.com/i/pCaYkB8)

