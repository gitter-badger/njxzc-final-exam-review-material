---
layout: post
title: 操作系统期末复习题(2)
tags: 操作系统
mathjax: true
categories:
  - 操作系统习题
date: 2022-01-08 19:06:32
---



更正：

+ 题5，LRU算法更正

感谢网友`Jackson`的指点。:thumbsup:



考察知识点：处理机调度算法

<!--more-->

![image-20220108190832102](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201081908164.png)

```
参考解答：
周转时间=完成时间-到达时间
平均周转时间=(所有作业的周转时间)/作业的个数
(1)优先级调度算法：
优先级高的任务先获得处理机。
故获得处理机的任务顺序依次为B、E、A、C、D
```

| 作业 | 到达时间 | 服务时间 | 开始时间 | 完成时间 | 周转时间 |
| :--: | :------: | :------: | :------: | :------: | :------: |
|  B   |    0     |    6     |    0     |    6     |    6     |
|  E   |    0     |    8     |    6     |    14    |    14    |
|  A   |    0     |    10    |    14    |    24    |    24    |
|  C   |    0     |    2     |    24    |    26    |    26    |
|  D   |    0     |    4     |    26    |    30    |    30    |

```
∴平均周转时间=(6+14+24+26+30)/5=20min
```

```
(2)时间片轮转算法：
每个任务每次仅运行一个时间片。
故获得处理机的任务顺序依次为
A、B、C、D、E、
A、B、D、E、
A、B、E、
A、E、
A、
∴
任务A的周转时间为15*2=30min
任务B的周转时间为11*2=22min
任务C的周转时间为3*2=6min
任务D的周转时间为8*2=16min
任务E的周转时间为14*2=28min
∴平均周转时间=(30+22+6+16+28)/5=20.4min
```



考察知识点：磁盘的相关计算

![image-20220108190920329](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201081909379.png)

```
参考解答：
读取该文件需要花费的时间由3部分组成(这边没有提及到时延)
①寻道时间【磁头移动到指定磁道上所经历的时间】
②平均等待时间/平均旋转延迟时间【扇区移动到磁头下面所经历的时间】
③传输时间【读取文件所经历的时间】
寻道时间=(100-50)*1=50ms
平均等待时间：
磁盘的转速为7200rpm——>磁盘的转速为每分钟7200转
∴磁盘转一圈所需的时间为
```

$$
\frac{1min}{7200r/min}=\frac{1}{7200}min
$$

```
又∵1min=60s，1s=1000ms
```

$$
∴磁盘旋转一周所需的时间为\frac{1}{7200}*60=\frac{1}{120}s=\frac{25}{3}ms
$$

```
又∵平均等待时间为磁盘转一圈所需时间的一半
```

$$
∴平均等待时间=\frac{25}{3}*\frac{1}{2}=\frac{25}{6}ms≈4.17ms
$$

```
传输时间=10MB/100MB/s=0.1s=100ms
∴读取该文件需要花费的时间=50+4.17+100=154.17ms
```



考察知识点：索引文件

![image-20220108191010266](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201081910319.png)

```
参考解答：
(1)
一个磁盘块能容纳的表项数=一个磁盘块大小/一个表项大小=512B/3B
∵文件索引表的每个表项又对应一个磁盘块，一个磁盘块大小为512B
∴该文件系统能管理的最大文件是512B/3B*512B
(2)
采用2级索引，该文件系统能管理的最大磁盘空间是
(512B/3B)*(512B/3B)*512B
采用3级索引，该文件系统能管理的最大磁盘空间是
(512B/3B)*(512B/3B)*(512B/3B)*512B
```



考察知识点：多道程序

![image-20220108202946441](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201082029493.png)

```
参考解答：
并发性：多个事件在同一时间间隔内发生
由题意得该场景为多道程序，CPU不能被抢占
```

![image-20220108211121071](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201082111189.png)

```
(2)周转时间=完成时间-到达时间
程序A的周转时间=300-0=300ms
程序B的周转时间=300-50=300ms
(3)
CPU有空闲等待，在100ms~150ms之间等待；
程序B运行时有空闲等待，在180ms~200ms之间等待。
```



考察知识点：页面置换算法

![image-20220108211557997](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201082115038.png)

```
参考解答：
最佳页面置换算法(OPT)：
其所选择的被淘汰页面，将是以后永不使用的或在(未来)最长时间内不会被访问的页面
当置换时，发现有多个页面未来永不使用，则任意选择一个页面进行置换即可！
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201090723283.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20220109072322210](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201090723283.png)

```
缺页次数=8
页面总访问次数=12
缺页中断率=8/12≈0.67
```

```
先进先出页面置换算法(FIFO)：
该算法总是会淘汰最先进入内存的页面，即选择在内存中驻留时间最久的页面予以淘汰
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201090723380.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20220109072307334](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201090723380.png)

```
缺页次数=9
页面总访问次数=12
缺页中断率=9/12=0.75
```

```
最近最久未使用算法(LRU)：
根据页面调入内存后的使用情况来做决策，由于无法预测各页面将来的使用情况，
只能将"最近的过去"作为"最近的将来"的近似。因此LRU页面置换算法会选择
最近最久未使用的页面予以淘汰。
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201090722118.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

<font color="red">错误解答：</font>

![image-20220109072246041](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201090722118.png)

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201092128430.png" style="color:green;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

<font color="green">正确解答：</font>

![image-20220109212848370](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201092128430.png)

```
缺页次数=10
页面总访问次数=12
缺页中断率=10/12≈0.83
```



考察知识点：死锁

![image-20220109073649531](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201090736608.png)

```
参考解答：
(1)
系统运行过程中有可能产生死锁。
原因：根据题意，系统中有R1设备3台，它要被4个进程共享，
且每个进程对它的最大需求均为2，那么，当P1、P2、P3进程各得到1个R1设备时，
它们可以继续运行，并均可以顺利地申请到1个R2设备，但当它们第2次申请R1设备时，
因系统已无空闲的R1设备，它们将全部阻塞，并进入循环等待的死锁状态。
(2)进程-资源图：
```

![image-20220109074925606](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201090749675.png)
