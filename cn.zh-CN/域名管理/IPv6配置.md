# IPv6配置

本文为您介绍了阿里云CDN IPv6功能在控制台的操作步骤，通过开启IPv6开关，IPv6的客户端请求将支持以IPv6协议访问CDN，CDN也将携带IPv6的客户端IP信息访问您的源站。

阿里云CDN大部分节点已经支持接收IPv6协议的请求，您可以在域名配置中开启IPv6开关。

开启开关后，当您的用户处于IPv6环境，且就近的CDN节点也支持IPv6的请求时，客户端可以通过IPv6协议访问CDN节点。当用户就近区域的CDN节点不支持IPv6协议时，客户端仍可以IPv4协议访问CDN节点。

**说明：** 目前海外、中国香港、中国澳门和中国台湾节点不支持IPv6配置。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  单击**IPv6配置**。

5.  打开**IPv6开关**。

    IPv6功能开启，您可以在客户端通过IPv6协议访问CDN节点，阿里云CDN节点也将携带IPv6协议信息访问您的源站。

    ![打开IPv6开关](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9766080261/p59015.png)


