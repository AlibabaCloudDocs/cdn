# CDN API鉴权规则 {#reference_q24_cpf_vdb .reference}

## **借助 RAM 实现子账号对主账号的 CDN 资源访问** {#section_kgk_hpf_vdb .section}

-   通过云帐号开通 CDN 服务，创建加速域名，所有服务和加速域名都是该帐号自己拥有的资源。默认情况下，帐号对自己的资源拥有完整的操作权限。
-   使用阿里云的访问控制RAM（Resource Access Management）服务，您可以将您云账号下 CDN 资源的访问及管理权限授予RAM中子用户。
-   在了解如何使用 RAM 来授权和访问 CDN 资源之前，请确保您已详细阅读了 [RAM 产品文档](../../../../cn.zh-CN/产品简介/什么是RAM.md#) 和 [API 文档](../../../../cn.zh-CN/API参考（RAM）/（隐藏）旧版 API 参考（RAM）/简介/RAM 简介.md#)。
-   如果您不需要使用RAM，请略过此章节。

## **RAM 中可授权的 CDN 资源类型** {#section_pqv_ypf_vdb .section}

目前，可以在 RAM 中进行授权的资源类型及描述方式如下表所示：

|资源类型|授权策略中的资源描述方式|说明|
|:---|:-----------|:-|
|service|acs:cdn:\*:$accountid:\*|授权子账户管理 CDN服务例如：变配，查询账户信息等|
|domain|acs:cdn:\*:$accountid:domain/$domainNameacs:cdn:\*:$accountid:domain/\*|授权子账户管理自己的加速域名例如：添加，配置，查询域名等|

## **CDN API 发生子账号访问主账号资源时的鉴权规则** {#section_d22_cqf_vdb .section}

当子账号通过 CDN Open API 对主账号的 CDN 资源进行访问时，CDN 后台向 RAM 进行权限检查，以确保资源拥有者的确将相关资源的相关权限授予了调用者。

每个不同的 CDN API 会根据涉及到的资源以及 API 的语义来确定需要检查哪些资源的权限。具体每个 API 的鉴权规则见下表：

|API|鉴权规则|
|:--|:---|
|OpenCdnService|acs:cdn::$accountid:|
|DescribeCdnService|acs:cdn::$accountid:|
|ModifyCdnService|acs:cdn::$accountid:|
|DescribeUserDomains|acs:cdn::$accountid:domain/|
|DescribeCdnDomainDetail|acs:cdn:\*:$accountid:domain/$domainName|
|AddCdnDomain|acs:cdn::$accountid:domain/|
|StartCdnDomain|acs:cdn:\*:$accountid:domain/$domainName|
|StopCdnDomain|acs:cdn:\*:$accountid:domain/$domainName|
|DeleteCdnDomain|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainConfigs|acs:cdn:\*:$accountid:domain/$domainName|
|SetOptimizeConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetPageCompressConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetIgnoreQueryStringConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetRangeConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetVideoSeekConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetSourceHostConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetErrorPageConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetForceRedirectConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetRefererConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetFileCacheExpiredConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetPathCacheExpiredConfig|acs:cdn:\*:$accountid:domain/$domainName|
|ModifyFileCacheExpiredConfig|acs:cdn:\*:$accountid:domain/$domainName|
|ModifyPathCacheExpiredConfig|acs:cdn:\*:$accountid:domain/$domainName|
|DeleteCacheExpiredConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetReqAuthConfig|acs:cdn:\*:$accountid:domain/$domainName|
|SetHttpHeaderConfig|acs:cdn:\*:$accountid:domain/$domainName|
|ModifyHttpHeaderConfig|acs:cdn:\*:$accountid:domain/$domainName|
|DeleteHttpHeaderConfig|acs:cdn:\*:$accountid:domain/$domainName|
|RefreshObjectCaches|acs:cdn::$accountid:domain/|
|PushObjectCache|acs:cdn::$accountid:domain/|
|DescribeRefreshTasks|acs:cdn::$accountid:domain/|
|DescribeRefreshQuota|acs:cdn::$accountid:domain/|
|DescribeLiveStreamsPublishList|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeLiveStreamsOnlineList|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeLiveStreamsBlockList|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeLiveStreamsControlHistory|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeLiveStreamOnlineUserNum|acs:cdn:\*:$accountid:domain/$domainName|
|ForbidLiveStream|acs:cdn:\*:$accountid:domain/$domainName|
|ResumeLiveStream|acs:cdn:\*:$accountid:domain/$domainName|
|SetLiveStreamsNotifyUrlConfig|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainBpsData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainFlowData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainSrcBpsData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainSrcFlowData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainHitRateData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainQpsData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainHttpCodeData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainsUsageByDay|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeTopDomainsByFlow|acs:cdn::$accountid:domain/|
|DescribeDomainPvData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainUvData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainRegionData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainISPData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainTopUrlVisit|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainTopReferVisitl|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainFileSizeProportionData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainCCData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainWafData|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeCdnDomainLogs|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeIpInfo|acs:cdn::$accountid:domain/|

