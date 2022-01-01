---
layout: post
title: 软件工程复习题(4)
tags: 软件工程
categories:
  - 软件工程习题
date: 2021-12-31 18:15:25
---




考察知识点：E-R图

<!--more-->

![image-20220101093641644](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201010936757.png)

```
分析：
实体及属性：
1)商店：商店编号、商店名、地址
2)商品：商品号、商品名、规格、单价
3)职工：职工编号、姓名、性别、业绩
联系及联系属性：
1)商店和商品之间：销售联系、多对多，销售联系的属性为：月销售量
2)商店和职工之间：聘用联系，一对多，聘用联系的属性为：聘期、月薪
```

```
(1)E-R图
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201010952888.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20220101095233737](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201010952888.png)



考察知识点：白盒测试

![image-20220101124117870](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201011241971.png)

```
参考解答：
(1)(书本P163)
条件覆盖：不仅每个语句至少执行一次，而且使判定表达式中的每个条件都取到各种可能的结果。
分支覆盖：不仅每个语句必须至少执行一次，而且每个判定的每种可能的结果都应该至少执行一次，也就是每个判定的每个分支都至少执行一次。
不一定，如测试用例a=1,b=-4和a=-1，b=4满足条件覆盖，但不满足分支覆盖。
这两个测试用例使得判定表达式【a>=0 and b>=0以及(a-b)>=3 or (a-b)<=-3】每个条件都取到各种可能的结果，即真和假。但是其并没有满足每个判定的每个分支都至少执行一次。均只执行了其中的一个分支，具体如下图所示：
```

![image-20220101132124056](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201011321109.png)

```
(2)答案不唯一。
条件组合覆盖：使得每个判定表达式中条件的各种可能组合都至少出现一次
本题中每个判定各有两个条件，因此各有4个条件取值的组合，至少需要取
4个测试数据组才能满足要求。注：第二个判定中的(a-b)>=3、(a-b)<=-3不可能同时出现
即下面的条件组合⑤。
对于图11.15流程图而言，共有8种可能的条件组合，它们分别是：
①a>=0，b>=0
②a>=0，b<0
③a<0，b>=0
④a<0，b<0
⑤(a-b)>=3，(a-b)<=-3
⑥(a-b)>=3，(a-b)>-3
⑦(a-b)<3，(a-b)<=-3
⑧(a-b)<3，(a-b)>-3
最小测试用例组【无需考虑⑤】：
1)a=5，b=1【针对①和⑥两种组合】
2)a=0，b=-1【针对②和⑧两种组合】
3)a=-5，b=1【针对③和⑦两种组合】
4)a=-5，b=-1【针对④和⑦两种组合】
```



考察知识点：黑盒测试

![image-20220101135617993](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201011356142.png)

```
参考解答：
1)答案不唯一
```

|  a   |  b   |  c   |        输出结果         |
| :--: | :--: | :--: | :---------------------: |
|  2   |  2   |  2   |        正三角形         |
|  2   |  2   |  3   |       等腰三角形        |
|  3   |  4   |  5   |      不等边三角形       |
|  2   | 201  | 200  | b的取值不在允许的范围内 |
|  1   |  2   |  3   |        非三角形         |

```
2)答案不唯一
划分等价类并编号
```

| 输入条件 | 有效等价类 | 编号 | 无效等价类  | 编号 |
| :------: | :--------: | :--: | :---------: | :--: |
|    a     | 1<=a<=200  |  1   | a<1   a>200 | 2、3 |
|    b     | 1<=b<=200  |  4   | b<1   b>200 | 5、6 |
|    c     | 1<=c<=200  |  7   | c<1   c>200 | 8、9 |
|  a、b+c  |   a<b+c    |  10  |   a>=b+c    |  11  |
|  b、a+c  |   b<a+c    |  12  |   b>=a+c    |  13  |
|  c、a+b  |   c<a+b    |  14  |   c>=a+b    |  15  |

```
测试用例：
a	b	c	
0	0	0
5	5	5
250	250	250
1	1	5
1	3	2
```

```
(3)用边界值设计5个测试用例
(书本P175)按照边界值分析法，应该选取刚好等于、稍小于和稍大于等价类边界值的数据作为测试数据，而不是选取每个等价类内的典型值或任意值作为测试数据。
a	b	c	边界情况
1	1	1	合法边界
0	1	1	超出边界
1	201	1	超出边界
1	2	3	合法边界
200	200	1	合法边界
```



考察知识点：0层数据流图(顶层数据流图)、功能级数据流图

```
书店向顾客发放订单，顾客将所填订单交由系统处理，系统首先依据图书目录对订单进行检查并对合格订单进行处理，处理过程中根据顾客情况和订单数目将订单分为优先订单与正常订单两种，随时处理优先订单，定期处理正常订单。最后系统将所处理的订单汇总，并按出版社要求发给出版社。
请画出顶层数据流图(0层数据流图)和功能级数据流图
```

```
分析：
系统：图书预定系统
数据源点：顾客
数据终点：出版社
数据处理：检查订单、处理订单
数据存储：图书目录、优先订单、正常订单、汇总订单......
```

```
参考解答：
(1)顶层数据流图
```

![image-20220101083316878](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201010833043.png)

```
(2)0层数据流图
```

![image-20220101090025125](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201010900205.png)

```
(3)1层数据流图
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201010927231.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20220101092729047](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201010927231.png)



考察知识点：数据字典

![image-20211231185901621](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311859668.png)

```
问：请用数据字典定义该高校的电话号码
参考解答：
数字字符=[0|1|2|3|4|5|6|7|8|9]
数字字符A=[1|2|3|4|5|6|7|8]
非零数字字符=[1|2|3|4|5|6|7|8|9]
校内电话=数字字符A+3{数字字符}3
本市电话=非零数字字符+7{数字字符}7
区码=0+非零数字字符+1{数字字符}2
当地电话=非零数字字符+6{数字字符}7
外地电话=区码+当地电话号码
校外电话=9+[本市电话|外地电话]
电话号码=[校内电话|校外电话]
```