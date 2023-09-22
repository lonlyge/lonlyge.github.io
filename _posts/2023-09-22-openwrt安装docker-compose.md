---
layout: post
title: openwrt安装docker-compose
date: 2023-9-22 
tags: 经验 学习    
---
# openwrt安装docker-compose


[github项目地址]([Releases · docker/compose (github.com)](https://github.com/docker/compose)) 

## 1.命令行下载

```
$ curl -SL https://github.com/docker/compose/releases/download/v2.20.3/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
#需要能连接GitHub的网络环境
```

## 2.点击上方下载地址，按照系统需要自行下载

```
上传到 /usr/bin/ 或者 /usr/local/bin/
chmod +x /usr/local/bin/docker-compose #将可执行权限应用于安装路径中的独立二进制文件
docker-compose -v #查看版本
```

