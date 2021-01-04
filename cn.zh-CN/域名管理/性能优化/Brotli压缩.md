---
keyword: [Brotli压缩, 性能优化]
---

# Brotli压缩

当您需要对静态文本文件进行压缩时，可以开启此功能，有效减小传输内容大小，加速分发效果。本文为您详细介绍开启Brotli压缩功能的方法。

Brotli是开源的一种新型压缩算法。开启Brotli压缩功能后，CDN节点返回请求资源时，会对HTML、JS、CSS等文本文件进行Brotli压缩。压缩文本文件时Brotli压缩比Gzip压缩性能提升约15%~25%。

-   客户端请求携带请求头`Accept-Encoding: br`：客户端希望获取对应资源时进行Brotli压缩。
-   服务端响应携带响应头`Content-Encoding: br`：服务端响应的内容是Brotli压缩的资源。

**说明：**

-   当Brotli压缩和Gzip压缩同时开启时，且客户端请求头`Accept-Encoding`同时带`br`和`gzip`时，CDN节点将优先选择Brotli压缩。
-   如果源站已经开启压缩功能，并且响应中携带`content_encoding`，则无法开启Brotli压缩功能。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**性能优化**。

5.  在**Brotli压缩**区域，打开**Brotli压缩**开关。


