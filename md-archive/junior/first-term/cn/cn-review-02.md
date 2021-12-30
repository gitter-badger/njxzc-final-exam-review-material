---
layout: draft
title: 计算机网络期末复习题(2)
date: 2021-12-29 09:38:43
tags: 计算机网络
categories:
  - 计算机网络习题
---





![image-20211229094421123](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112290944214.png)





![image-20211229094548789](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112290945876.png)



![image-20211229094710305](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112290947367.png)



![image-20211229094749426](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112290947518.png)





![image-20211229112939115](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112291129184.png)

```
1.参考解答：
网络地址=IP地址和子网掩码相与，即
00001010.01010000.00000000.00000000
and
11111111.11100000.00000000.00000000
得00001010.01000000.00000000.00000000，转换成十进制为10.64.0.0

广播地址：主机号部分全置为1
∴广播地址为10.01011111.11111111.11111111，转换成十进制为10.95.255.255
∵用户地址介于网络地址和广播地址之间
∴最小用户地址为10.64.0.1，最大用户地址为10.95.255.254

2.参考解答：
多项式G(x)=x^5+x^4+x^2+1——>除数为110101
除数的位数=n+1=6得n=5，所以原始数据加5位0，即10011010110100000
100110101101÷110101，余数为11110，即循环冗余码CRC为11100
```



![image-20211229095901863](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112290959931.png)



