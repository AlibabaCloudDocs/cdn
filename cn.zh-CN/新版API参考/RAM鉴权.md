---
keyword: [鉴权, RAM]
---

# RAM鉴权

通过访问控制RAM（Resource Access Management）的RAM用户调用CDN API之前，您需要通过阿里云账号创建授权策略对RAM用户进行授权。在授权策略中使用资源描述符ARN（Alibaba Cloud Resource Name）指定授权资源。本文介绍可授权的CDN资源类型和API。

默认情况下，阿里云账号或RAM用户均能使用CDN控制台或CDN API完整操作自己创建的CDN资源。在以下场景中，会涉及到操作授权问题：

-   RAM用户刚创建，没有权限操作阿里云账号的资源。
-   操作具有权限控制的CDN资源前，需要资源拥有者授权目标资源和目标API行为权限。

当其他账号通过CDN API访问阿里云账号的资源时，阿里云CDN首先向RAM发起权限检查，以确保资源拥有者已经将相关权限授予调用者。不同的CDN API会根据涉及的资源以及API语义确定需要检查哪些资源的权限。实现授权策略和权限控制，请参见[访问控制产品文档](/cn.zh-CN/产品简介/什么是访问控制.md)和[API参考文档](/cn.zh-CN/API参考/API参考（RAM）/API概览.md)。

了解CDN的RAM用户如何使用，请参见[CDN子账户使用指南](/cn.zh-CN/服务管理/RAM用户权限管理/CDN子账户使用指南.md)。

了解通过RAM为CDN创建自定义授权策略，请参见[通过RAM对CDN进行权限管理](/cn.zh-CN/教程/通过RAM对CDN进行权限管理.md)。

了解如何通过RAM为RAM用户授予刷新预热功能的权限，请参见[授予RAM用户刷新预热权限](/cn.zh-CN/服务管理/RAM用户权限管理/授予RAM用户刷新预热权限.md)。

## 可授权的CDN资源类型

目前，可以在RAM中进行授权的资源类型及描述方式如下表所示。

**说明：** 下表中的$accountid为阿里云账号的账号ID，可以用星号（\*）表示。

|资源类型|授权策略中的资源描述方式|说明|
|:---|:-----------|:-|
|service|acs:cdn:\*:$accountid:\*|授权RAM用户管理CDN服务，例如变配、查询账号信息等。|
|domain|acs:cdn:\*:$accountid:domain/$domainName|授权RAM用户管理自己的加速域名，例如添加、配置、查询域名等。 $domainName表示对指定域名或泛域名（例如\*.aliyun.com）提供授权。

末尾的星号（\*）表示对所有域名提供授权。 |
|acs:cdn:\*:$accountid:domain/\*|

## 可授权的CDN API

每个API的资源描述如下表所示。

|API|资源描述|
|:--|:---|
|OpenCdnService|acs:cdn:\*:$accountid:\*|
|DescribeCdnService|acs:cdn:\*:$accountid:\*|
|ModifyCdnService|acs:cdn:\*:$accountid:\*|
|DescribeUserDomains|acs:cdn:\*:$accountid:domain/\*|
|DescribeCdnDomainDetail|acs:cdn:\*:$accountid:domain/$domainName|
|AddCdnDomain|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|StartCdnDomain|acs:cdn:\*:$accountid:domain/$domainName|
|StopCdnDomain|acs:cdn:\*:$accountid:domain/$domainName|
|DeleteCdnDomain|acs:cdn:\*:$accountid:domain/$domainName|
|RefreshObjectCaches|acs:cdn:\*:$accountid:domain/$domainName|
|PushObjectCache|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeRefreshTasks|acs:cdn:\*:$accountid:domain/\*|
|DescribeRefreshQuota|acs:cdn:\*:$accountid:domain/\*|
|ForbidLiveStream|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainBpsData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainSrcBpsData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainHitRateData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainQpsData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainHttpCodeData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainsUsageByDay|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeTopDomainsByFlow|acs:cdn:\*:$accountid:domain/\*|
|DescribeDomainPvData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainUvData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainRegionData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainISPData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainTopUrlVisit|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainFileSizeProportionData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeCdnDomainLogs|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeIpInfo|acs:cdn:\*:$accountid:domain/\*|

