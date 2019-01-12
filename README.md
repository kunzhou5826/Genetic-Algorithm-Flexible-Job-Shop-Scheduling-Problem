# Genetic Algorithm Flexible Job Shop Scheduling Problem
此为一个基于遗传算法 (GA) 的柔性车间调度问题 (FJSSP) 方案的加工车 (RGV) 的多机床放料移动路线最优化模拟程序。
## 运行 ##
`python main.py`

通过命令提示符的交互问询指定必要之数据与参数。

## 读入数据格式说明 ##
**输入的数据文件需为文本文件，编码为 UTF-8.** 

其中:
+ 在第一行中包含至少2个整数：

  第一个是全部作业数a，第二个是CNC机器数b(机器ID由1开始排列)，第三个参数c非必需，它是每个机器的同时进行操作容量(此算法通常为1)
  
+ 在第二行中包含b个整数：

  分别表示RGV在对应顺序CNC机器一次上下料所需之单位时间
  
+ 在第三行中包含4个整数：

  分别表示RGV 清洗作业时间 和 移动1、2和3个单位CNC机器间隔距离所需之时间
  
+ 在第四行中包含2个参数：

  分别对应 故障率(小数) 和 故障恢复时间(整数，单位时间)。
  
  若故障率不为0，机器在开始前每次将以此概率随机发生故障并停止工作指定之故障时间，此后方才恢复进入加工序列
  
+ 接下来的a行中行代表一个工件的作业(变量对应activity)：

  第一个整数是该次作业的操作工序(变量对应operation)之数量 k，
  
  第二个数字 (若k >= 1) 是可以处理第一个工序的机器(变量对应machine)数量;
  
  然后根据k，有k对(机器ID, 处理时间)的参数对以空格间隔，指定哪些机器可以处理本次工序及其处理时间;
  
  然后为第二次工序的数据，以此类推...

## 开源协议 ##
本程序代码遵循 [MIT](http://opensource.org/licenses/MIT) 开源协议。