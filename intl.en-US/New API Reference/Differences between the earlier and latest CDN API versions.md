---
keyword: [api, cdn]
---

# Differences between the earlier and latest CDN API versions

This topic describes the differences between the earlier and latest CDN API versions.

For more information, see [List of operations by function](/intl.en-US/New API Reference/List of operations by function.md).

**Note:** The earlier version \(2014-11-11\) of the Alibaba Cloud CDN API is no longer maintained. We recommend that you use the latest version of the Alibaba Cloud CDN API.

## Changes to the opertaions

|Operation name \(earlier version\)|Details of change|
|:---------------------------------|:----------------|
|DescribeDomainFlowData|Changed to DescribeDomainTrafficData.|
|-   DescribeDomainBpsData
-   DescribeDomainHitRateData
-   DescribeDomainHttpCodeData
-   DescribeDomainQpsData
-   DescribeDomainTrafficData

|-   The time format is changed from YYYY-MM-DDThh:mmZ to yyyy-MM-ddTHH:mm:ssZ.
-   The fixTimeGap and timeMerge parameters are removed.
-   The parameters that specify static and dynamic resources are removed. |
|AddCdnDomain|The following parameters are removed: -   SourceType
-   SourcePort
-   Priorities
-   Region |
|ModifyCdnDomain|-   The SourceType, SourcePort, and Priorities parameters are removed.
-   The format of the Sources parameter is changed to \[\{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80\}\] |
|DescribeCdnDomainDetail|-   The SourceType, Sources, SourcePort, and Region response parameters are removed.
-   Descriptions are added for the Description, Scope, and CertificateName response parameters. |
|DescribeDomainBpsData|-   The time range for data query is changed from the last 90 days to a custom time range within the last 90 days.
-   The DomainType request parameter is removed.
-   The description for the Interval request parameter is changed. In the earlier version, you can set the time range to 300, 3600, 14400, 28800, or 86400 seconds. If you do not set this parameter or the specified value is invalid, the default value 300 is used. In the latest version:
    -   Valid values are 300, 3600, and 86400.
    -   If you do not set the parameter or the specified value is invalid, the default value is used. For a time range that does not exceed 3 days, the default value is 300 seconds. For a time range that exceeds 3 days, the default value is 3600 seconds. For a time range that exceeds 30 days, the default value is 86400 seconds.
-   Descriptions are added for the LocationNameEn and IspNameEn response parameters.
-   The description for the SupplyBpsDatas response parameter is removed. |
|DescribeCdnDomainLogs|-   The time format is changed from YYYY-MM-DDThh:mmZ to yyyy-MM-ddTHH:mm:ssZ.
-   The LogDay request parameter is removed.
-   The response parameter format is adjusted. For more information, see [here](#no8). |
|DeleteSpecificConfig|The FunctionName parameter is removed.|
|DescribeDomainAverageResponseTime|The time format is changed from YYYY-MM-DDThh:mmZ to yyyy-MM-ddTHH:mm:ssZ.|
|DescribeUserDomains|-   The SourceType response parameter is removed.
-   The Sources request parameter is removed.
-   The format of the Sources response parameter is adjusted. |
|DescribeDomainRegionData|-   The time format is changed from YYYY-MM-DDThh:mmZ to yyyy-MM-ddTHH:mm:ssZ.
-   The maximum time range for data query is changed from the last 90 days to 90 days.
-   The ByteHitRate, ReqErrRate, and ReqHitRate response parameters are removed. |
|DescribeExtensiveDomainData|-   The time format is changed from YYYY-MM-DDThh:mmZ to yyyy-MM-ddTHH:mm:ssZ.
-   The ExtensiveDomain request parameter no longer checks the validity of the wildcard domain.
-   The limit of only data in the last 90 days can be queried is removed.
-   In the latest version, you must specify both the beginning and end of the time range to query. |
|DescribeDomainBpsDataByTimeStam|The time format is changed from YYYY-MM-DDThh:mmZ to yyyy-MM-ddTHH:mm:ssZ.|
|-   DescribeDomainFileSizeProportion
-   DescribeDomainPvData
-   DataDescribeDomainUvData

|-   The time format is changed from YYYY-MM-DDThh:mmZ to yyyy-MM-ddTHH:mm:ssZ.
-   The DomainName request parameter is changed from optional to required. |
|-   DescribeDomainMax95BpsData
-   DescribeDomainsUsageByDay
-   DescribeDomainReqHitRateData
-   DescribeTopDomainsByFlow

|-   The time format is changed from YYYY-MM-DDThh:mmZ to yyyy-MM-ddTHH:mm:ssZ.
-   The maximum time range for data query is changed from the last 90 days to 90 days. |
|-   DescribeDomainTopReferVisit
-   DescribeDomainTopUrlVisit

|The DomainName request parameter is changed from optional to required.|
|DescribeDomainHttpsData|-   The DomainType, TimeMerge, Cls, and FixTimeGap request parameters are removed.
-   The time format is changed from YYYY-MM-DDThh:mmZ to yyyy-MM-ddTHH:mm:ssZ.
-   The maximum time range for data query is changed from the last 90 days to 90 days.
-   The response parameters that specify static and dynamic resources are removed. |
|-   SetPageCompressConfig
-   SetIgnoreQueryStringConfig
-   SetVideoSeekConfig
-   SetOptimizeConfig
-   SetRemoveQueryStringConfig

|The parameter value is changed from On/Off to on/off.|
|SetFileCacheExpiredConfig|The Weight parameter is removed.|
|SetIpBlackListConfig|You can no longer leave parameters empty.|
|DeleteCacheExpiredConfig|The required parameter CacheType is removed.|

```
{
"RequestId": "1805F349-0A2B-41D9-B4AD-33632AFC27F1",
"DomainLogModel": {
"DomainName": "example.com",
"DomainLogDetails": {
"DomainLogDetail": [
{
"EndTime": "2015-05-23T04:00:00Z",
"LogName": "example.com_2015_05_23_1100_1200.gz",
"LogPath": "cdnlog.cn-hangzhou.oss.aliyun-inc.com/example.com/2015_05_23/example.com_2015_05_23_1100_1200.gz? OSSAccessKeyId\u003d3xmgf7Jhexxxxxx\u0026Expires\u003d143253xxxx\u0026Signature\u003d7Ly4ccKN3afzAGYyWDbxBcOxxxxx",
"LogSize": 257,
"StartTime": "2015-05-23T03:00:00Z"
}
]
}
},
"PageNumber": 1,
"TotalCount": 3,
"PageSize": 100
}
--------->
{
"RequestId": "077D0284-F041-4A41-A932-B48377FDAA25",
"DomainLogDetails": {
"DomainLogDetail": [
{
"LogInfos": {
"LogInfoDetail": [
{
"LogName": "test1.test.com_2018_03_25_180000_190000.gz",
"LogPath": "cdnlog2.aliyuncs.com/test1.test.com/2018_03_25/test1.test.com_2018_03_25_180000_190000.gz? Expires=1522659xxx&OSSAccessKeyId=test&Signature=suZFyJHoD3RzZqK%2Bcu6P4Vaxxxx",
"EndTime": "1521975600",
"StartTime": "1521972000",
"LogSize": 2645401
}
]
},
"LogCount": 20,
"PageInfos": {
"PageNumber": 1,
"PageSize": 20,
"Total": 20
},
"DomainName": "test1.test.com"
}
]
}
}
```

## Operations remain unchanged

The following list shows the operations that remain unchanged:

-   StartCdnDomain
-   StopCdnDomain
-   DeleteCdnDomain
-   PushObjectCache
-   RefreshObjectCaches
-   PreloadObjectCaches
-   PurgeObjectCaches
-   OpenCdnService
-   ModifyCdnService
-   DescribeUserConfigs
-   DescribeCdnService
-   DescribeCdnTypes
-   SetDomainServerCertificate
-   DescribeDomainCertificateInfo
-   BatchDeleteCdnDomainConfig
-   BatchStartCdnDomain
-   BatchStopCdnDomain
-   SetRangeConfig
-   SetUserAgentAcessRestriction
-   BatchSetCdnDomainConfig
-   SetL2OssKeyConfig
-   SetForwardSchemeConfig
-   SetPathCacheExpiredConfig
-   SetForceRedirectConfig
-   SetReqAuthConfig
-   SetErrorPageConfig
-   SetIpAllowListConfig
-   SetDomainGreenManagerConfig
-   SetHttpErrorPageConfig
-   SetCcConfig
-   SetHttpsOptionConfig
-   SetSourceHostConfig
-   SetRemoteReqAuthConfig
-   SetUserGreenManagerConfig
-   SetHttpHeaderConfig
-   SetRefererConfig
-   SetReqHeaderConfig
-   ModifyFileCacheExpiredConfig
-   ModifyPathCacheExpiredConfig
-   ModifyHttpHeaderConfig
-   DeleteHttpHeaderConfig

## Newly added operations

The following list shows the new operations supported by the latest Alibaba Cloud CDN API:

-   DescribeDomainSrcHttpCodeData
-   DescribeDomainAverageResponseTime
-   DescribeDomainRealTimeSrcBpsData
-   DescribeDomainRealTimeSrcHttpCodeData
-   DescribeDomainRealTimeSrcTrafficData
-   DescribeDomainRealTimeHttpCodeData
-   DescribeDomainRealTimeTrafficData
-   DescribeDomainSrcTrafficData
-   DescribeDomainTrafficData
-   BatchAddCdnDomain
-   BatchStartCdnDomain
-   BatchStopCdnDomain
-   BatchSetCdnDomainConfig
-   DescribeCdnCertificateList
-   DescribeDomainCertificateInfo
-   DescribeCdnDomainConfigs
-   DescribeUserVipsByDomain
-   DescribeCdnHttpsDomainList
-   CreateRealtimeLogDelivery
-   DeleteRealtimeLogDelivery
-   DescribeDomainRealtimeLogDelivery
-   DescribeRealtimeDeliveryAcc
-   DisableRealtimeLogDelivery
-   EnableRealtimeLogDelivery
-   ListRealtimeLogDeliveryDomains
-   ModifyRealtimeLogDelivery
-   ListRealtimeLogDeliveryInfos
-   ListUserCustomLogConfig
-   DescribeCdnUserResourcePackage
-   DescribeCdnUserResourcePackage
-   DescribeUserUsageDataExportTask
-   CreateUserUsageDataExportTask
-   CreateUsageDetailDataExportTask
-   DescribeUserUsageDetailDataExportTask
-   DescribeUserUsageDetailDataExportTask
-   DescribeTagResources
-   DescribeUserTags
-   TagResources
-   UntagResources

