---
title: macOs设置
date: 2019-03-29 11:13:04
tags:
 - macos
---

应用设置

<!-- more -->

### 安装常用软件

- 安装brew
```
 /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

- 安装iterm
```
brew install iterm
```

- oh-my-zsh
```
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```


- 安装autojump
```
brew install autojump
cd ~
vim .zshrc


plugins=(git autojump)
```

### 开启ssd 加速
```
sudo trimforce enable
```

### vpn l2tp关闭共享密码
```
cd /etc/ppp
touch options
vim options


plugin L2TP.ppp
l2tpnoipsec
```

### 开启安装隐私中显示任何来源
```
sudo spctl --master-disable
```

### 关闭ipv6
```
networksetup -setv6off Ethernet
```
