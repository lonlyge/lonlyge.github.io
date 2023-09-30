---

layout: post
title: x-ui面板+reality协议部署
date: 2023-9-30 
tags: 经验 学习 

---

# x-ui面板+reality协议部署Vless

## 准备工作

> [RackNerd垃圾vps](https://www.racknerd.com/)

> [魔改x-ui](https://v2rayssr.com/go?url=https://github.com/FranzKafkaYu/x-ui/)
>
> [Reality](https://github.com/XTLS/REALITY)

> [查找目标网址](https://www.ssllabs.com/projects/index.html)



## 搭建环境

> ### VPS:  

RackNerd的1核1G的垃圾vps

> ### 系统

Ubuntu 20.04 64 Bit



## 搭建步骤

### 安装依赖

```bash
## 以下为 CentOS 命令
yum update -y 
yum install curl wget -y
```

```bash
## 以下为 Debian / Ubuntu 命令
apt update -y 
apt install curl wget -y
```



### 安装x-ui

```bash
bash <(curl -Ls https://raw.githubusercontent.com/FranzKafkaYu/x-ui/master/install.sh)

```

![](/images/posts/github/093001.png)



### 开启BBR加速

1. 系统自带

   ```bash
   echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
   echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
   sysctl -p
   ```

2. BBRplus

   ```bash
   wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh
   ```

3. 查看BBR加速是否开启

   ```bash
    lsmod | grep bbr
    #看到有 tcp_bbr 模块即说明 BBR 已启动
   ```

   

### 查找目标网址

> 目标网站最低标准：国外网站，支持 TLSv1.3 与 H2，域名非跳转用
>
> 加分项：IP 相近（更像，且延迟低），Server Hello 后的握手消息一起加密（如 dl.google.com），有 OCSP Stapling
>
> 配置加分项：禁回国流量，TCP/80、UDP/443 也转发（REALITY 对外表现即为端口转发，目标 IP 冷门或许更好）

[查看TLS点这里](https://www.ssllabs.com/projects/index.html)

1. 进入网址，点击[<font color="#dd0000">SSL Server Test</font>]，输入网址或点击下方网址，查看网址详情中的[<font color="#dd0000">Protocols</font>]中的“TLS1.3”是否为”yes”

   > 如点击网址出现多个IP，选择ipv4地址

![](/images/posts/github/093002.png)

2. 复制适合的网址到浏览器中打开，F12检查网页，找到[<font color="#dd0000">安全</font>]查看（如没有“安全”项，点击右边“+”调出）

   ![](/images/posts/github/093003.png)

3. 点击[<font color="#dd0000">网络</font>]，刷新页面，查看[<font color="#dd0000">协议</font>]是否支持[<font color="#dd0000">h2</font>]

   ![](/images/posts/github/093004.png)

4. [点这里查看目标网是否支持"OCSP Stapling"](http://web.chacuo.net/netocspstapling)（不支持也关系不大）

   

### 设置x-ui面板

1. 浏览器打开：http://<span></span>ip:端口
2. 切换<font color="#dd0000">xray 状态</font>到1.8以上
3. 点击<font color="#dd0000">面板设置</font>，待系统自动分配“面板url根路径”并重启完成

### 部署vless+ reality节点

> 添加入站，配置方法很简单，按下图修改即可，其他不明白用处的地方都可以不变

 ![](/images/posts/github/093005.png)



### Reality客户端推荐

- OpenWrt

  passwall	passwall2		

- Windows

  [v2rayN](https://github.com/2dust/v2rayN)

- Android

  [v2rayNG](https://github.com/2dust/v2rayNG)

- IOS

  shadowrocket

- MacOS

  [v2rayU](https://github.com/yanue/V2rayU)
