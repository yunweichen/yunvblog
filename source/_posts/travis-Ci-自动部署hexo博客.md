---
title: travis-Ci-自动部署hexo博客
date: 2019-04-26 14:03:20
tags:
---

### travis Ci

travis ci 和 github 可以实现提交代码到github 自动部署到对应的环境

生成 id_rsa.enc

### 代码结构

在代码的主目录下 创建 .travis.yml

```

language: node_js
node_js:
- stable
branches:
  only:
  - master
before_install:
- openssl aes-256-cbc -K $encrypted_XXXXXXXXX_key -iv $encrypted_XXXXXXXXXX_iv
  -in .travis/id_rsa.enc -out ~/.ssh/id_rsa -d
- chmod 600 ~/.ssh/id_rsa
- eval $(ssh-agent)
- ssh-add ~/.ssh/id_rsa
- cp .travis/ssh_config ~/.ssh/config
- git config --global user.name 'XXXXXXX'
- git config --global user.email XXXXX
install:
- npm install hexo-cli -g
- npm install hexo-deployer-git --save
- npm install --save hexo-filter-flowchart
- npm install --save hexo-filter-sequence
- npm install
script:
- hexo clean
- hexo g
- hexo d

```