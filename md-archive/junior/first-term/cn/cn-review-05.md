---
layout: post
title: 计算机网络期末复习题(5)
tags: 计算机网络
categories:
  - 计算机网络习题
date: 2022-01-03 15:36:47
---




考查知识点：常用网络命令

<!--more-->

```
请分别写出Windows系统下以下常用网络命令的作用
1)ping命令
2)ipconfig命令
3)netstat命令
4)arp命令
5)tracert命令
6)route命令
```

```
参考解答：
1)ping命令的作用是测试网络连接量
2)ipconfig命令的作用是显示当前电脑的TCP/IP网络的配置信息
3)netstat命令的作用是显示网络连接、路由表、网络接口等信息
4)arp命令的作用是显示和修改地址解析协议(ARP)缓存中的条⽬
5)tracert命令的作用是确定IP数据包访问目标所采取的路径
6)route命令的作用是展示或操作IP路由表
```



考察知识点：路由器IP地址的配置

```
请你对路由器R1的两个接口进行IP地址的配置，使得最终PC1能ping通PC2。
```

![image-20220103195941097](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201031959175.png)

```shell
# 对路由器R1的G0/0接口进行IP地址的配置
回车
enable
config terminal
interface G0/0
ip address 192.2.0.1 255.255.255.0
no shutdown
exit
# 对路由器R1的G0/1接口进行IP地址的配置
回车
enable
config terminal
interface G0/1
ip address 192.2.1.1 255.255.255.0
no shutdown
exit
```



考察知识点：静态路由、默认路由的配置

```
请写出配置递归的静态路由、直连的静态路由以及默认路由配置的一般流程。
参考解答：
```

```shell

回车
enable
config terminal
# 以下配置均需在全局模式下进行
# 配置一条递归的静态路由
# 命令格式：ip route 目的网络的网络地址 目的网络的子网掩码 下一跳的IP地址
ip route network-address subnet-mask ip-address
# 配置一条直连的静态路由
# 命令格式：ip route 目的网络的网络地址 目的网络的子网掩码 指定送出的接口
ip route network-address subnet-mask exit-intf
# 配置默认路由
# 命令格式：ip route 0.0.0.0 0.0.0.0 指定送入的接口/指定送入的接口的IP地址
ip route 0.0.0.0 0.0.0.0 {ip-address or exit-intf}
```

<font color="red">注意点：</font>

**递归的静态路由的最后一个参数是下一跳的IP地址**

**直连的静态路由的最后一个参数是指定送出的接口**

**默认路由的最后一个参数是指定送入的接口/指定送入的接口的IP地址**



考察知识点：路由器配置RIP

```
请你对路由器进行RIP配置，使得最终PC1能ping通PC2。【假设各路由器均已配置好IP地址】
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201032023035.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20220103202329920](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201032023035.png)

```
参考解答：
```

```shell
# 路由器R1的RIP配置
回车
enable
config terminal
router rip
version 2
no auto-summary
network 192.2.0.0
network 10.2.1.0
# 路由器R2的RIP配置
回车
enable
config terminal
router rip
version2
no auto-summary
network 10.2.1.0
network 10.2.0.0
# 路由器R3的RIP配置
回车
enable
config terminal
router rip
version 2
no auto-summary
network 10.2.0.0
network 192.2.1.0
```



考察知识点：VLAN的划分

```
请你在下图中的交换机S1、S2上分别创建VLAN10和VLAN20，并将PC11、PC12划分到同一个VLAN10,
PC21、PC22划分到同一个VLAN20，同时再配置一下交换机之间的接口。使得PC11能ping通PC12。
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112251331337.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112251331337.png)

```
参考解答：
```

```shell
# 交换机S1新建VLAN10、VLAN20
回车
enable
config terminal
vlan 10
name VLAN10
vlan 20
name VLAN20
# 交换机S2新建VLAN10、VLAN20
回车
enable
config terminal
vlan 10
name VLAN10
vlan 20
name VLAN20
```

```shell
# 将PC11、PC12划分到同一个VLAN10、将PC21、PC22划分到同一个VLAN20
# S1接口的配置
config terminal
interface F0/10
switchport mode access
switchport access vlan 10
interface F0/20
switchport mode access
switchport access vlan 20
# S2接口的配置
config terminal
interface F0/10
switchport mode access
switchport access vlan 10
interface F0/20
switchport mode access
switchport access vlan 20
```

```shell
# 交换机之间接口的配置
# S1接口的配置
config terminal 
interface G0/1
switchport mode trunk
# S2接口的配置
config terminal 
interface G0/1
switchport mode trunk
```



考察知识点：配置单臂路由

```
请你在交换机上分别创建VLAN10和VLAN20，接着将相应的PC划分到对应的VLAN，与此同时还需设置交换机与交换机之间、
交换机和路由器之间的接口模式，最后配置路由器子接口。保证经前面的配置后PC11能ping通PC12。
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112181021679.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:


![](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112181021679.png)

```
参考解答：
```

```shell
# 交换机上创建VLAN
# S1创建VLAN
回车
enable
config terminal
vlan 10
name VLAN10
vlan 20
name VLAN20
# S2创建VLAN
回车
enable
config terminal
vlan 10
name VLAN10
vlan 20
name VLAN20
# S0创建VLAN
回车
enable
config terminal
vlan 10
name VLAN10
vlan 20
name VLAN20
```

```shell
# 将相应的PC划分到对应的VLAN
# S1的接口配置
interface F0/10
switchport mode access
switchport access vlan 10
interface F0/20
switchport mode access
switchport access vlan 10
# S2的接口配置
interface F0/10
switchport mode access
switchport access vlan 20
interface F0/20
switchport mode access
switchport access vlan 20
```

```shell
# 设置接口模式
# S1的接口设置
interface F0/22
switchport mode trunk
interface F0/24
switchport mode trunk
# S2的接口设置
interface range F0/22-23
switchport mode trunk
# S0的接口设置
interface range F0/23-24
switchport mode trunk
interface G0/1
switchport mode trunk
```

```shell
# 路由器子接口配置
interface G0/0.10
encapsulation dot1q 10
ip address 192.2.0.126 255.255.255.128
interface G0/0.20
encapsulation dot1q 20
ip address 192.2.0.254 255.255.255.128
interface G0/0
no shutdown
```



考察知识点：配置三层交换

```
请你在交换机上分别创建VLAN10、VLAN20、VLAN30，接着将对应的主机划分到相应
的VLAN，与此同时还得设置交换机与交换机之间的接口模式，最后对三层交换机进行
配置，使得PC11能ping通PC21。
```

![image-20220103211133417](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202201032111529.png)

```shell
# 交换机创建VLAN
# S1创建VLAN
回车
enable
config terminal
vlan 10
name VLAN10
vlan 20
name VLAN20
vlan 30
name VLAN30
# S2创建VLAN
回车
enable
config terminal
vlan 10
name VLAN10
vlan 20
name VLAN20
vlan 30
name VLAN30
# S3创建VLAN
回车
enable
config terminal
vlan 10
name VLAN10
vlan 20
name VLAN20
vlan 30
name VLAN30
# M1创建VLAN
回车
enable
config terminal
vlan 10
name VLAN10
vlan 20
name VLAN20
vlan 30
name VLAN30
```

```shell
# 将相应的主机划分到对应的VLAN
# S1接口的配置
interface F0/1-2
switchport mode access
switchport access vlan 10
# S2接口的配置
interface F0/1-2
switchport mode access
switchport access vlan 20
# S3接口的配置
interface F0/1-2
switchport mode access
switchport access vlan 30
```

```shell
# 设置接口模式
# S1接口的设置
interface range F0/3-4
switchport mode trunk
# S2接口的设置
interface range F0/3-5
switchport mode trunk
# S3接口的设置
interface F0/4
switchport mode trunk
interface F0/6
switchport mode trunk
# M1接口的配置
interface G1/0/2
switchport trunk encapsulation dot1q
switchport mode trunk
interface G1/0/3
switchport trunk encapsulation dot1q
switchport mode trunk
interface G1/0/4
switchport trunk encapsulation dot1q
switchport mode trunk
```

```shell
# 三层交换机M1的配置
interface vlan 10
ip address 192.168.2.126 255.255.255.0
no shutdown
interface vlan 20
ip address 192.168.2.190 255.255.255.0
no shutdown
interface vlan 30
ip address 192.168.2.254 255.255.255.0
no shutdown
ip routing
```

