# 配置回源SNI {#task_261642 .task}

如果您的源站IP绑定了多个域名，当CDN节点以HTTPS协议访问您的源站时，您可以设置回源SNI，指明具体访问域名。

服务器名称指示 Server Name Indication（SNI）是一个扩展的传输层安全性协议 Transport Layer Security（TLS）。在该协议下，握手过程开始时，客户端会告诉它正在连接的那台服务器即将要连接的主机名称，以允许该服务器在相同的IP地址和TCP端口号上呈现多个证书，即一台服务器可以为多个域名提供服务。因此，同一个IP地址上提供的多个安全的HTTPS网站（或其他任何基于TLS的服务），不需要使用相同的证书。

如果您的源站服务器使用单个IP提供多个域名的HTTPS服务，且您已经为CDN设置了443端口回源（CDN节点以HTTPS协议访问您的服务器），您就需要设置回源SNI，指明所请求的具体域名。这样CDN节点以HTTPS协议回源访问您的服务器时，服务器才会正确地返回对应的证书。

**说明：** 如果您的源站是阿里云OSS，则无需设置回源SNI。

回源SNI的工作原理如下图所示。

![SNI工作原理](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/156653074040953_zh-CN.png)

1.  CDN节点以HTTPS协议访问源站时，在SNI中指定访问的域名。
2.  源站接收到请求后，根据SNI中记录的域名，返回对应域名的证书。
3.  CDN节点收到证书，与服务器端建立安全连接。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理页面，单击目标域名对应的**管理**。
4.  在指定域名的左侧导航栏，单击**回源配置**。
5.  在**回源SNI**区域，单击**修改配置**。 

    ![回源SNI](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/156653074040954_zh-CN.png)

6.  打开**回源SNI开关**，根据所需输入服务器源站提供服务的域名。
7.  单击**确定**。

