# 浅析URL

## 什么是URL

### URL

* 全称Uniform Resource Locator，意思是统一资源定位器。俗称网址或者链接。

### URL包括哪几个部分？每个部分分别有什么作用？

* 协议+域名或IP+端口号+路径+查询字符串+锚点

* 举例：`https://www.baidu.com/s?wd=hello&rsv_spt=1#5`

1. http:// 是协议 ，对于前端来说只有两种协议 http:// 和 https://。

2. www.baidu.com是域名，表明正在请求哪个web服务器。一个域名可以对应不同的IP，这个叫做均衡负载，防止一台机器扛不住。

3. 端口：服务器默认用80提供http服务；服务器默认用443提供https服务。 

4. 路径： /s 是路径，全称是网络服务器上的资源路径，在同一个服务器上使用不同的路径就可以得到不同的页面。比如html和CSS。

5. ?wd=hello&rsv_spt=1 是查询参数，可以理解为提供给网络服务器的额外参数。

6. #5 是锚点，#后面的内容被叫做片段标识符。 锚点看起来有中文，实际上不支持中文。 锚点无法在Network面板看到的。 因为锚点不会传给服务器。

## DNS 的作用是什么？nslookup 命令怎么用？

### DNS：Domain Name System 域名系统

* 作用：域名和IP是通过DNS对应起来的。 DNS（Domain Name Server，域名服务器）是进行域名(domain name)和与之相对应的IP地址 (IP address)转换的服务器。

### nslookup 命令

* nslookup命令用于查询DNS的记录，查看域名解析是否正常，在网络故障的时候用来诊断网络问题。语法格式：`nslookup –option1 –option2 host-to-find dns-server`。 有两种模式：一种是非交互模式，每次查询需要输入完整的命令和参数；一种是交互模式，在命令行下输入`nslookup baidu.com`,进入交互模式后不再需要输入完整的命令便可以进行查询，并且可以连续的进行查询.

## IP 的作用是什么，ping 命令怎么用?

### IP (Internet Protocal)

* 主要约定两件事：一、如何定位一台设备；二、如何封装数据报文以跟其他设备交流。

* IP 分为外网和内网。内网的设备可以互相访问，但不能直接访问外网；如果想要访问外网，必须用路由器中转。

* 几个特殊的IP，分别是

1. 127.0.0.1 表示自己；

2. localhost通过hosts指定为自己；

3. 0.0.0.0不表示任何设备。

### ping命令

* 在网络中ping是一个十分强大的TCP/IP工具。它的作用主要为：1、用来检测网络的连通情况和分析网络速度。2、根据域名得到服务器IP。3、根据ping返回的TTL值来判断对方所使用的操作系统及数据包经过路由器数量。

* 例如：baidu.com 对应什么IP：`ping baidu.cpm`

* 例如：qq.com 对应什么IP： `ping qq.com` 

## 域名是什么，分别哪几类域名?

### 域名

* 域名就是对IP的别称。

* 一个域名可以对应不同IP；这个叫做均衡负载，防止一台机器扛不住。一个IP可以对应不同的域名，这个叫共享主机。

### 域名的分类

* com是顶级域名；

* 二级域名（俗称一级域名），例如：xiedaimala.com 
  
* 三级域名（俗称二级域名），例如：www.xiedaimala.com 

* 注意：二级域名和三级域名可以不是一家公司，也可以是。 