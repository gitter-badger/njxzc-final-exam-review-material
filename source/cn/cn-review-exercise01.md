# 计算机网络期末复习题(1)




> 注：没有的解析的题目，自己可以自行百度搜索，或者看书理解。

## 1.单选题

![image-20211227073736103](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270737287.png)

```
参考解答：C
解析：
子网掩码为255.255.255.224——>IP地址是32位的二进制代码，网络号部分占27位，主机号部分占5位。
又∵主机号全0代表这个网络段本身，称之为"网络地址"。
∴只需将IP地址为218.22.50.40的主机号部分置为0，即得到该主机驻留子网的网络地址。
218.22.50.00101000，将该IP地址的最后5位全置0，得：
218.22.50.00100000，转换成十进制为218.22.50.32。
故选择C选项
```

![image-20211227074719096](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270747188.png)

```
参考解答：D
备注：
划分子网是把IP地址的主机号host-id进行再划分，而不改变IP地址的网络号net-id(对于分类的IP地址而言)；
对于无分类编址的IP地址而言,划分子网是把IP地址的主机号host-id进行再划分，即增加IP地址的网络前缀。
划分出来的子网使用相同的掩码。
解析：
C类网络——>32位的IP地址中，网络号部分占24位，主机号部分占8位。
因为每借一位主机号，则可多出2(2^1)个子网。
故要想切割成5个子网，则需借3位主机号(2^3=8>5;2^2=4<5)。
故网络号部分占27(24+3)位。
即子网掩码为11111111.11111111.11111111.11100000，
转换成十进制为255.255.255.224。
故选择D选项
```

![image-20211227075651333](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270756438.png)

```
参考解答：C
解析：
常识性问题：HTTP协议
```

![image-20211227075828291](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270758375.png)

```
参考解答：D
解析：(书本P275)
端口不是默认的80端口，则不可省略；访问网站一般都是访问的是index.html，这部分可省略。
```

![image-20211227080140411](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270801473.png)

```
参考解答：A
解析：
转发数据包时，网络层使用的主要信息依据是转发表，即IP路由表。
```

![image-20211227080532829](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270805915.png)

```
参考解答：B
解析：
该计算机网络系统是属于局域网(LAN，Local Area Network)，
故选择B选项
A选项PAN(Personal Area Network)，代表个人区域网
C选项MAN(Metropolitan Area Network)，代表城域网
D选项WAN(Wide Area Network)，代表广域网
```

![image-20211227080958913](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270809997.png)

```
参考解答：C
解析：(书本P307)
SNMP(Simple Network Management Protocol)：简单网络管理协议
A选项用于邮件发送；
B选项用于文件传输；
D选项用于浏览器和Web服务器之间传送万维网文档。
```

![image-20211227081613411](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270816499.png)

```
参考解答：C
解析：
A选项比特流是物理层的协议数据单元(Protocol Data Unit)；
D选项分组是网路层的PDU。
```

![image-20211227081836416](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270818494.png)

```
参考解答：C
解析：(书本P124表4-2)
IP地址的每个字段的十进制范围为0~255，A选项的第三个字段为809，故不合法；
B选项属于C类IP地址，其主机号部分全为1，则代表广播地址，故不合法；
D选项，属于A类IP地址，其网络号部分全为0，一般不指派，故不合法。
```

![image-20211227082631448](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270826506.png)

```
参考解答：B
解析：
通过路由器或者三层交换机才能通信，表明两个主机属于不同的网络。
子网掩码为255.255.192.0，表明32位的IP地址，网络号部分占18位，主机号部分占14位。
主机IP地址为129.23.144.16，将IP地址的后两个字段转换成二进制为129.23.10010000.00010000，
故该主机所处的网络的网络地址为129.23.10000000.00000000【主机号部分置为0，代表这个网络段本身】
转换成十进制为129.23.128.0。该网段的主机IP地址范围为129.23.128.1~129.23.255.254【去掉主机
号全为0和全为1的部分】
可以发现A、C、D选项均属于该网络，只有B选项属于其他网络，故选择B选项。
```

![image-20211227085950266](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270859389.png)

```
参考解答：C
解析：(书本P133)
```

![image-20211227090315729](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270903824.png)

```
参考解答：D
解析：(书本P157-167)
OSPF和RIP都属于动态路由，故A选项错误；
OSPF属于链路状态型路由协议，RIP属于距离向量型路由协议；
D选项是对的，C选项前后颠倒了。
```

![image-20211227090916983](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270909100.png)

```
参考解答：A
解析：(书本P263)
com(通用顶级域名)
net(网络服务机构)
org(非营利性租住)
gov(政府部门)
```

![image-20211227091306941](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270913985.png)

```
参考解答：D
解析：(书本P296 6-1)
TCP/IP体系的电子邮件系统规定电子邮件地址(E-mail address)的格式如下：
用户名@邮件服务器的域名
```

![image-20211227091503558](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270915633.png)

```
参考解答：B
解析：(书本P215表5-2)
```

![image-20211227091616097](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270916171.png)

```
参考解答：D
解析：(书本P158)
内部网关协议IGP(Interior Gateway Protocol)，即在一个自治系统内部使用的路由选择协议，
而这与在互联网中的其他自治系统选用什么路由选择协议无关。
```

![image-20211227091829556](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112270918642.png)



```
参考解答：B
解析：(见下图)
```

![image-20211227100147965](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271001050.png)

![image-20211227100305217](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271003268.png)

```
参考解答：D
解析：
IP地址为184.231.138.239，其属于B类IP地址。
网络号部分占16位，主机号部分占16位。
因主机地址部分的前10位用于子网，则主机号部分只剩下6位。
故子网掩码为11111111.11111111.11111111.11000000，
转换成十进制为255.255.255.192
```

![image-20211227101405956](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271014036.png)

```
参考解答：A
解析：(书本P95/见下图)
```

![image-20211227101435132](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271014195.png)

![image-20211227101733124](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271017215.png)

```
参考解答：A
解析：(见下图)
```

![image-20211227102146133](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271021227.png)



## 2.多选题

![image-20211227102255564](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271022636.png)

```
**参考解答：A、C、D
解析：
Web服务器是提供WWW服务的，不需要具有创建和编辑Web页面的功能。
服务器和Web服务器不是一个东西。
在云厂商处购买的服务器叫做云服务器，你可以给其安装Linux系统镜像或者是Windows Server等镜像；
而Web服务器是Tomcat、Nginx这类，具体的可以看下图解析。
Web服务器一般只需对其进行配置，如nginx，你需要配置网站根目录位置等，
我从来没有用Web服务器，如nginx创建或编辑过一个html文件，因此B选项错误。
```

![image-20211227133452601](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271334674.png)

![image-20211227110117003](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271101068.png)

```
参考解答：A、B、C
解析：(书本P44)
```

![image-20211227110405434](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271104485.png)

```
参考解答：A、B、C、D
```

![image-20211227110642538](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271106640.png)

```
**参考解答：C、D
解析：
流量控制，是为了让发送方的发送速率不要太快，让接收方来得及接收，故A选项错误；
分段和重组，是为了解决数据包过长的情况，故B选项错误
```



## 3.判断题

![image-20211227111918170](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271119269.png)

```
**参考解答：错误
解析：
不是数据报的MAC地址表，是三层交换机的MAC地址表。
```

![image-20211227111934672](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271119720.png)

```
参考解答：正确
解析：(书本P143)
```



## 4.填空题

![image-20211227130418061](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271304112.png)

```
参考解答：广域网、城域网、局域网
解析：(书本P19)
```



![image-20211227130431426](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271304505.png)

```
参考解答：通信、资源
```

![image-20211227132853369](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271328427.png)

```
参考解答：调幅、调频、调相
解析：(书本P45)
```



![image-20211227130616672](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271306745.png)

```
参考解答：IP地址
```



## 5.问答题

![image-20211227131844853](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271318940.png)

```
参考解答：
解析：
IP数据报长度=IP首部+IP数据报数据部分
故IP数据报数据部分=4000-20=3980字节
MTU(Maximum Transfer Unit)：最大传送单元。当一个IP数据报封装成链路层的帧时，此数据报的总长度(即首部加上数据部分)一定不能超过下面的数据链路层所规定的MTU值。
最常用的以太网就规定其MTU值是1500字节。即每一个分片的总长度(IP首部固定的20字节+每一个分片IP数据报的数据部分，当然这边约定IP数据报首部的可选字段长度为0)要<=1500，所以每一个分片IP数据报的数据部分<=1480。分片肯定是分得越少越好，因此每一个分片的IP数据报的数据部分取最大值1480。
IP数据报总长度/每一个分片的IP数据报的数据部分的最大值=3980÷1480=2...1020
∴IP数据报数据部分分片数==2+1=3
各数据报分片的数据字段长度为1480、1480、1020
片偏移字段的取值分别为
1480*(1-1)/8=0
1480*(2-1)/8=185
1480*(3-1)/8=370

MF(More Fragment)，MF=1表示后面还有切片的数据报。MF=0表示这已是若干数据报报片中的最后一个。
故MF标志分别为1、1、0
```



![image-20211227131857815](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271318888.png)

```
参考解答：
解析：
采用CRC的多项式是P(X)=X^4+X+1——>由多项式表示CRC方法得除数p=10011
除数n+1=5，得n=4.所以原始数据加4位0，为11010110110000。
11010110110000÷10011，余数为1110，即校验序列FCS的值为1110
```



![image-20211227132027366](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271320452.png)

还有一列是主机范围(3)(6)(9)

```
参考解答：
(1)28.85.245.0
(2)28.85.245.255
(3)28.85.245.1~8.85.245.254
(4)153.50.6.0
(5)153.50.6.127
(6)153.50.6.1~153.50.6.126
(7)200.12.45.96
(8)200.12.45.127
(9)200.12.45.97~200.12.45.126
解析：
这边所说的子网地址，表示的是该IP地址所处网络的网络地址。
因此子网地址的求解，均可以套用公式：网络地址=IP地址与子网掩码相与
28.85.245.00001000 and 255.255.255.0 得 28.85.245.0
153.50.6.00011010 and 255.255.255.10000000 得 153.50.6.0
200.12.45.01111011 and 255.255.255.11100000 得 200.12.45.01100000
转换成十进制为200.12.45.96

主机部分全为1，代表该网络的广播地址。

主机范围，即去掉主机部分全为0和全为1的IP地址。
```



![image-20211227132115120](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112271321218.png)

```
参考解答：
(1)会话层
(2)网络层
(3)数据链路层
(4)运输层
(5)IP
解析：(书本P31)
```

