# 配置OCSP Stapling

OCSP Stapling功能是由CDN服务器查询OCSP（Online Certificate Status Protocol）信息，可以降低客户端验证请求延迟，减少等待查询结果的响应时间。通过本文，您可以了解OCSP Stapling功能的使用场景和控制台开启该功能的操作步骤。

使用OCSP Stapling功能需要客户端支持OCSP扩展字段，客户端不支持，则无法生效。

OCSP信息是由数字证书颁发机构CA（Certificate Authority）提供，用于在线实时验证证书的合法性和有效性。

用户痛点：客户端（浏览器）根据证书中的OCSP信息，将查询请求发送到CA的验证地址，检查此证书是否合法、有效。在网络状况不佳的情况下，客户端在等待获取查询结果时，会造成长时间的页面空白，阻塞您终端用户的后续操作。

![OCSP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1532717161/p99426.png)

解决方案：OCSP Stapling功能将查询OCSP信息的工作由CDN服务器完成。CDN通过低频次查询，将查询结果缓存到服务器中（默认缓存时间60分钟）。当客户端向服务器发起TLS握手请求时，CDN服务器将证书的OCSP信息和证书链一起发送到客户端。这样可以避免客户端验证会产生的阻塞问题。由于OCSP信息是无法伪造的，因此这一过程不会产生额外的安全问题。

![OCSP Stapling](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8615817161/p99427.png)

**说明：** OCSP Stapling缓存在某个节点时间过期后，该节点发起的第一个请求不生效。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**HTTPS配置**。

5.  在**OCSP Stapling**区域，打开**开关**。

    ![OCSP Stapling](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3347747061/p99429.png)


