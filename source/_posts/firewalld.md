---
title: firewalld
date: 2019-04-023 10:00:00
tags:
 - linux
---

```
systemctl status firewalld > /dev/null 2>&1
yum install firewalld systemd -y
systemctl start firewalld
systemctl status firewalld
firewall-cmd --permanent --zone=public --add-port=12301/tcp
firewall-cmd --permanent --zone=public --add-port=12301/udp

netstat -ntlp
```
