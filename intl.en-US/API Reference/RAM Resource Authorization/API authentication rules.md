# API authentication rules {#reference_q24_cpf_vdb .reference}

## **Use RAM to give a subaccount access to its primary account’s CDN resources.** {#section_kgk_hpf_vdb .section}

-   When an Alibaba Cloud account activates the CDN service and creates CDN domains, all services and CDN domains are held as resources of this account. By default, accounts have full operation permissions on their resources.
-   Alibaba Cloud Resource Access Management \(RAM\) allows you to grant RAM sub-users the permission to access and manage the resources under your Alibaba Cloud account.
-   Make sure that you have read the [RAM product documentation](../../../../intl.en-US/Product Introduction/What is RAM?.md#) and [API documentation](../../../../intl.en-US/API Reference/(Old Version) API Reference (RAM)/Introduction/RAM introduction.md#) carefully before learning how to use RAM to grant access to CDN resources.
-   If you do not need RAM, skip this section.

## **CDN authorizable resource type in RAM** {#section_pqv_ypf_vdb .section}

Currently, authorizable resource type and description methods in RAM are set out as following table:

|Resource type|Resource descriptions in authorization policy|Description|
|:------------|:--------------------------------------------|:----------|
|service|acs:cdn:\*:$accountid:\*|Authorizes subaccounts to manage CDN services,such as changing configuration and querying account information.|
|domain|acs:cdn:\*:$accountid:domain/$domainNameacs:cdn:\*:$accountid:domain/\*|Authorizes subaccounts to manage their own CDN domains,such as adding, configuring, and querying domain names.|

## **CDN API authentication rules when a subaccount requests access to resources of primary CDN account** {#section_d22_cqf_vdb .section}

When a subaccount requests access to resources of primary CDN account through CDN Open APIs, CDN backend sends one corresponding request to RAM to check authority granting, in order to ensure that the resource owner grants the caller access right to relevant resources.

Each different CDN API determines authority of relevant resources according to the involved resources and the semantics of the API. Authentication rules for each API are listed as follows:

|API|Authentication rules|
|:--|:-------------------|
|OpenCdnService|acs:cdn:\*:$accountid:\*|
|Describecdnservice|acs:cdn:\*:$accountid:\*|
|ModifyCdnService|acs:cdn:\*:$accountid:\*|
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
|Deletehttpheaderconfig|acs:cdn:\*:$accountid:domain/$domainName|
|RefreshObjectCaches|acs:cdn::$accountid:domain/|
|PushObjectCache|acs:cdn::$accountid:domain/|
|DescribeRefreshTasks|acs:cdn::$accountid:domain/|
|DescribeRefreshQuota|acs:cdn::$accountid:domain/|
|DescribeLiveStreamsPublishList|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeLiveStreamsOnlineList|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeLiveStreamsBlockList|ACS: CDN: \*: $ accounts: domain/$ domainname|
|DescribeLiveStreamsControlHistory|acs:cdn:\*:$accountid:domain/$domainName|
|Describelivestreamonlineusernum|acs:cdn:\*:$accountid:domain/$domainName|
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
|Describecdndomainlogs|acs:cdn::$accountid:domain/ acs:cdn:\*:$accountid:domain/$domainName|
|DescribeIpInfo|acs:cdn::$accountid:domain/|

