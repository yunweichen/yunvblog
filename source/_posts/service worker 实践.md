---
title: service worker 实践
date: 2019-04-04 14:37:04
tags:
 - 博客
---

### 参考文档

More info: [godbmw.com](https://godbmw.com/passages/2019-04-02-pwa-service-worker/)
More info: [zhangxinxu.com](https://www.zhangxinxu.com/wordpress/2017/07/service-worker-cachestorage-offline-develop/)

### 遇到的问题

```
The path of the provided scope ('/') is not under the max scope allowed ('/j
```

说的是本缓存的js文件存放的位置，不是主目录的话就要按规定设置的意思吧


#### 相关解决方案
More info: [stackoverflow.com](https://stackoverflow.com/questions/49084718/how-exactly-add-service-worker-allowed-to-register-service-worker-scope-in-upp/)
More info: [stackoverflow.com](https://stackoverflow.com/questions/35780397/understanding-service-worker-scope/)
