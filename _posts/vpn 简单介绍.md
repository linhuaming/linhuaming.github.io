---
layout:     post                    # 使用的布局（不需要改）
title:      vpn介绍               # 标题 
subtitle:   vpn介绍   #副标题
date:       2023-08-01             # 时间
author:     linhuaming                      # 作者
header-img: img/post-java.jpg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - vpn
---

## vpn 简单介绍

[TOC]

### 一、vpn介绍

#### 1、vpn技术出现背景

一个技术的出现都是由于某种需求触发的。那么为什么会出现VPN技术呢？VPN技术解决了什么问题呢？

在没有VPN之前，企业的总部和分部之间的互通都是采用运营商的internet进行通信，那么Internet中往往是不安全的，通信的内容可能被窃取、修改等，从而造成安全事件。

![](https://pics3.baidu.com/feed/a8773912b31bb0518fc9aa9cbf9004bd48ede08d.jpeg@f_auto?token=8437a3ef4bd6c9386cb38a637cb2f490)





那么有没有一种技术既能实现总部和分部间的互通，也能够保证数据传输的安全性呢？

答案是当然有。

一开始大家想到的是专线，在总部和分部拉条专线，只传输自己的业务，但是这个专线的费用确不是一般公司能够承受的。而且维护也很困难。

![](https://pics5.baidu.com/feed/4034970a304e251f087d1cd6c86c171e7e3e530e.jpeg@f_auto?token=87171ddd66cb278523cd1dae75b4d2f6)





那么有没有成本也比较低的方案呢？

有，那就是VPN。VPN通过在现有的Internet网中构建专用的虚拟网络，实现企业总部和分部的通信，解决了互通、安全、成本的问题；

![](https://pics1.baidu.com/feed/d788d43f8794a4c2003ed47a7e1ec5dcac6e39b1.jpeg@f_auto?token=a212c47fd2f31279e78780eef95f9dd1)



#### 2、什么是VPN技术

那么什么是VPN技术吗？

VPN即虚拟专用网，指通过VPN技术在**公有网络**中构建**专用**的**虚拟**网络；

![](https://pics7.baidu.com/feed/94cad1c8a786c917231c6d11bed7aec63ac757ea.jpeg@f_auto?token=3335c82d8a7acff0d9521d379be82935)





用户在此虚拟网络中传输流量，从而在Internet网络中实现安全、可靠的连接。

（1）专用：

VPN虚拟网络是专门给VPN用户使用的网络，对于用户而言，使用VPN和Internet，用户是不感知的，是由VPN虚拟网络提供安全保证。



（2）虚拟：

相对于公有网络而言，VPN网络是虚拟的，是逻辑意义上的一个专网。



#### 3、常见的vpn协议

| 常见的vpn协议              | 优点                                                         | 缺点                                                       |
| -------------------------- | ------------------------------------------------------------ | ---------------------------------------------------------- |
| PPTP(点对点隧道协议)       | windows自带，无需安装，网络连接较为稳定                      | 安全性低，可以被防火墙阻止(不建议用于公司或商业用途)       |
| L2TP/IPsec------PPTP升级版 | 安全性较之pptp高，windows自带，无需安装，可用于具有相同vpn配置的多个设备 | 速度较慢(加密算法导致)，不建议用于cpu性能较低的计算机。    |
| IKEv2/IPsec                | 速度加快；安全性较高；重连速度较快；与手机兼容性也较强(较适合用于手机) | 搭建较为困难，暂时支持的平台不是很多                       |
| OpenVPN                    | 安全性较高；可配置性较强；可以绕过防火墙                     | 需要安装第三方软件；安装过程较为复杂；移动端支持较差(手机) |



### 二、vpn分类

#### 1、根据VPN建设单位不同进行划分

**（1）租用运营商VPN专线搭建企业网络**

运营商的专线网络大多数都是使用的MPLS VPN，企业通过购买运营商提供的VPN专线服务实现总部和分部间的通信需求。VPN网关为运营商所有。

![](https://pics5.baidu.com/feed/29381f30e924b8998370d2ad18ecc39c087bf6cf.jpeg@f_auto?token=6a5198b81d1e0600c09acd5a5eee1a38)



**（2）企业自建VPN网络**

企业自己基于Internet自建vpn网络，常见的如IPsec VPN、GRE VPN、L2TP VPN。

企业自己购买VPN网络设备，搭建自己的VPN网络，实现总部和分部的通信，或者是出差员工和总部的通信。

![](https://pics1.baidu.com/feed/8b82b9014a90f603a7b94db456f86d12b151ed29.jpeg@f_auto?token=d33959e148dcda7f7cceedb2322dcf2c)



#### 2、根据组网方式进行划分

**（1）远程访问VPN**

这种方式适用于出差员工拨号接入VPN的方式，员工可以在只要有Internet的地方都可以通过VPN接入访问内网资源。最常见的就是SSL VPN、L2TP VPN。

![](https://pics3.baidu.com/feed/34fae6cd7b899e51a885d8adcb4d073ac9950d70.jpeg@f_auto?token=15c153862a941b520afd863a29430a43)



**（2）站点到站点的VPN**

这种方式适用于企业两个局域网互通的情况。例如企业的分部访问总部。最常见的就是MPLS VPN、IPSEC VPN。

![](https://pics1.baidu.com/feed/8b82b9014a90f603a7b94db456f86d12b151ed29.jpeg@f_auto?token=d33959e148dcda7f7cceedb2322dcf2c)



#### 3、根据协议分类

- PPTP协议：使用GRE协议封装，加密强度较低，适用于不需要太高安全度的场景。
- L2TP协议：基于PPTP协议，加入L2TP协议使其更安全，适用于需要中等安全度的场景。
- IPSec协议：加密强度高，安全性好，但设置较为复杂，适用于需要高度安全保障的场景。



### 三、VPN关键技术

#### 1、隧道技术

VPN技术的基本原理其实就是用的隧道技术，就类似于火车的轨道、地铁的轨道一样，从A站点到B站点都是直通的，不会堵车。对于乘客而言，就是专车。

![](https://pics6.baidu.com/feed/b7003af33a87e950a249bc397fd28d4afaf2b479.jpeg@f_auto?token=f953e8dee426fb0390eb1dfb89772991)







隧道技术其实就是对传输的报文进行封装，利用公网的建立专用的数据传输通道，从而完成数据的安全可靠性传输。可以看到原始报文在隧道的一端进行封装，封装后的数据在公网上传输，在隧道另一端进行解封装，从而实现了数据的安全传输。

![](https://pics4.baidu.com/feed/a8773912b31bb0519eb3d1db599004bd48ede0a6.jpeg@f_auto?token=609d7110575dec2d9517b118fb55cfac)







隧道通过**隧道协议**实现。如GRE（Generic Routing Encapsulation）、L2TP（Layer 2 Tunneling Protocol）等。

隧道协议通过在隧道的一端给数据加上隧道协议头，即进行**封装**，使这些被封装的数据能都在某网络中传输，并且在隧道的另一端去掉该数据携带的隧道协议头，即进行解封装。报文在隧道中传输前后都要通过封装和解封装两个过程。

![](https://pics2.baidu.com/feed/8644ebf81a4c510fedba1bb60fb3fb24d52aa510.jpeg@f_auto?token=c149f99fe9ca06b3e88f96acef6a0a9b)







#### 2、身份认证、数据加密、数据验证

**（1）身份认证**

VPN网关对接入VPN的用户进行身份认证，保证接入的用户都是合法用户。

![](https://pics7.baidu.com/feed/2e2eb9389b504fc26100014d8a37391891ef6d0b.jpeg@f_auto?token=30c0e4f15fe96c4395bc4693fbabbeba)







**（2）数据加密**

将明文通过加密技术成密文，哪怕信息被获取了，也无法识别。

![](https://pics4.baidu.com/feed/1e30e924b899a9010e45e19c737fd4720308f518.jpeg@f_auto?token=394b0e0ba1dbaa2b091cc12ce0365326)









**（3）数据验证**

通过数据验证技术验证报文的完整性和真伪进行检查，防止数据被篡改。

![](https://pics3.baidu.com/feed/91ef76c6a7efce1b90bbcca5debb2dd7b68f65c4.jpeg@f_auto?token=359a9c8378054c9c2e128434186f5093)





参考：

https://baijiahao.baidu.com/s?id=1724457048928923155&wfr=spider&for=pc

https://zhuanlan.zhihu.com/p/424407038

https://blog.csdn.net/w17791476027/article/details/130166864












