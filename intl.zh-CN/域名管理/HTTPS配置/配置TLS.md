# 配置TLS {#task_261642 .task}

为了保障您互联网通信的安全性和数据完整性，阿里云CDN提供TLS版本控制功能。您可以根据不同域名的需求，灵活地配置TLS协议版本。通过本文档，您可以了解配置TLS协议的操作方法。

执行该操作前，请您确保已成功配置HTTPS证书，操作方法请参见[配置HTTPS证书](intl.zh-CN/域名管理/HTTPS配置/配置HTTPS证书.md#)。

TLS（Transport Layer Security）即安全传输层协议，在两个通信应用程序之间提供保密性和数据完整性。最典型的应用就是HTTPS。HTTPS，即HTTP over TLS，就是安全的HTTP，运行在HTTP层之下，TCP层之上，为HTTP层提供数据加解密服务。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理页面，单击目标域名对应的**管理**。
4.  在**TLS版本控制**区域，根据所需开启或关闭对应的TLS版本。 

    TLS协议说明如下表所示。

    |协议|说明|支持的主流浏览器|
    |--|--|--------|
    |TLSv1.0|RFC2246，1999年发布，基于SSLv3.0，该版本易受各种攻击（如BEAST和POODLE），除此之外，支持较弱加密，对当今网络连接的安全已失去应有的保护效力。不符合PCI DSS合规判定标准。|     -   IE6+
    -   Chrome 1+
    -   Firefox 2+
 |
    |TLSv1.1|RFC4346，2006年发布，修复TLSv1.0若干漏洞。|     -   IE 11+
    -   Chrome 22+
    -   Firefox 24+
    -   Safri 7+
 |
    |TLSv1.2|RFC5246，2008年发布，目前广泛使用的版本。|     -   IE 11+
    -   Chrome 30+
    -   Firefox 27+
    -   Safri 7+
 |
    |TLSv1.3|RFC8446，2018年发布，最新的TLS版本，支持0-RTT模式（更快），只支持完全前向安全性密钥交换算法（更安全）。|     -   Chrome 70+
    -   Firefox 63+
 |

    ![TLS版本控制](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41679/156505457447114_zh-CN.png)

    **说明：** 目前TLSv1.0、TLSv1.1和TLSv1.2版本默认开启。


