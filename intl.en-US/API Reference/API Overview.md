# API Overview {#reference_ckk_xml_vdb .reference}

## Service Operation Interface {#section_tsp_qnl_vdb .section}

|API|Description|
|:--|:----------|
|[OpenCdnService](https://www.alibabacloud.com/help/doc-detail/27157.htm)|Activates the CDN service.|
|[DescribeCdnService](https://www.alibabacloud.com/help/doc-detail/27158.htm)|Queries the CDN service status. This includes Includes Current billing type, service opening time, next effective billing type, current business status, etc.|
|[ModifyCdnService](https://www.alibabacloud.com/help/doc-detail/27159.htm)|Changes the CDN service billing type.|

## Refresh the preheating Interface {#section_tzc_vnl_vdb .section}

|API|Description|
|:--|:----------|
|[Refreshobjectcaches](https://www.alibabacloud.com/help/doc-detail/27200.htm)|Refreshes the file content on a node. Refreshes the specified URL content to the Cache node.|
|[PushObjectCache](https://www.alibabacloud.com/help/doc-detail/27201.htm)|Actively pushes content from the origin site to the L2 Cache node. Upon first access, users can directly hit cache so as to relieve pressure on the origin site.|
|[Describerefreshtasks](https://www.alibabacloud.com/help/doc-detail/27202.htm)|Queries whether or not cache push or refresh statuses have taken effect for the whole site.|
|[DescribeRefreshQuota](https://www.alibabacloud.com/help/doc-detail/27203.htm)|Query preheating refresh operation margin|

## Log Information Interface {#section_c3h_xnl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeCdnDomainLogs](https://www.alibabacloud.com/help/doc-detail/27224.htm)|Obtains the download address for the original access log of the specified domain name.|
|[DescribeCustomLogConfig](https://www.alibabacloud.com/help/doc-detail/62687.htm)|Query custom log configuration details according to configId.|
|[ModifyDomainCustomLogConfig](https://www.alibabacloud.com/help/doc-detail/62688.htm)|Modify custom log configurations under a domain name.|
|[DescribeUserCustomLogConfig](https://www.alibabacloud.com/help/doc-detail/62690.htm)|Obtain user's all the custom log congifuration.|
|[ListDomainsByLogConfigId](https://www.alibabacloud.com/help/doc-detail/62689.htm)|Query the list of all the domain names using a custom log configuration.|
|[ModifyDomainCustomLogConfig](https://www.alibabacloud.com/help/doc-detail/62691.htm)|Modify custom log configurations under a domain name.|
|[ModifyUserCustomLogConfig](https://www.alibabacloud.com/help/doc-detail/62692.htm)|Modifies the user customized log configuration information.|

## Configuration Interface {#section_lqd_5nl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeDomainConfigs](https://www.alibabacloud.com/help/doc-detail/27169.htm)|Queryies domain name configuration|
|[Setoptimizeconfig](https://www.alibabacloud.com/help/doc-detail/27170.htm)|Configures page optimization parameters.|
|[SetPageCompressConfig](https://www.alibabacloud.com/help/doc-detail/27171.htm)|Configures smart compression parameters.|
|[SetIgnoreQueryStringConfig](https://www.alibabacloud.com/help/doc-detail/27172.htm)|Configure filter parameters|
|[SetRangeConfig](https://www.alibabacloud.com/help/doc-detail/27173.htm)|Configures Back-to-source of range.|
|[SetVideoSeekConfig](https://www.alibabacloud.com/help/doc-detail/27174.htm)|Configures Drag/Drop playback.|
|[Setsourcehostconfig](https://www.alibabacloud.com/help/doc-detail/27175.htm)|Set back-to-source host|
|[SetErrorPageConfig](https://www.alibabacloud.com/help/doc-detail/27176.htm)|Set the 404 page.|
|[Setforceredirectconfig](https://www.alibabacloud.com/help/doc-detail/27177.htm)|Set the force redirect method, and currently support HTTP and HTTPS force redirects.|
|[SetRefererConfig](https://www.alibabacloud.com/help/doc-detail/27178.htm)|Set Anti-leech.|
|[SetFileCacheExpiredConfig](https://www.alibabacloud.com/help/doc-detail/27179.htm)|Set file expiration configuration.|
|[SetPathCacheExpiredConfig](https://www.alibabacloud.com/help/doc-detail/27180.htm)|Modify directory expiration configuration.|
|[ModifyFileCacheExpiredConfig](https://www.alibabacloud.com/help/doc-detail/27181.htm)|Modify file expiration settings.|
|[ModifyPathCacheExpiredConfig](https://www.alibabacloud.com/help/doc-detail/27182.htm)|Modify the path Cache Policy|
|[DeleteCacheExpiredConfig](https://www.alibabacloud.com/help/doc-detail/27183.htm)|Delete a custom cache policy.|
|[SetReqAuthConfig](https://www.alibabacloud.com/help/doc-detail/27184.htm)|Set CDN domain access authentication configuration.|
|[Sethttpheaderconfig](https://www.alibabacloud.com/help/doc-detail/27185.htm)|Set custom HTTP headers.|
|[ModifyHttpHeaderConfig](https://www.alibabacloud.com/help/doc-detail/27186.htm)|Modify custom HTTP headers.|
|[DeleteHttpHeaderConfig](https://www.alibabacloud.com/help/doc-detail/27187.htm)|Delete the Referer anti-leech configuration of a CDN domain.|
|[SetDomainServerCertificate](https://www.alibabacloud.com/help/doc-detail/45014.htm)|Set whether to enable the certificate function under a domain name and modify certificate information.|
|[SetIpBlackListConfig](https://www.alibabacloud.com/help/doc-detail/55792.htm)|Set the IP address blacklist of a CDN domain.|

## Domain Operation Interface {#section_iv2_tnl_vdb .section}

|API|Description|
|:--|:----------|
|[AddCdnDomain](https://www.alibabacloud.com/help/doc-detail/27161.htm)|Adds CDN domains. At one time, only one CDN can be submitted.|
|[DescribeUserDomains](https://www.alibabacloud.com/help/doc-detail/27162.htm)|Queries all domain names and statuses under a user name.|
|[DescribeCdnDomainDetail](https://www.alibabacloud.com/help/doc-detail/27163.htm)|Obtains the basic information for the specified CDN domain configuration.|
|[ModifyCdnDomain](https://www.alibabacloud.com/help/doc-detail/27164.htm)|Modify CDN domains.|
|[StartCdnDomain](https://www.alibabacloud.com/help/doc-detail/27165.htm)|Enables an accelerated domain name with a status of "disabled" and changes the domainstatus to online|
|[StopCdnDomain](https://www.alibabacloud.com/help/doc-detail/27166.htm)|Deactivates a CDN domain by changing the “DomainStatus” to “offline”.|
|[DeleteCdnDomain](https://www.alibabacloud.com/help/doc-detail/27167.htm)|\[USE WITH CAUTION\] Deletes the current CDN domain. Only one CDN domain can be submitted at a time.|
|[DescribeDomainsBySource](https://www.alibabacloud.com/help/doc-detail/50453.htm)|Query the corresponding domain name information based on the source station|

## Tool Interface {#section_ttd_ynl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeIpInfo](https://www.alibabacloud.com/help/doc-detail/27226.htm)|Verifies whether the specified IP address is the IP address of an Alibaba Cloud CDN node.|

## Resource Monitoring Interface {#section_mn2_wnl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeDomainBpsData](https://www.alibabacloud.com/help/doc-detail/27205.htm)|Obtain the network bandwidth metric data of a CDN domain.|
|[DescribeDomainFlowData](https://www.alibabacloud.com/help/doc-detail/27206.htm)|Obtain the network traffic metric data of a CDN domain.|
|[DescribeDomainSrcBpsData](https://www.alibabacloud.com/help/doc-detail/27207.htm)|Obtain the back-to-source bandwidth metric data of CDN domains.|
|[DescribeDomainSrcFlowData](https://www.alibabacloud.com/help/doc-detail/27208.htm)|Obtain the back-to-source traffic metric data on a CDN domain in bits.|
|[DescribeDomainHitRateData](https://www.alibabacloud.com/help/doc-detail/27209.htm)|Obtain the bytes hit rate \(percentage of hit bytes\) of CDN domains.|
|[DescribeDomainReqHitRateData](https://www.alibabacloud.com/help/doc-detail/27210.htm)|Obtain the request hit rate \(percentage of hit requests\) of CDN domain names.|
|[DescribeDomainQpsData](https://www.alibabacloud.com/help/doc-detail/27211.htm)|Obtain the times of access to a CDN domain per second. The value is expressed in QPS.|
|[DescribeDomainHttpCodeData](https://www.alibabacloud.com/help/doc-detail/27212.htm)|Obtain the HTTP return code proportion of CDN domains. The minimum granularity is 5 minutes.|
|[DescribeDomainsUsageByDay](https://www.alibabacloud.com/help/doc-detail/27213.htm)|Obtain the per-day monitoring statistics on a CDN domain.|
|[DescribeTopDomainsByFlow](https://www.alibabacloud.com/help/doc-detail/27214.htm)|Obtain the domain names that are ranked by traffic.|
|[DescribeDomainPvData](https://www.alibabacloud.com/help/doc-detail/27215.htm)|Obtain the PV page access statistics. The minimum granularity is 1 hour.|
|[DescribeDomainUvData](https://www.alibabacloud.com/help/doc-detail/27216.htm)|Obtain the independent UV page access statistics of a CDN domain. The minimum granularity is 1 hour.|
|[DescribeDomainRegionData](https://www.alibabacloud.com/help/doc-detail/27217.htm)|Obtain the regional user distribution of CDN domains with day granularity.|
|[DescribeDomainISPData](https://www.alibabacloud.com/help/doc-detail/27218.htm)|Obtain the distribution of users and carriers of CDN domain names with day granularity.|
|[Describedomaintopurlvisit](https://www.alibabacloud.com/help/doc-detail/27219.htm)|Obtain the popular URL list for a CDN domain name on a specific day.|
|[DescribeDomainTopReferVisit](https://www.alibabacloud.com/help/doc-detail/27220.htm)|Obtain the reference times ranking of popular pages for a CDN domain name on a specific day.|
|[DescribeDomainFileSizeProportionData](https://www.alibabacloud.com/help/doc-detail/27221.htm)|Obtain the file size shares of a CDN domain name. The minimum granularity is 1 hour.|
|[DescribeCdnRegionAndIsp](https://www.alibabacloud.com/help/doc-detail/43474.htm)|Obtain a list of regions and carriers.|
|[DescribeDomainBpsDataByTimeStamp](https://www.alibabacloud.com/help/doc-detail/43473.htm)|Obtain the bandwidth data of a CDN domain name on different locations and ISPs at specific time. The unit is bit/second.|
|[DescribeDomainMax95BpsData](https://www.alibabacloud.com/help/doc-detail/60698.htm)|Obtain the 95th percentile bandwidth metric data of CDN domain names. Unit: bit/second. Unit: bit/second.|
|[DescribeDomainPathData](https://www.alibabacloud.com/help/doc-detail/61132.htm)|Obtain metric data of 5 minutes of CDN domain names path level, including traffic and times of accesses.|
|[DescribeL2VipsByDomain](https://www.alibabacloud.com/help/doc-detail/48769.htm)|Query the virtual IP address list of an L2 node by the domain name. This interface takes effect after a whitelist is configured.|
|[Describerangedatabylocateandispservice](https://www.alibabacloud.com/help/doc-detail/44723.htm)|Gets bandwidth data on different locates and ISPs for an accelerated domain name at a certain time.|
|[DescribeDomainRealTimeBpsData](https://www.alibabacloud.com/help/doc-detail/67951.htm)|Obtain bandwidth data of domain name with 1-minute granularity.|
|[DescribeDomainRealTimeByteHitRateData](https://www.alibabacloud.com/help/doc-detail/65027.htm)|Obtain byte hit rate data of domain names with 1-minute granularity.|
|[DescribeDomainRealTimeQpsData](https://www.alibabacloud.com/help/doc-detail/65028.htm)|Obtain Queries per second \(QPS\) of the domain name for every 1 minute.|
|[DescribeDomainRealTimeReqHitRateData](https://www.alibabacloud.com/help/doc-detail/65029.htm)|Obtain the request hit rate of the domain name with 1-minute granularity.|

## Dynamic Route for CDN Interface {#section_ggs_h2x_yfb .section}

|API|Description|
|:--|:----------|
|[SetDynamicConfig](https://www.alibabacloud.com/help/doc-detail/62851.htm)|Set the cache rules of Dynamic Route for Content Delivery Network \(DCDN\).|

