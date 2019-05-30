# 设置TLS {#task_261642 .task}

为了保障您互联网通信的安全性和数据完整性，阿里云CDN提供TLS版本控制功能。您可以根据不同域名的需求，灵活地配置TLS协议版本。

开启TLS功能前，您需要确保已成功[配置HTTPS证书](intl.zh-CN/用户指南/域名管理/HTTPS安全加速/HTTPS安全加速设置.md#)。

TLS（Transport Layer Security）即安全传输层协议，在两个通信应用程序之间提供保密性和数据完整性。最典型的应用就是HTTPS。HTTPS，即HTTP over TLS，就是安全的HTTP，运行在HTTP层之下，TCP层之上，为HTTP层提供数据加解密服务。

目前，TLS主要有4个版本：

-   TLSv1.0：RFC2246，1999年发布，基于SSLv3.0，该版本易受各种攻击（如BEAST和POODLE），除此之外，支持较弱加密，对当今网络连接的安全已失去应有的保护效力。不符合PCI DSS合规判定标准。支持的主流浏览器： IE6+、Chrome 1+、Firefox 2+。
-   TLSv1.1：RFC4346，2006年发布，修复TLSv1.0若干漏洞。支持的主流浏览器：IE11+、Chrome22+、Firefox24+、Safri7+。
-   TLSv1.2：RFC5246，2008年发布，目前广泛使用的版本。支持的主流浏览器：IE11+、Chrome30+、Firefox27+、Safri7+。
-   TLSv1.3：RFC8446，2018年发布，最新的TLS版本，支持0-RTT模式（更快），只支持完全前向安全性密钥交换算法（更安全）。支持的主流浏览器：Chrome 70+和Firefox 63+。

1.  登录[CDN控制台](https://cdn.console.aliyun.com/)。
2.  单击**域名管理**。
3.  单击目标域名后的**管理**。
4.  单击**HTTPS配置**。
5.  在**TLS版本控制**区域框，根据您的需要，开启或关闭对应的TLS版本。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41679/155918093947114_zh-CN.png)

    **说明：** 目前TLSv1.0、TLSv1.1和TLSv1.2版本默认开启。


