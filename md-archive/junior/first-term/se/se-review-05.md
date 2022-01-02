---
layout: post
title: 软件工程期末复习题(5)
tags: 软件工程
categories:
  - 软件工程习题
date: 2022-01-01 13:07:57
---




考察知识点：N-S图、状态转换图

<!--more-->

![image-20220102090310405](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020903495.png)

```
(1)N-S图
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201021431750.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20220102143136648](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201021431750.png)

```
(2)状态转换图
do事件指定在该状态下的动作。
个人认为不会出如下图所示的状态转换图习题，因此直接给出参考答案。
```

![image-20220102144530061](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201021445127.png)



考察知识点：面向对象、状态图的理解

![image-20220101131216875](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201011312973.png)

```
参考解答：
(1)
根据稿件类的状态图可知Article类的属性有tname,inDomain,qualityOK,isApproved；
方法有submit()、initCheck()、review()、reject()、Refine()、accept()
故Article类的定义【Java实现】如下：
```

```java
public Class Article{
    private String tname;
    private boolean inDomain;
    private boolean qualityOK;
    private boolean isApproved;
    
    // 无参构造方法、有参构造方法
    // get、set方法此处省略
    
    public void submit(String tname){
        this.tname=tname;
    }
    
    public void initCheck(){
        
    }
    
    public void review(){
        
    }
    
    public void reject(){
        
    }
    
    public void Refine(){
        
    }
    
    public void accept(){
        
    }
}
```

```
(2)所有需要测试的类状态：
Submitted、InitialChecked、PeerReviewed、Rejected、Refined、Acceptted
(3)所有需要测试状态的转换
```

![image-20220102092303969](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020923037.png)

```
(4)属于后续章节的内容，故可忽略
参考答案如下图所示：
```

![image-20220102092650661](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020926736.png)



考察知识点：基本路径测试

![image-20220102090030893](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020900015.png)

```
（1）程序控制流图：
当我做到这道题目的时候，跟复习题(2)的第1题进行了比较，
最后纠正了复习题(2)的第1题流图绘制的错误。与此同时，当我再次翻看流图绘制的讲解的时候，
又发现了其中的一个坑点。

当过程设计中包含复合条件时，生成流图的方法会稍微复杂一些。所谓复合条件，就是
在条件中包含了一个或多个布尔运算法(逻辑OR,AND,NAND,NOR)。在这种情况下，应该把复合条件分解为若干个简单条件，每个简单条件对应流图中一个结点。......(书本P137、P139图6.17)
```

<font color="red">错误画法：</font>

![image-20220102095802333](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020958407.png)

<font color="green">正确画法：</font>

![image-20220102132041237](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201021320321.png)

可以先画出上图，接着再将结点内的判定条件以及边上的逻辑值去除，便可得到规范的流图，具体如下图所示：

![image-20220102132316938](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201021323041.png)

```
(2)
环形复杂度=流图中边的条数-流图中结点数+2
流图中边的条数为10，流图中结点数为7
∴环形复杂度=10-7+2=5
【或者环形复杂度=流图中判定结点的个数+1，
流图中判定结点的个数为4，分别为编号为1、2、4、5的结点
∴环形复杂度=4+1=5】
(3)程序的一个独立路径的集合
由于环形复杂度为5，所以找出5条独立路径。
路径1：①——②——④——⑦
路径2：①——②——④——⑤——⑦
路径3：①——②——④——⑤——⑥——⑦
路径4：①——③——④——⑤——⑦
路径5：①——②——③——④——⑦
```

补充：有同学可能会有疑问，路径不还有

+ 1)—3)—4)—7)
+ 1)—3)—4)—5)—6)—7)
+ 1)—2)—3)—4)—5)—7)
+ 1)—2)—3)—4)—5)—6)—7)

嘛？

答：

![image-20220102134600644](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201021346747.png)

上述的路径没满足独立路径的定义，至少包含有一条在其它独立路径中从未有过的边的路径。

+ 1)—3)—4)—7)的边在路径4和路径1中均出现过了
+ 1)—3)—4)—5)—6)—7)的边在路径4和路径3中均出现过了
+ 1)—2)—3)—4)—5)—7)的边在路径5和路径2中均出现过了
+ 1)—2)—3)—4)—5)—6)—7)的边在路径5和路径3中均出现过了

程序的环形复杂度决定了程序中独立路径的数量，而且这个数是确保程序中所有语句至少被执行一次所需的测试数量的上界【环形复杂度=独立路径数】



```
(4)根据独立路径设计测试用例
```

| 路径名 |    输入数据    |   预期结果    |
| :----: | :------------: | :-----------: |
| 路径1  | A=2，B=5，X=1  | A=2，B=5，X=1 |
| 路径2  | A=3，B=5，X=4  | A=3，B=5，X=4 |
| 路径3  | A=3，B=5，X=2  | A=3，B=5，X=2 |
| 路径4  | A=5，B=1，X=15 | A=5，B=1，C=3 |
| 路径5  | A=2，B=4，X=8  | A=2，B=4，X=4 |



考察知识点：状态转换图(状态图)

![image-20220102081554597](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020816751.png)

```
参考解答：
IP长途卡的状态有：未使用、使用、无法使用
引起"未使用状态—>使用状态"的事件:打开卡密、刮开密码；进入使用状态的动作是通过座机绑定
引起"使用状态—>无法使用状态"的事件：余额不足、超出长途卡的使用日期范围

注：
在状态图中，初态用实心圆表示，终态用一对同心圆(内圆为实心圆)表示。
中间状态用圆角矩形表示，可以用两条水平横线将它分成上、中、下3个部分。
上面部分为状态的名称，这部分是必须有的；中间部分为状态变量的名字和值，
这部分是可选的；下面部分是活动表，这部分也是可选的。

状态图：
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020945131.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20220102094516015](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201020945131.png)
