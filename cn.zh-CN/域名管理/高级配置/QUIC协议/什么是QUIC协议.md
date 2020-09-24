# 什么是QUIC协议

如果客户端和CDN节点之间的链路使用QUIC协议，则可以保障数据传输的安全性，同时提升资源的访问效率。通过本文您可以了解QUIC协议的概念、工作原理、对客户端要求和计费规则。

## 什么是QUIC？

QUIC（Quick UDP Internet Connections）是一种实验性传输层网络协议，提供与TLS/SSL相当的安全性，同时具有更低的连接和传输延迟。QUIC基于UDP，因此拥有极佳的弱网性能，在丢包和网络延迟严重的情况下仍可提供可用的服务。QUIC在应用程序层面就能实现不同的拥塞控制算法，不需要操作系统和内核支持，这相比于传统的TCP协议，拥有了更好的改造灵活性，非常适合在TCP协议优化遇到瓶颈的业务。

目前，阿里云CDN开放使用的是七层协议的QUIC（HTTP over QUIC），版本号为Q46。

## 工作原理

在阿里云CDN中使用QUIC的工作原理如下图所示。

![原理图](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/7490246851/p54879.png)

## 对客户端的要求

QUIC协议对客户端的要求如下：

-   如果您使用Chrome浏览器，当前阿里云CDN支持的QUIC协议是Q46版本，Chrome支持直接对阿里云CDN发起QUIC请求。
-   如果您使用自研App，则App必须集成支持QUIC协议的网络库，例如：lsquic-client或cronet网络库。

## QUIC计费规则

QUIC协议属于增值服务，会对QUIC请求数进行额外计费，详情请参见[CDN 详细价格信息](https://www.aliyun.com/price/product?spm=5176.175459.915900.btn2.3749312f2FsBxF#/cdn/detail)的QUIC部分。

**说明：** 一个协议头为HTTPS的QUIC协议请求，不会同时收取HTTPS请求数和QUIC请求数两笔费用。因为各个请求数的计费互斥，一个请求仅会被收取一种请求数费用。

QUIC协议请求统计规则如下。

-   QUIC协议的请求不区分请求头，而是判断请求是否基于UDP协议。
-   CDN优先判断是否为QUIC协议请求，如果是，则对其进行QUIC请求数计费，不再匹配是否为HTTPS请求；如果不是，则会匹配HTTPS请求。

## 使用QUIC

QUIC第一轮内测已经于2020年6月结束，目前暂不支持新用户接入，敬请期待下一轮内测。

