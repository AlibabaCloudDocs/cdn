# Brotli压缩 {#task_371714 .task}

当您需要对静态文本文件进行压缩时，可以开启此功能，有效减小传输内容大小，加速分发效果。本文为您详细介绍开启Brotli压缩功能的方法。

Brotli是开源的一种新型压缩算法。开启Brotli压缩功能后，CDN节点返回请求资源时，会对html、js、css等文本文件进行Brotli压缩。压缩文本文件时，Brotli压缩比智能压缩性能提升约15~25%。

-   当客户端的请求携带请求头`Accept-Encoding: br`时，表示客户端希望获取对应资源时进行Brotli压缩。
-   当服务端响应携带响应头`Content-Encoding: br`时，表示服务端响应的内容是Brotli压缩的资源。

**说明：** 当Brotli压缩和Gzip压缩同时开启时，客户端请求头`Accept-Encoding`同时带`br`和`gzip`时，CDN节点将优先选择Brotli压缩。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理页面，单击目标域名对应的**管理**。
4.  在指定域名的左侧导航栏，单击**性能优化**。
5.  在Brotli压缩区域框中，打开Brotli压缩开关。 

    ![Brotli压缩](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301855/156414089948022_zh-CN.png)


