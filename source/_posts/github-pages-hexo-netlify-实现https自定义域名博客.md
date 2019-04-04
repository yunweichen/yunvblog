---
title: github pages + hexo + netlify 实现https自定义域名博客
date: 2019-03-29 10:51:33
tags:
 - 博客
---

本博客搭建方案

<!-- more -->

## 方案一： 阿里云域名和github+netlify

### github pages 搭建静态页面博客

More info: [github pages](https://pages.github.com/)

### hexo

More info: [hexo官网](https://hexo.io/zh-cn/)
           [hexo文档](https://hexo.io/zh-cn/docs/)
           [hexo主题](https://hexo.io/themes/)

### 购买的域名和netlify实现https

More info: [方案](https://jingyan.baidu.com/article/f79b7cb3309be79144023ea4.html)

## 方案二： 腾讯云域名和coding+cloudflare

### coding pages 服务搭建静态页面博客

More info: [coding pages](https://dev.tencent.com/help/doc/quick-start/creating-pages)
More info: [其他博客](https://www.jianshu.com/p/a19962485b4a)

### cloudflare 修改域名解析dns

More info: [cloudflare](https://www.cloudflare.com/zh-cn/)

### hexo 插件

1. 自动生成目录 More info: [详细教程](https://www.npmjs.com/package/hexo-toc)
```shell
npm install hexo-toc --save
```

2. 流程图和时序图  More info: [详细教程](https://www.liuyude.com/How_to_make_your_HEXO_blog_support_handwriting_flowchart.html)
```shell
npm install --save hexo-filter-flowchart
npm install --save hexo-filter-sequence
```

eg :


## 流程图

```flow
stOrder=>start: 下单请求
stPay=>start: 支付请求
eOrder=>end: 结束推送（取消订单）
e=>end: 结束推送
condorder=>condition: 对接系统下单是否成功？
condpay=>condition: 对接系统支付是否成功？

stOrder->condorder
condorder(yes)->stPay
condorder(no)->eOrder
stPay->condpay
condpay(yes)->e
condpay(no)->eOrder
```


## 时序图

```sequence

my->api: 下单请求
Note right of api: 对接系统下单
api-->my: 成功
my->api: 支付请求
Note right of api: 对接系统支付
api-->my: 成功
api->my: 出票请求
my-->api: 出票成功
Note left of my: 正常订单流程完成

```
