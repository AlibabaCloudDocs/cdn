---
keyword: [Brotli压缩, 性能优化]
---

# Brotli压缩

Brotli是开源的一种新型压缩算法，开启Brotli压缩功能，CDN节点向您返回请求的资源时，会对文本文件进行Brotli压缩，可以有效缩小传输文件的大小，提升文件传输效率，减少带宽消耗。

当源站文件的大小超过1024 B时，您可以使用智能压缩或Brotli压缩来压缩文件，有效缩小传输文件的大小，提升文件传输效率，Brotli压缩比Gzip压缩性能更好，性能提升约15%~25%。

-   Brotli压缩支持的文件类型有text/xml、text/plain、text/css、application/javascript、application/x-javascript、application/rss+xml、text/javascript、image/tiff、image/svg+xml、application/json、application/xml。
-   客户端请求携带请求头`Accept-Encoding: br`：客户端希望获取对应资源时进行Brotli压缩。
-   服务端响应携带响应头`Content-Encoding: br`：服务端响应的内容是经过Brotli压缩后的资源。

## 注意事项

-   源站文件配置了MD5校验机制，请不要开启智能压缩功能。

    开启智能压缩功能，CDN对静态文件进行压缩时，会改变文件的MD5值，导致压缩后文件的MD5值和源站文件的MD5值不一致。

-   源站开启了压缩功能，且服务端响应中携带了`content_encoding`，则CDN的压缩功能将不再生效。
-   同时开启Brotli压缩和Gzip压缩，且客户端请求头`Accept-Encoding`同时携带`br`和`gzip`时，只有Brotli压缩生效。
-   如果您同时开启了页面优化和压缩功能（智能压缩或者Brotli压缩），页面优化功能将会失效，CDN只会对文件进行压缩。
-   Gzip的浏览器兼容性高于Brotli，Gzip基本兼容所有浏览器，Brotli只兼容部分浏览器，单击[浏览器兼容](https://caniuse.com)查询网站，查询浏览器的兼容情况。

## 操作步骤

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**性能优化**。

5.  在**Brotli压缩**区域框中，打开**Brotli压缩**开关，完成配置。

    成功开启Brotli压缩功能后，您可以对比原始文件大小和压缩后的文件大小，压缩后的文件大小变小了，说明文件已经被压缩了。


## 相关API

[BatchSetCdnDomainConfig](/intl.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)

