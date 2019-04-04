---
title: mac下代理多线程下载
date: 2019-03-29 10:22:12
tags:
 - 代理
categories: gfw
---

## 下载方案一

```shell

brew install axel
brew install shadowsocks-libev
brew install proxychains-ng
cd ~
touch shadowsocks.json
vim ~/shadowsocks.json
	{
        "server":"xx.xx.xx.xx",
        "server_port":XXXX,
        "local_address": "127.0.0.1",
        "local_port":1080,
        "timeout":300,
        "password":"xxxxx",
        "method":"aes-256-cfb",
        "fast_open": false
    }
vim /usr/local/etc/proxychains.conf
         socks5 127.0.0.1 1080
ss-local -c ~/shadowsocks.json
proxychains4 axel -n 10 http://xxxxxxxxxxxx

```

## 下载方案二

直接在服务器上下载需要的文件
使用 linux  scp命令

scp 上传命令
```shell

scp fileName user@Ip:/path/fileName
scp -r localFolder user@Ip:/folder

```

scp 下载命令

```shell
scp user@Ip:/path/fileName /localPath/fileName
scp -r user@Ip:/path/folder /localPath/folder
```
