# 什么是阿里云CDN {#concept_aml_tlg_tdb .concept}

阿里云内容分发网络（Content Delivery Network，简称CDN）是建立并覆盖在承载网之上，由分布在不同区域的边缘节点服务器群组成的分布式网络。阿里云CDN分担源站压力，避免网络拥塞，确保在不同区域、不同场景下加速网站内容的分发，提高资源访问速度。

阿里云CDN将源站资源缓存至阿里云遍布全球的加速节点上，当终端用户请求访问和获取该资源时，无需回源，系统自动调用离终端用户最近的CDN节点上已缓存的资源。接入阿里云CDN的方法，请参考[快速入门](../../../../cn.zh-CN/快速入门/快速入门.md#)。

目前，CDN部分节点已支持IPv6进行访问。

## CDN使用 {#section_i4g_cnf_l2b .section}

-   您可以查看[CDN基本概念](cn.zh-CN/产品简介/名词解释.md#)，了解阿里云CDN的基本概念。
-   您可以查看[CDN工作原理](ZH-CN_TP_545056_V1.dita#concept_678821)，了解阿里云CDN的工作原理。
-   您可以查看[CDN学习路径](https://help.aliyun.com/learn/learningpath/cdn.html)，快速了解并使用CDN。
-   您可以使用CDN的[API](../../../../cn.zh-CN/新版API参考/简介.md#)，对CDN服务进行相关操作。

## CDN定价 {#section_c3q_dnf_l2b .section}

CDN的计费方式包括[基础服务计费](../../../../cn.zh-CN/产品定价/计费方式/基础服务计费.md#)和[增值服务计费](../../../../cn.zh-CN/产品定价/计费方式/增值服务计费.md#)。其中，基础服务可以按流量或峰值带宽计费。

关于CDN的具体计费价格请参见[CDN详细价格信息](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail)。

## 相关服务 {#section_xzx_yyb_n2b .section}

**CDN子产品**

-   您可以使用[全站加速](../../../../cn.zh-CN/产品简介/什么是全站加速.md#)区分动静态资源，并实现动静态资源分别加速。
-   您可以使用[安全加速SCDN](https://help.aliyun.com/product/63560.html)兼顾加速与安全两个业务目标。
-   您可以使用[PCDN](https://help.aliyun.com/product/54287.html)显著降低分发成本，并应用在视频点播、直播、大文件下载等业务场景。

相关产品

-   您可以在[对象存储OSS](../../../../cn.zh-CN/产品简介/什么是对象存储 OSS.md#)中使用CDN加速，提高网站访问速度，有效降低OSS的外网流量费用。
-   您可以在[视频直播](https://help.aliyun.com/product/29949.html)中应用CDN，实现媒资存储、切片转码、访问鉴权、内容分发加速一体化解决方案。
-   您可以在[视频点播](https://help.aliyun.com/product/29932.html)中应用CDN，减少缓冲时间，实现高流畅度的播放体验。
-   您可以借助[阿里云云解析](https://help.aliyun.com/product/29697.html)提供的强大稳定的解析调度入口，确保顺畅的访问体验。
-   您可以借助[云服务器ECS](../../../../cn.zh-CN/产品简介/什么是云服务器ECS.md#)提高网站可用性，保护服务器源站信息，降低带宽使用成本。
-   您可以将[负载均衡](../../../../cn.zh-CN/产品简介/什么是负载均衡.md#)服务器的IP地址设置为回源地址，降低回源带宽压力。

