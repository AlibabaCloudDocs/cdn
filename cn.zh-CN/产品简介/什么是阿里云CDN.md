# 什么是阿里云CDN {#concept_aml_tlg_tdb .concept}

阿里云内容分发网络（Content Delivery Network，简称CDN）是建立并覆盖在承载网之上，由分布在不同区域的边缘节点服务器群组成的分布式网络。阿里云CDN为您分担源站压力，避免网络拥塞，确保在不同区域、不同场景下加速您网站内容的分发，提高访问资源速度。

阿里云CDN将您源站资源缓存至阿里云遍布全球的加速节点上，当终端用户请求访问和获取这些资源时，无需回源，系统将就近调用CDN节点上已经缓存的资源。您可以参考[快速入门](../../../../cn.zh-CN/快速入门/快速入门.md#)快速接入阿里云CDN。

目前，CDN部分节点已支持IPv6进行访问。

## 工作原理 {#section_qry_wz2_h2b .section}

通过以下案例，您可以清楚地了解CDN的工作原理。

假设您的源站域名为`www.a.com`。接入CDN开始使用加速服务后，当您的终端用户（北京）发起 HTTP 请求时，实际的处理流程如下：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5098/15585148394886_zh-CN.png)

1.  终端用户（北京）向`www.a.com`下的某资源发起请求，会先向LDNS发起域名解析请求。
2.  LDNS检查缓存中是否有www.a.com的ip记录，如果有则直接返回给终端。如果没有则向授权DNS查询。
3.  当授权DNS解析`www.a.com`时，会发现已经配置了CNAME `www.a.tbcdn.com`。
4.  解析请求会发送至阿里云DNS调度系统，并为请求分配最佳节点 IP。
5.  LDNS获取DNS返回的解析IP。
6.  用户获取解析IP。
7.  用户向获取的IP发起对该资源的访问请求。
    -   若该IP对应的节点已缓存该资源，则会将数据直接返回给用户（如图中步骤7、8），此时请求结束。
    -   若该IP对应的节点未缓存该资源，则节点会向业务源站发起对该资源的请求。获取资源后，结合用户自定义配置的缓存策略（详情请参见[缓存配置](../../../../cn.zh-CN/用户指南/域名管理/节点缓存设置/缓存配置.md#)），将资源缓存至节点（图中的北京节点），并返回给用户，此时请求结束。

## 使用CDN {#section_i4g_cnf_l2b .section}

您可以查看[CDN名词解释](cn.zh-CN/产品简介/名词解释.md#)，了解阿里云CDN的基本概念。

您可以查看[CDN学习路径](https://help.aliyun.com/learn/learningpath/cdn.html)，快速了解并上手CDN。

您可以登录[CDN控制台](https://cdnnext.console.aliyun.com)，了解并使用了CDN的[全部功能](../../../../cn.zh-CN/用户指南/CDN功能列表.md#)。

您还可以使用CDN的[API](../../../../cn.zh-CN/新版API参考/简介.md#)，更灵活地帮助您的业务。

## CDN定价 {#section_c3q_dnf_l2b .section}

CDN的计费方式包括[基础服务计费](../../../../cn.zh-CN/产品定价/计费方式/基础服务计费.md#)和[增值服务计费](../../../../cn.zh-CN/产品定价/计费方式/增值服务计费.md#)。其中，基础服务可以按流量或峰值带宽计费。关于CDN的具体计费价格请参见[CDN详细价格信息](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail)。

## 相关服务 {#section_xzx_yyb_n2b .section}

**CDN子产品**

您可以使用[全站加速](../../../../cn.zh-CN/产品简介/什么是全站加速.md#)区分动静态资源，并实现动静态资源分别加速。

您可以使用[安全加速SCDN](https://help.aliyun.com/product/63560.html)兼顾加速与安全两个业务目标。

您可以使用[PCDN](https://help.aliyun.com/product/54287.html)显著降低分发成本，并应用在视频点播、直播、大文件下载等业务场景。

**相关产品**

您可以在[对象存储OSS](../../../../cn.zh-CN/产品简介/什么是对象存储 OSS.md#)中使用CDN加速，提高网站访问速度，有效降低OSS的外网流量费用。

您可以在[视频直播](https://help.aliyun.com/product/29949.html)中应用CDN，实现媒资存储、切片转码、访问鉴权、内容分发加速一体化解决方案。

您可以在[视频点播](https://help.aliyun.com/product/29932.html)中应用CDN，减少缓冲时间，实现高流畅度的播放体验。

您可以借助[阿里云云解析](https://help.aliyun.com/product/29697.html)提供的强大稳定的解析调度入口，确保顺畅的访问体验。

您可以借助[云服务器ECS](../../../../cn.zh-CN/产品简介/什么是云服务器ECS.md#)提高网站可用性，保护服务器源站信息，降低带宽使用成本。

您可以将[负载均衡](../../../../cn.zh-CN/产品简介/什么是负载均衡.md#)服务器的IP地址设置为回源地址，降低回源带宽压力。

