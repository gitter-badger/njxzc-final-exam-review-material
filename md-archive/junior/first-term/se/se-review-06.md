---
layout: post
title: 软件工程期末复习题(6)
tags: 软件工程
categories:
  - 软件工程习题
date: 2022-01-02 08:37:56
---



更正：

+ 最后1题独立路径中的路径4和路径5，写错的已纠正。

感谢网友`Jacksong`的指点。:thumbsup:



考察知识点：

+ 数据流图、数据字典
+ 类与对象、事件跟踪图、状态转换图

<!--more-->

![image-20220102084027923](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020840036.png)

+ 选择A

```
(1)层次方框图
层次方框图用树形结构的一系列多层次的矩形框描绘数据的层次结构。
树形结构的顶层是一个单独的矩形框，它代表完整的数据结构，下面的
各层矩形框代表这个数据结构的子集，最底层的各个框代表组成这个数据的实际数据元素(不能再分割的元素)

层次方框图是来描述数据的层次结构的，用其表示系统需求不方便。
以下是层次图和层次方框图的比较，书本P68、P102对两者也有介绍，
个人认为用层次图表示系统的需求较为合理。鉴于层次图考到的概率不大，故忽略此题
```

![image-20220103064943223](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201030649348.png)

```
(2)数据流图
a.顶层数据流图——>0层数据流图——>1层数据流图
b.顶层数据流图——>功能级数据流图
两种思路选择其一，我选择前者，因为我的软件工程实验就按照这样的流程来逐层细分的。
不管选择哪种思路，只要数据流图工整规范，都会判对。

顶层数据流图
```

![image-20220102154220933](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201021542012.png)

```
0层数据流图
```

![image-20220103102103154](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201031021272.png)

```
1层数据流图
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201031022480.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20220103102214355](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201031022480.png)

```
(3)数据字典描述系统所涉及的数据
这边只罗列出了旅客信息中的数据元素
```

|   字段名   |     类型     |      说明      |
| :--------: | :----------: | :------------: |
|    姓名    | varchar(50)  |    旅客姓名    |
|    性别    | varchar(10)  |    旅客性别    |
|  工作单位  | varchar(50)  |  旅客工作单位  |
| 身份证号码 | varchar(50)  | 旅客身份证号码 |
|  旅行时间  |     date     |  旅客旅行时间  |
| 旅行目的地 | varchar(100) | 旅客旅行目的地 |
|    年龄    | varchar(10)  |    旅客年龄    |

```
(4)用面向数据流的方法设计软件体系结构
这道题目就是书本P114页题3(2)。题目让你用面向数据流的方法设计软件体系
结构，参考答案的解题思路是先画出数据流图，接着再补一张结构图。
鉴于结构图考到的概率不大，故忽略此题。
```




+ 选择B

```
(1)
类：旅客类、旅行社类
对象：一名旅客、一个旅行社
(2)
脚本编写期末不要求，原本想忽略的，但是看到接下的第3小问是基于第2小问的，
而第3小问属于需要掌握的知识点，故硬着头皮做了。

在建立动态模型的过程中，脚本是指系统在某一执行期间内出现的一系列事件。
```

机票预订系统的正常情况脚本

***

+ 旅行社将旅客信息输入系统
+ 系统成功为旅客安排上航班
+ 系统打印出取票通知和账单
+ 旅客凭取票通知和账单交款取票
+ 系统校对后，认定取票通知和账单无误
+ 系统打印机票给旅客

***

机票预订系统的异常情况脚本

***

+ 旅行社将旅客信息输入系统
+ 系统为旅客安排航班，发现没有该旅行时间去往目的地的航班
+ 旅客重新填写旅行时间
+ 重复流程，直至系统成功为旅客安排上航班
+ 系统打印出取票通知和账单
+ 旅客凭取票通知和账单交款取票
+ 旅客票款不足以支付机票，向朋友借钱
+ 旅客借到相应的款项，成功支付机票钱
+ 系统校对后，发现该取票通知和账单存有不一致的地方
+ 旅客拨打旅行社电话，旅行社和机场商定后成功解决取票通知和账单不一致问题
+ 系统打印机票给旅客

***



```
(3)根据脚本画出事件事件跟踪图

a.确定事件
1.输入旅客信息(发送对象：旅行社，接收对象：机票预订系统)
2.安排航班(发送对象：机票预订系统，接收对象：旅客)
3.打印取票通知和账单(发送对象：机票预订系统，接收对象：旅客)
4.凭取票通知和账单交款取票(发送对象：旅客，接受对象：机票预订系统)
5.系统校对(发送对象：机票预订系统，接收对象：旅客)
6.打印机票(发送对象：机票预订系统，接收对象：旅客)

b.画出事件跟踪图
在事件跟踪图中，一条竖线代表一个对象，每个事件用一条水平的箭头线表示，箭头方向从事件的
发送对象指向接收对象，时间从上向下递增......(书本P250)
```

![image-20220103082543387](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201030825480.png)

```
(4)画出系统状态图
机票的状态有：未预订、预订未付款、预订已付款、已打印
引起"未预定状态——>预订未付款状态"的事件：旅行社将旅客信息输入系统、成功安排航班
引起"预订未付款状态——>预订已付款状态"的事件：旅客凭取票通知和账单交款取票
引起"预订已付款状态——>已打印状态"的事件：系统校对
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201030842529.png" style="color:red;border-bottom:none">看不清楚图片，请戳我！</a> :point_left:

![image-20220103084257459](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201030842529.png)



考察知识点：

+ 数据流图、数据字典、HIPO图
+ 事件跟踪图、状态图、数据流图

![image-20220102084256162](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020842369.png)

该题供大家查漏补缺。



考察知识点：

+ 黑盒测试(等价类划分、边界值分析)

![image-20220103091838521](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201030918679.png)

```
参考解答：
(1)
a.划分等价类并编号
假设一天的取款次数为N，N至少为1；一次取款金额为X，一天取款金额为Y。
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201030904299.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20220103090406181](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201030904299.png)

```
b.给出测试用例
X								Y		N		预期结果
50								50		1		取款成功
2000、1000、1000、1000	  		  5000    4		  取款失败
51、49						   100     2       取款失败	
2500、2500					   5000    2       取款失败
2000 2000 2000					6000    3       取款失败
```



考察知识点：白盒测试(基本路径测试)

```
针对test函数按照基本路径测试方法设计测试用例。
```

```c
int test(int count,int flag)
{
	int temp=0;
	while (count>0)
	{
		if (flag==0){
			temp=count+100;
			break;
		}
		else{
            if (flag==1){
                temp=temp+10;
            }
            else{
                temp=temp+20;
            }
        }
     	count--;
	}
    
	return temp;
}
```

```
1)导出程序流程图的拓扑结构-流图(控制流程图)
2)计算流图G的环路复杂性V(G)
3)确定只包含独立路径的基本路径集
4)设计测试用例
```

```
参考解答：
1)流图由程序流程图导出，因此先画程序流程图
```

![image-20220103095751945](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201030957047.png)

```
流图：
```

![image-20220103101337444](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201031013576.png)

```
(2)环形复杂度=流图中边的条数-流图中结点数+2
流图中边的条数=10，流图中结点数=8
∴环形复杂度=10-8+2=4
【检验：环形复杂度=流图中判定结点的数目+1，
流图中判定结点的数目=3(分别为编号为2、3、6的结点)
∴环形复杂度=3+1=4】
(3)确定只包含独立路径的基本路径集
由于环形复杂度为4，所以找出4条独立路径
路径1：①——②——⑩
路径2：①——②——③——④——⑤——⑩
路径3：①——②——③——⑥——⑦——⑨——⑩
路径4：①——②——③——⑥——⑧——⑨——⑩
(4)设计测试用例
```

| 路径名 |     输入数据     | 期望结果 |
| :----: | :--------------: | :------: |
| 路径1  | count=-1，flag=1 |    0     |
| 路径2  | count=1，flag=0  |   101    |
| 路径3  | count=1，flag=1  |    10    |
| 路径4  | count=1，flag=2  |    20    |
