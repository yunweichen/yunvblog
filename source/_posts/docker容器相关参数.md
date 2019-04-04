---
title: docker容器相关参数
date: 2019-03-29 13:43:46
tags:
 - docker
---

<!-- toc -->

## 背景：在一起开发中需要在docker的开发环境中拨vpn 连接到远程的数据库

启动参数需要增加以下，否则无法使用vpn

``` shell
docker run -it --cap-add=NET_ADMIN --device /dev/net/tun 镜像id /bin/bash
```

## 背景：测试的开发容器启动太多

删除所有未运行的容器

``` shell
sudo docker rm $(sudo docker ps -a -q)
```
