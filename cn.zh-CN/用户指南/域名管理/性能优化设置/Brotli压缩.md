# Brotli压缩 {#task_371714 .task}

本文档为您介绍了Brotli压缩功能及开通步骤。开启Brotli压缩功能，可以有效减少传输内容大小，加速分发效果。

Brotli是开源的一种新型压缩算法。开启该功能后，CDN节点返回请求的资源时，会对html、js、css等文本文件进行Brotli压缩。在文本文件资源下载方面会比Gzip性能提升约15~25%。当您需要对静态文本文件进行优化压缩，可以开启此功能。

-   当客户端的请求携带请求头`Accept-Encoding: br`时表示客户端希望获取对应资源时进行Brotli压缩。
-   服务端响应携带响应头`Conetnt-Encoding: br`时表示服务端响应的内容是brotli压缩的资源。

**说明：** 当Brotli压缩和Gzip压缩同时开启，且客户端`Accept-Encoding`请求头同时带`br`和`gzip`时，CDN节点将优先选择Brotli压缩。

1.  登录[CDN控制台](https://cdn.console.aliyun.com/overview)。
2.  在左侧导航栏，单击**域名管理**。
3.  在您需要设置的域名，单击**管理**。
4.  在左侧导航栏，单击**性能优化**。
5.  在Brotli压缩区域框中，打开开关。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301855/156014885148022_zh-CN.png)


