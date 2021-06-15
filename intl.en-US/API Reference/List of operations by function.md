# List of operations by function

The following tables list API operations available for use in Alibaba Cloud Content Delivery Network \(CDN\).

## Service management

|API operation|Description|
|-------------|-----------|
|[OpenCdnService](/intl.en-US/API Reference/Service operation interface/OpenCdnService.md)|Activates Alibaba Cloud CDN. You must activate Alibaba Cloud CDN before you can manage domain names in Alibaba Cloud CDN.|
|[DescribeCdnService](/intl.en-US/API Reference/Service operation interface/DescribeCdnService.md)|Queries the status of your Alibaba Cloud CDN service. The status information includes the current billing method, the service activation time, the next effective billing method, and the current service status.|
|[ModifyCdnService](/intl.en-US/API Reference/Service operation interface/ModifyCdnService.md)|Changes the billing method of Alibaba Cloud CDN.|

## Domain name management

|API operation|Description|
|-------------|-----------|
|[AddCdnDomain](/intl.en-US/API Reference/Domain Operation Interface/AddCdnDomain.md)|Adds a domain name to Alibaba Cloud CDN.|
|[DescribeUserDomains](/intl.en-US/API Reference/Domain Operation Interface/DescribeUserDomains.md)|Queries all accelerated domain names that belong to your Alibaba Cloud account and their status.|
|[DescribeCdnDomainDetail](/intl.en-US/API Reference/Domain Operation Interface/DescribeCdnDomainDetail.md)|Queries the basic information about an accelerated domain name.|
|[ModifyCdnDomain](/intl.en-US/API Reference/Domain Operation Interface/ModifyCdnDomain.md)|Modifies the configuration of an accelerated domain name.|
|[StartCdnDomain](/intl.en-US/API Reference/Domain Operation Interface/StartCdnDomain.md)|Enables an accelerated domain name that is in the Offline state. After the accelerated domain name is enabled, the value of the DomainStatus parameter is changed to Online.|
|[StopCdnDomain](/intl.en-US/API Reference/Domain Operation Interface/StopCdnDomain.md)|Disables an accelerated domain name.|
|[DeleteCdnDomain](/intl.en-US/API Reference/Domain Operation Interface/DeleteCdnDomain.md)|Removes an accelerated domain name from Alibaba Cloud CDN.|
|[DescribeDomainsBySource](/intl.en-US/API Reference/Domain Operation Interface/DescribeDomainsBySource.md)|Queries all domain names corresponding to one or more origin servers that belong to your Alibaba Cloud account.|

## Refresh and prefetch tasks

|API operation|Description|
|-------------|-----------|
|[RefreshObjectCaches](/intl.en-US/API Reference/Refresh the preheating Interface/RefreshObjectCaches.md)|Refreshes files on CDN nodes.|
|[PushObjectCache](/intl.en-US/API Reference/Refresh the preheating Interface/PushObjectCache.md)|Prefetches content from one or more origin servers to all L2 CDN nodes in a specified accelerated region.|
|[DescribeRefreshTasks](/intl.en-US/API Reference/Refresh the preheating Interface/DescribeRefreshTasks.md)|Queries the status of refresh or prefetch tasks that belong to an accelerated domain name.|
|[DescribeRefreshQuota](/intl.en-US/API Reference/Refresh the preheating Interface/DescribeRefreshQuota.md)|Queries the maximum and remaining numbers of URLs and directories for object refreshing, and the maximum and remaining numbers of URLs for object prefetching.|

## Configuration management

|API operation|Description|
|-------------|-----------|
|[DescribeDomainConfigs](/intl.en-US/API Reference/Configuration Interfaces/DescribeDomainConfigs.md)|Queries the configurations of an accelerated domain name.|
|[SetOptimizeConfig](/intl.en-US/API Reference/Configuration Interfaces/SetOptimizeConfig.md)|Enables or disables the HTML optimization feature for an accelerated domain name.|
|[SetPageCompressConfig](/intl.en-US/API Reference/Configuration Interfaces/SetPageCompressConfig.md)|Configures the intelligent compression feature for an accelerated domain name.|
|[SetIgnoreQueryStringConfig](/intl.en-US/API Reference/Configuration Interfaces/SetIgnoreQueryStringConfig.md)|Configures the parameter filtering feature for an accelerated domain name.|
|[SetRangeConfig](/intl.en-US/API Reference/Configuration Interfaces/SetRangeConfig.md)|Configures the object chunking feature for an accelerated domain name.|
|[SetSourceHostConfig](/intl.en-US/API Reference/Configuration Interfaces/SetSourceHostConfig.md)|Specifies an origin host for an accelerated domain name.|
|[SetForceRedirectConfig](/intl.en-US/API Reference/Configuration Interfaces/SetForceRedirectConfig.md)|Configures the URL redirect feature for an accelerated domain name.|
|[SetRefererConfig](/intl.en-US/API Reference/Configuration Interfaces/SetRefererConfig.md)|Configures the referer-based hotlink protection feature for an accelerated domain name.|
|[SetPathCacheExpiredConfig](/intl.en-US/API Reference/Configuration Interfaces/SetPathCacheExpiredConfig.md)|Configures a cache expiration rule for a specified directory.|
|[DeleteCacheExpiredConfig](/intl.en-US/API Reference/Configuration Interfaces/DeleteCacheExpiredConfig.md)|Deletes a custom caching policy.|
|[SetReqAuthConfig](/intl.en-US/API Reference/Configuration Interfaces/SetReqAuthConfig.md)|Configures the authentication feature for an accelerated domain name.|
|[SetHttpHeaderConfig](/intl.en-US/API Reference/Configuration Interfaces/SetHttpHeaderConfig.md)|Specifies a custom HTTP header for an accelerated domain name.|
|[DeleteHttpHeaderConfig](/intl.en-US/API Reference/Configuration Interfaces/DeleteHttpHeaderConfig.md)|Deletes the configuration of referer-based hotlink protection for an accelerated domain name.|
|[SetDomainServerCertificate](/intl.en-US/API Reference/Configuration Interfaces/SetDomainServerCertificate.md)|Configures an SSL certificate for an accelerated domain name.|
|[SetIpBlackListConfig](/intl.en-US/API Reference/Configuration Interfaces/SetIpBlackListConfig.md)|Configures an IP blacklist for an accelerated domain name.|
|[SetHttpsOptionConfig](/intl.en-US/API Reference/Configuration Interfaces/SetHttpsOptionConfig.md)|Enables or disables the HTTP/2 protocol for an accelerated domain name.|
|[BatchDeleteCdnDomainConfig](/intl.en-US/API Reference/Configuration Interfaces/BatchDeleteCdnDomainConfig.md)|Deletes the configurations of specified features for one or more accelerated domain names.|
|[DeleteSpecificConfig](/intl.en-US/API Reference/Configuration Interfaces/DeleteSpecificConfig.md)|Deletes specified configurations for an accelerated domain name.|
|[SetRemoveQueryStringConfig](/intl.en-US/API Reference/Configuration Interfaces/SetRemoveQueryStringConfig.md)|Configures the parameter filtering feature for an accelerated domain name.|
|[SetCcConfig](/intl.en-US/API Reference/Configuration Interfaces/SetCcConfig.md)|Configures protection against HTTP flood attacks, and configures an IP blacklist and an IP whitelist for an accelerated domain name.|
|[SetReqHeaderConfig](/intl.en-US/API Reference/Configuration Interfaces/SetReqHeaderConfig.md)|Customizes a header for requests before they are redirected to the origin server for an accelerated domain name.|
|[SetIpAllowListConfig](/intl.en-US/API Reference/Configuration Interfaces/SetIpAllowListConfig.md)|Configures an IP whitelist for an accelerated domain name.|
|[DescribeUserConfigs](/intl.en-US/API Reference/Configuration Interfaces/DescribeUserConfigs.md)|Queries services that you have activated with your Alibaba Cloud account.|

## Resource monitoring

|API operation|Description|
|-------------|-----------|
|[DescribeDomainBpsData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainBpsData.md)|Queries bandwidth monitoring data for one or more accelerated domain names.|
|[DescribeDomainFlowData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainFlowData.md)|Queries traffic monitoring data for one or more accelerated domain names.|
|[DescribeDomainSrcBpsData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainSrcBpsData.md)|Queries bandwidth monitoring data of requests that are redirected to origin servers for one or more accelerated domain names.|
|[DescribeDomainSrcFlowData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainSrcFlowData.md)|Queries traffic monitoring data of requests that are redirected to origin servers for one or more accelerated domain names.|
|[DescribeDomainHitRateData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainHitRateData.md)|Queries the byte hit ratio that is measured in percentage.|
|[DescribeDomainReqHitRateData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainReqHitRateData.md)|Queries the request hit ratio that is measured in percentage.|
|[DescribeDomainHttpCodeData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainHttpCodeData.md)|Queries the total number and proportions of HTTP status codes returned from an accelerated domain name. The data is collected every 5 minutes.|
|[DescribeDomainsUsageByDay](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainsUsageByDay.md)|Queries the monitoring data of an accelerated domain name. The data is collected every day.|
|[DescribeTopDomainsByFlow](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeTopDomainsByFlow.md)|Queries the top N domain names ranked by network traffic.|
|[DescribeDomainPvData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainPvData.md)|Queries the page view \(PV\) data of an accelerated domain name. The data is collected every hour.|
|[DescribeDomainUvData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainUvData.md)|Queries the page view \(PV\) data of an accelerated domain name. The data is collected every hour.|
|[DescribeDomainRegionData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainRegionData.md)|Queries the visitor data classified by region for one or more accelerated domain names. The data is collected every day.|
|[DescribeDomainISPData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainISPData.md)|Queries the proportions of data usage of different Internet service providers \(ISPs\). The data is collected every day.|
|[DescribeDomainTopUrlVisit](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainTopUrlVisit.md)|Queries frequently requested URLs of an accelerated domain name on a specified day.|
|[DescribeDomainFileSizeProportionData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainFileSizeProportionData.md)|Queries the proportions of file sizes. The data is collected every hour.|
|[DescribeCdnRegionAndIsp](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeCdnRegionAndIsp.md)|Queries ISPs in each region.|
|[DescribeDomainBpsDataByTimeStamp](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainBpsDataByTimeStamp.md)|Queries the bandwidth data at a specified time for an accelerated domain.|
|[DescribeDomainMax95BpsData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainMax95BpsData.md)|Queries the 95th percentile bandwidth values of one or more accelerated domain names.|
|[DescribeDomainPathData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainPathData.md)|Queries monitoring data of network traffic and visits for an accelerated domain name. The data is collected every 5 minutes. This operation is available to only selected users.|
|[DescribeL2VipsByDomain](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeL2VipsByDomain.md)|Queries the virtual IP addresses of L2 CDN nodes for an accelerated domain name.|
|[DescribeRangeDataByLocateAndIspService](/intl.en-US/API Reference/Resource Monitoring Interface/Describerangedatabylocateandispservice.md)|Queries the bandwidth data at a specified time for each ISP in different regions.|
|[DescribeDomainRealTimeBpsData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainRealTimeBpsData.md)|Queries the bandwidth data that is collected every minute.|
|[DescribeDomainRealTimeByteHitRateData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainRealTimeByteHitRateData.md)|Queries byte hit ratios for an accelerated domain name. The data is collected every minute.|
|[DescribeDomainRealTimeQpsData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainRealTimeQpsData.md)|Queries the number of queries per second for one or more accelerated domain names. The data is collected every minute.|
|[DescribeDomainRealTimeReqHitRateData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainRealTimeReqHitRateData.md)|Queries the request hit ratios for one or more accelerated domain names. The data is collected every minute.|
|[DescribeDomainTopReferVisit](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainTopReferVisit.md)|Queries frequently requested web pages on a specified day and sorts the web pages.|
|[DescribeDomainQpsData](/intl.en-US/API Reference/Resource Monitoring Interface/DescribeDomainQpsData.md)|Queries the number of queries per second for one or more accelerated domain names.|

## Log management

|API operation|Description|
|-------------|-----------|
|[DescribeCdnDomainLogs](/intl.en-US/API Reference/Log Information Interface/DescribeCdnDomainLogs.md)|Queries the address where you can download the raw access log data of a specific domain name.|
|[DescribeCustomLogConfig](/intl.en-US/API Reference/Log Information Interface/DescribeCustomLogConfig.md)|Queries the detailed configuration of logging.|
|[DescribeDomainCustomLogConfig](/intl.en-US/API Reference/Log Information Interface/ModifyDomainCustomLogConfig.md)|Queries the custom log configuration of an accelerated domain name.|
|[DescribeUserCustomLogConfig](/intl.en-US/API Reference/Log Information Interface/DescribeUserCustomLogConfig.md)|Queries all custom log configurations that belong to your Alibaba Cloud account.|

## Auxiliary tools

|API operation|Description|
|-------------|-----------|
|[DescribeIpInfo](/intl.en-US/API Reference/Tool interface/DescribeIpInfo.md)|Checks whether a specified IP address belongs to a CDN node.|

