---
layout: post
title: 软件工程期末复习题(2)
tags: 软件工程
categories:
  - 软件工程习题
date: 2021-12-29 08:33:48
---



更正：

+ 第1题第2小问画流图，去除原本开始框映射成的结点【实则开始框不能映射成结点】，具体见题目，错误画法和正确画法均已给出。方便比较学习。

+ 第2题第2小问画流图，同样存在和第1题原本一样的问题，目前已修正



考察知识点：程序流程图、流图、环形复杂度

<!--more-->

```
已知有一段代码实现了 “输出ABC三个数中的最大值”，要求完成下列问题：
（1）画出代码的流程图
（2）根据该程序流程图画出该程序的流图
（3）计算该流图的环形复杂度
```

```
(1)程序流程图(书本P125)
```

![image-20211230095659538](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112300956643.png)



```
(2)流图
在流图中用圆表示结点，一个圆代表一条或多条语句。
程序流程图中的一个顺序的处理框序列和一个菱形框判定框，可以映射成流图中的一个结点。
流图中的箭头称为边，它和程序流程图中的箭头线类似，代表控制流。
在流图中一条边必须终止于一个结点，即使这个结点并不代表语句(实际上相当于一个空语句)。
由边和结点围成的面积称为区域，当计算区域数时应该包括图外部未被围起来的那个区域。

注：程序流程图中的开始框不能映射成流图中的一个结点。
同样停止框也不能映射成流图中的一个结点，只是流图中有这样的规定：
一条边必须终止于一个结点，故画流图的时候最后会有一个结点来让前面的边终止。
这就造成了让人误认为最后一个结点是由停止框映射而成的假想，其实最后一个结点相当于一个空语句。
```

<font color="red">错误画法：</font>

![image-20211230094404602](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112300944671.png)

<font color="green">正确画法：</font>

![image-20220102123623486](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201021236588.png)

```
(3)环形复杂度
书本P137,3种方法
流图中判定结点的格式为3，即结点编号为1、2、3的结点，
∵环形复杂度=判定结点+1
∴环形复杂度=3+1=4
```



考察知识点：程序流程图、流图、程序环形复杂度、白盒测试

```
输入三整数,判断是否构成三角形,如构成三角形,则输出三条边的值,否则输出“不能构成三角形”
要求:
1.用程序流程图表示该问题的算法；
2.计算程序复杂度； 
3.设计路径覆盖的测试用例。
```

```
(1)
假设输入的三整数为a,b,c
程序流程图：
```

![image-20211230100155403](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301001461.png)

```
(2)程序复杂度即环形复杂度
在此之前需画出流图
```

<font color="red">错误画法：</font>

![image-20211230101858728](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301018800.png)



<font color="green">正确画法：</font>

![image-20220104065926679](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201040659812.png)

```
流图中判定结点的数目为3，即结点编号为2、3、4的结点
∵环形复杂度=流图中判定结点的数目+1
∴环形复杂度=3+1=4
```

```
由流图可得路径：
1.①——②——⑥——⑦
2.①——②——③——⑥——⑦
3.①——②——③——④——⑥——⑦
4.①——②——③——④——⑤——⑦
```

```
(3)这是对白盒测试逻辑覆盖中的路径覆盖的考察，请重视！！！
路径覆盖的测试用例(设计所有的测试用例，来覆盖程序中的所有可能的执行路径。)
```

| 路径 | 测试用例(A，B，C) |      结果      |
| :--: | :---------------: | :------------: |
|  1   |   A=1，B=2，C=3   | 不能构成三角形 |
|  2   |   A=1，B=3，C=1   | 不能构成三角形 |
|  3   |   A=4，B=2，C=2   | 不能构成三角形 |
|  4   |   A=3，B=4，C=5   | A=3，B=4，C=5  |



考察知识点：判定树

![image-20211229091207130](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112290912207.png)

```
参考解答：
设每月通话费为x
```

![image-20211230123642960](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301236099.png)



考察知识点：类图、用例图

![image-20211230125341563](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301253001.png)

```
(1)用例图：
这道题目，没有参考答案可循，我也是自己看书理解作图的，如有问题，欢迎DM(Direct Message，私聊)！
个人认为一个系统开发完毕后，自带管理员的账号、密码，因此图书管理员无需使用该系统的注册功能。
```

![image-20211230135715349](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301357411.png)

期末考试只要求会做UML的类图，故不考虑第二小问。

因此第二小问用以下一小题来代替。

```
请按照下面描述，用UML提供的类图来建立对象模型。
一个年级有多个班级
一个班级有多名学生
每个班级有一名班主任
每个班级可能有一名副班主任
```

```
分析：
一共有5个类
年级、班级、学生、班主任、副班主任
年级的属性有年级ID和年级名，方法无
班级的属性有班级ID和班级名，方法无
学生的属性有学号、姓名、性别、年龄、班级ID、年级ID，方法有学习、玩耍
班主任、副班主任的属性有教职工工号、教师名、性别、年龄、班级ID、年级ID，方法有教书、玩耍
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301446254.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a>  :point_left:

![image-20211230144655170](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301446254.png)
