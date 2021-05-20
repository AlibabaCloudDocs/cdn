---
keyword: [回源SNI, CDN, 源站]
---

# 配置回源SNI

如果您的源站IP绑定了多个域名，当CDN节点以HTTPS协议访问您的源站时，您可以设置回源SNI，指明具体需要访问的域名。

服务器名称指示SNI（Server Name Indication）是一个扩展的传输层安全性协议TLS（Transport Layer Security）。当该协议下的握手过程开始时，客户端会返回正在连接的那台服务器即将要连接的主机名称，以允许该服务器在相同的IP地址和TCP端口号上呈现多个证书，即一台服务器可以为多个域名提供服务。因此，同一个IP地址上提供的多个安全的HTTPS网站或其他任何基于TLS的服务，不需要使用相同的证书。

如果您的源站服务器使用单个IP提供多个域名的HTTPS服务，且已经为CDN设置了以HTTPS协议访问您的服务器，您需要设置回源SNI，指明所请求的具体域名。当CDN节点以HTTPS协议回源访问您的服务器时，服务器才会正确地返回对应的证书。

**说明：** 如果您的源站是阿里云OSS，则无需设置回源SNI。

回源SNI的工作原理如下图所示。

![SNI工作原理](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5272649951/p40953.png)

回源SNI的工作流程如下：

1.  当CDN节点以HTTPS协议访问源站时，需要在SNI中指定访问的域名。
2.  源站接收到请求后，根据SNI中记录的域名，返回对应域名的证书。
3.  CDN节点收到证书，与服务器端建立安全连接。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**回源配置**。

5.  在**配置**页签下找到**回源SNI**，单击**修改配置**。

6.  在**回源SNI**对话框，打开**回源SNI开关**，输入服务器源站提供服务的域名。

    **说明：**

    -   SNI在阿里云CDN产品中指源站域名。如果您的源站服务器使用单个IP地址提供多个域名的HTTPS服务，则需要设置回源SNI，指明所请求的具体域名，例如cdn.console.aliyun.com。
    -   目前回源SNI只支持配置精确域名，不支持配置为泛域名。
    -   在加速域名为泛域名，且回源协议为HTTPS协议的情况下，您可以将需要获取资源的域名配置到回源SNI，也可以[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)申请后台配置。
    ![回源SNI](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8334575061/p40954.png)

7.  单击**确定**，完成配置。


**相关文档**  


[批量配置域名](/cn.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)

