# List of operations by function

The following tables list API operations available for use in Alibaba Cloud Content Delivery Network \(CDN\). For more information, see OpenAPI Explorer.

## Data monitoring

|API operation|Description|
|-------------|-----------|
|[DescribeDomainSrcHttpCodeData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcHttpCodeData.md)|Queries the total number and proportions of HTTP status codes returned from an accelerated domain name. The data was collected at an interval of five minutes. You can query data collected within the last 90 days.|
|[DescribeDomainTopReferVisit](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainTopReferVisit.md)|Queries frequently requested web pages on a specified day and sorts the web pages. You can query data collected within the last 90 days.|
|[DescribeDomainTopUrlVisit](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainTopUrlVisit.md)|Queries frequently requested URLs of an accelerated domain name on a specified day. You can query data collected within the last 90 days.|
|[DescribeDomainAverageResponseTime](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainAverageResponseTime.md)|Queries the average response time of one or more accelerated domain names. You can query data collected within the last 90 days.|
|[DescribeDomainFileSizeProportionData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainFileSizeProportionData.md)|Queries the proportions of file sizes. The data was collected at an interval of one hour. You can query data collected within the last 90 days.|
|[DescribeDomainBpsDataByTimeStamp](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainBpsDataByTimeStamp.md)|Queries the bandwidth data at a specified time for an accelerated domain name.|
|[DescribeDomainISPData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainISPData.md)|Queries the proportions of data usage of different Internet service providers \(ISPs\). The data was collected at an interval of one day. You can query data collected within the last 90 days.|
|[DescribeCdnRegionAndIsp](/intl.en-US/New API Reference/Data monitoring operations/DescribeCdnRegionAndIsp.md)|Queries ISPs in each region.|
|[DescribeRangeDataByLocateAndIspService](/intl.en-US/New API Reference/Data monitoring operations/DescribeRangeDataByLocateAndIspService.md)|Queries the bandwidth data at a specified time for each ISP in different regions.|
|[DescribeDomainRealTimeBpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeBpsData.md)|Queries the bandwidth data of an accelerated domain name. The data was collected at an interval of one minute. You can query data collected within the last seven days.|
|[DescribeDomainRealTimeSrcBpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeSrcBpsData.md)|Queries the bandwidth data of back-to-origin requests. The data was collected at an interval of one minute. You can query data collected within the last seven days.|
|[DescribeDomainRealTimeSrcHttpCodeData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeSrcHttpCodeData.md)|Queries the total number and proportions of HTTP status codes returned from an accelerated domain name to back-to-origin requests. The data was collected at an interval of one minute. You can query data collected within the last seven days.|
|[DescribeDomainRealTimeSrcTrafficData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeSrcTrafficData.md)|Queries the monitoring data of back-to-origin traffic for an accelerated domain name. The data was collected at an interval of one minute. The network traffic is measured in bits. You can query data collected within the last 90 days.|
|[DescribeDomainRealTimeByteHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeByteHitRateData.md)|Queries byte hit rates of an accelerated domain name. The data was collected at an interval of one minute. You can query data collected within the last seven days.|
|[DescribeDomainRealTimeQpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeQpsData.md)|Queries the number of queries per second of an accelerated domain name. The data was collected at an interval of one minute. You can query data collected within the last seven days.|
|[DescribeDomainRealTimeHttpCodeData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeHttpCodeData.md)|Queries the total number and proportions of HTTP status codes returned from an accelerated domain name. The data was collected at an interval of one minute. You can query data collected within the last seven days.|
|[DescribeDomainRealTimeTrafficData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeTrafficData.md)|Queries the monitoring data of an accelerated domain name. The data was collected at an interval of one minute. The network traffic is measured in bytes. You can query data collected within the last 90 days.|
|[DescribeDomainRealTimeReqHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeReqHitRateData.md)|Queries the request hit rates of an accelerated domain name. The data was collected at an interval of one minute. You can only query the data collected within the last seven days.|
|[DescribeDomainBpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainBpsData.md)|Queries the network bandwidth data of an accelerated domain name. You can query data collected within the last 90 days.|
|[DescribeDomainSrcBpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcBpsData.md)|Queries the bandwidth data of back-to-origin requests. You can query data collected within the last 90 days.|
|[DescribeDomainSrcTrafficData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcTrafficData.md)|Queries the monitoring data of back-to-origin traffic for an accelerated domain name. The network traffic is measured in bits. You can query data collected within the last 90 days.|
|[DescribeDomainsUsageByDay](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainsUsageByDay.md)|Queries the monitoring data of an accelerated domain name. The data was collected at an interval of one day. You can query data collected within the last 90 days.|
|[DescribeDomainHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainHitRateData.md)|Queries the byte hit rates of an accelerated domain name. Hit rates are measured in percentage. You can query data collected within the last 90 days.|
|[DescribeL2VipsByDomain](/intl.en-US/New API Reference/Data monitoring operations/DescribeL2VipsByDomain.md)|Queries the virtual IP addresses of L2 CDN nodes for a specific domain name.|
|[DescribeDomainReqHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainReqHitRateData.md)|Queries the request hit rates of an accelerated domain name. Hit rates are measured in percentage. You can query data collected within the last 90 days.|
|[DescribeDomainHttpCodeData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainHttpCodeData.md)|Queries the total number and proportions of HTTP status codes returned from an accelerated domain name. You can query data collected within the last 90 days.|
|[DescribeDomainTrafficData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainTrafficData.md)|Queries the monitoring data of network traffic for an accelerated domain name. The network traffic is measured in bytes. You can query data collected within the last 90 days.|
|[DescribeTopDomainsByFlow](/intl.en-US/New API Reference/Data monitoring operations/DescribeTopDomainsByFlow.md)|Queries the top N domain names ranked by network traffic. You can query data collected within the last 90 days.|
|[DescribeDomainRegionData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRegionData.md)|Queries the visitor data classified by region for an accelerated domain name. The data was collected at an interval of one day.|
|[DescribeDomainUvData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainUvData.md)|Queries the unique visitor \(UV\) data of an accelerated domain name. The data was collected at an interval of one hour. You can query data collected within the last 90 days.|
|[DescribeDomainPvData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainPvData.md)|Queries the page view \(PV\) data of an accelerated domain name. The data was collected at an interval of one hour.|
|[DescribeDomainQpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainQpsData.md)|Queries the number of queries per second of an accelerated domain name. The data was collected at an interval of five minutes. You can query data collected within the last 90 days.|
|[ListFCTrigger](/intl.en-US/New API Reference/Data monitoring operations/ListFCTrigger.md)|Queries the Function Compute trigger set for an Alibaba Cloud CDN event.|
|[DescribeDomainQpsDataByLayer](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainQpsDataByLayer.md)|Queries the number of queries per second at a specific layer for an accelerated domain name. You can query data collected within the last 90 days.|
|[DescribeDomainTopClientIpVisit](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainTopClientIpVisit.md)|Queries client IP addresses that are ranked by the number of requests or the network traffic usage within a specific time range. You can query data collected within the last 90 days.|
|[DescribeDomainRealTimeDetailData]()|Queries the data usage of each ISP and the number of visits in each region. The data was collected at an interval of one minute. You can query data collected within the last seven days.|
|[DescribeDomainSrcTopUrlVisit](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcTopUrlVisit.md)|Queries frequently requested URLs of an accelerated domain name.|
|[DescribeDomainSrcQpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcQpsData.md)|Queries the number of back-to-origin requests per second of an accelerated domain name.|

## Domain management

|API operation|Description|
|-------------|-----------|
|[AddCdnDomain](/intl.en-US/New API Reference/Domain name management/AddCdnDomain.md)|Adds a domain name to Alibaba Cloud CDN.|
|[DeleteCdnDomain](/intl.en-US/New API Reference/Domain name management/DeleteCdnDomain.md)|Removes a domain name from Alibaba Cloud CDN.|
|[StopCdnDomain](/intl.en-US/New API Reference/Domain name management/StopCdnDomain.md)|Disables a domain name that is accelerated by Alibaba Cloud CDN. After the domain name is disabled, the value of the DomainStatus parameter is changed to Offline.|
|[StartCdnDomain](/intl.en-US/New API Reference/Domain name management/StartCdnDomain.md)|Enables a disabled domain name. After the domain name is enabled, the value of the DomainStatus parameter is changed to Online.|
|[BatchStartCdnDomain](/intl.en-US/New API Reference/Domain name management/BatchStartCdnDomain.md)|Enables one or more domain names at a time. After a domain name is enabled, the value of the DomainStatus parameter is changed to Online.|
|[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)|Configures multiple accelerated domain names at a time.|
|[ModifyCdnDomain](/intl.en-US/New API Reference/Domain name management/ModifyCdnDomain.md)|Modifies the information about an accelerated domain name.|
|[DescribeUserDomains](/intl.en-US/New API Reference/Domain name management/DescribeUserDomains.md)|Queries all domain names accelerated by Alibaba Cloud CDN under your account and the status of the accelerated domain names. You can filter domain names by name or status. Fuzzy match is supported.|
|[DescribeCdnDomainDetail](/intl.en-US/New API Reference/Domain name management/DescribeCdnDomainDetail.md)|Queries the basic information about an accelerated domain name.|
|[DescribeDomainsBySource](/intl.en-US/New API Reference/Domain name management/DescribeDomainsBySource.md)|Queries the domain names corresponding to origin servers under your account.|
|[BatchStopCdnDomain](/intl.en-US/New API Reference/Domain name management/BatchStopCdnDomain.md)|Disables one or more accelerated domain names at a time. After an accelerated domain name is disabled, the value of the DomainStatus parameter is changed to Offline.|
|[DescribeCdnDomainConfigs](/intl.en-US/New API Reference/Domain name management/DescribeCdnDomainConfigs.md)|Queries the configurations of an accelerated domain name. You can query the configuration of one or more features at a time.|
|[DeleteSpecificConfig](/intl.en-US/New API Reference/Domain name management/DeleteSpecificConfig.md)|Deletes specific configurations of an accelerated domain name.|
|[DescribeUserVipsByDomain](/intl.en-US/New API Reference/Domain name management/DescribeUserVipsByDomain.md)|Queries virtual IP addresses of CDN nodes by domain name.|
|[BatchAddCdnDomain](/intl.en-US/New API Reference/Domain name management/BatchAddCdnDomain.md)|Adds multiple domain names to Alibaba Cloud CDN at a time. You can add a maximum of 20 domain names to Alibaba Cloud CDN with each account.|
|[ModifyCdnDomainSchdmByProperty](/intl.en-US/New API Reference/Domain name management/ModifyCdnDomainSchdmByProperty.md)|Modifies the accelerated region for an accelerated domain name.|
|[BatchUpdateCdnDomain](/intl.en-US/New API Reference/Domain name management/BatchUpdateCdnDomain.md)|Updates the configurations of multiple accelerated domain names at a time.|
|[SetWaitingRoomConfig](/intl.en-US/New API Reference/Domain name management/SetWaitingRoomConfig.md)|Configures the virtual waiting room feature for an accelerated domain name. This operation is available only for accelerated domain names of the DCDN workload type.|

## Log management

|API operation|Description|
|-------------|-----------|
|[DescribeCdnDomainLogs](/intl.en-US/New API Reference/Log operations/DescribeCdnDomainLogs.md)|Queries the address where you can download the raw access log data of a specific domain name.|
|[CreateRealTimeLogDelivery](/intl.en-US/New API Reference/Log operations/CreateRealTimeLogDelivery.md)|Configures real-time log delivery for specific accelerated domain names.|
|[DeleteRealtimeLogDelivery](/intl.en-US/New API Reference/Log operations/DeleteRealtimeLogDelivery.md)|Deletes the configurations of real-time log delivery for specific accelerated domain names.|
|[DescribeDomainRealtimeLogDelivery](/intl.en-US/New API Reference/Log operations/DescribeDomainRealtimeLogDelivery.md)|Queries the information about real-time log delivery for an accelerated domain name.|
|[DisableRealtimeLogDelivery](/intl.en-US/New API Reference/Log operations/DisableRealtimeLogDelivery.md)|Disables real-time log delivery for specific accelerated domain names.|
|[EnableRealtimeLogDelivery](/intl.en-US/New API Reference/Log operations/EnableRealtimeLogDelivery.md)|Enables real-time log delivery for specific accelerated domain names.|
|[ListRealtimeLogDeliveryDomains](/intl.en-US/New API Reference/Log operations/ListRealtimeLogDeliveryDomains.md)|Queries all domain names that are associated with a specific real-time log delivery configuration.|
|[ListRealtimeLogDeliveryInfos](/intl.en-US/New API Reference/Log operations/ListRealtimeLogDeliveryInfos.md)|Queries the information about real-time log delivery in a specified region.|
|[ModifyRealtimeLogDelivery](/intl.en-US/New API Reference/Log operations/ModifyRealtimeLogDelivery.md)|Modifies the real-time log delivery configuration for an accelerated domain name. You can deliver log data of an accelerated domain name to only one Logstore.|
|[DescribeDomainCustomLogConfig](/intl.en-US/New API Reference/Log operations/DescribeDomainCustomLogConfig.md)|Queries the custom log configuration of an accelerated domain name.|
|[ListDomainsByLogConfigId](/intl.en-US/New API Reference/Log operations/ListDomainsByLogConfigId.md)|Queries all accelerated domain names associated with a custom log configuration.|
|[ListUserCustomLogConfig](/intl.en-US/New API Reference/Log operations/ListUserCustomLogConfig.md)|Queries all custom log configurations under your account.|
|[DescribeCustomLogConfig](/intl.en-US/New API Reference/Log operations/DescribeCustomLogConfig.md)|Queries the detailed configuration of logging.|

## Refresh and prefetch tasks

|API operation|Description|
|-------------|-----------|
|[PushObjectCache](/intl.en-US/New API Reference/Refresh and preload operations/PushObjectCache.md)|Prefetches content from origins to L2 CDN nodes. This reduces workloads on origins because users can hit cache upon their first visits.|
|[DescribeRefreshQuota](/intl.en-US/New API Reference/Refresh and preload operations/DescribeRefreshQuota.md)|Queries the maximum and remaining numbers of URLs and directories for object refreshing, the maximum and remaining numbers of URLs for object prefetching, and the maximum and remaining numbers of URLs and directories that can be blocked.|
|[DescribeRefreshTasks](/intl.en-US/New API Reference/Refresh and preload operations/DescribeRefreshTasks.md)|Queries the status of refresh or prefetch tasks.|
|[RefreshObjectCaches](/intl.en-US/New API Reference/Refresh and preload operations/RefreshObjectCaches.md)|Refreshes files on CDN nodes. Alibaba Cloud CDN allows you to refresh content of multiple URLs at a time.|

## Service management

|API operation|Description|
|-------------|-----------|
|[OpenCdnService](/intl.en-US/New API Reference/Service management operations/OpenCdnService.md)|Activates Alibaba Cloud CDN. You must activate Alibaba Cloud CDN before you can manage domain names in Alibaba Cloud CDN.|
|[DescribeCdnService](/intl.en-US/New API Reference/Service management operations/DescribeCdnService.md)|Queries the status of your Alibaba Cloud CDN service. The status information includes the service activation time, current service status, current billing method, and new billing method.|
|[DescribeCdnUserResourcePackage](/intl.en-US/New API Reference/Service management operations/DescribeCdnUserResourcePackage.md)|Queries the current resource plans that you have purchased for Alibaba Cloud CDN.|
|[DescribeCdnUserQuota](/intl.en-US/New API Reference/Service management operations/DescribeCdnUserQuota.md)|Queries the quotas and usage of Alibaba Cloud CDN resources.|

## Certificate management

|API operation|Description|
|-------------|-----------|
|[CreateCdnCertificateSigningRequest](/intl.en-US/New API Reference/Certificate operations/CreateCdnCertificateSigningRequest.md)|Creates a certificate signing request \(CSR\).|
|[DescribeDomainCertificateInfo](/intl.en-US/New API Reference/Certificate operations/DescribeDomainCertificateInfo.md)|Queries the certificate information about an accelerated domain name.|
|[SetDomainServerCertificate](/intl.en-US/New API Reference/Certificate operations/SetDomainServerCertificate.md)|Configures a Secure Sockets Layer \(SSL\) certificate for an accelerated domain name.|
|[SetCdnDomainCSRCertificate](/intl.en-US/New API Reference/Certificate operations/SetDomainServerCertificate.md)|Configures an SSL certificate for a specified domain name.|
|[DescribeCdnDomainByCertificate](/intl.en-US/New API Reference/Certificate operations/DescribeCdnDomainByCertificate.md)|Queries accelerated domain names by SSL certificate.|
|[DescribeCdnCertificateDetail](/intl.en-US/New API Reference/Certificate operations/DescribeCdnCertificateDetail.md)|Queries the detailed information about an SSL certificate.|
|[DescribeCdnCertificateList](/intl.en-US/New API Reference/Certificate operations/DescribeCdnCertificateList.md)|Queries the list of certificates for accelerated domain names.|
|[DescribeCertificateInfoByID](/intl.en-US/New API Reference/Certificate operations/DescribeCertificateInfoByID.md)|Queries the information about a specific certificate.|
|[BatchSetCdnDomainServerCertificate](/intl.en-US/New API Reference/Certificate operations/BatchSetCdnDomainServerCertificate.md)|Configures an SSL certificate for one or more accelerated domain names.|
|[DescribeCdnHttpsDomainList](/intl.en-US/New API Reference/Certificate operations/DescribeCdnHttpsDomainList.md)|Queries the information about certificates under your account.|

## Resource usage queries

|API operation|Description|
|-------------|-----------|
|[DescribeUserUsageDataExportTask](/intl.en-US/New API Reference/Usage query operations/DescribeUserUsageDataExportTask.md)|Queries export tasks that were created in the last three months. The tasks were used to export resource usage information.|
|[CreateUserUsageDataExportTask](/intl.en-US/New API Reference/Usage query operations/CreateUserUsageDataExportTask.md)|Creates a task to export your resource usage history. The information is exported to a PDF file.|
|[CreateUsageDetailDataExportTask](/intl.en-US/New API Reference/Usage query operations/CreateUsageDetailDataExportTask.md)|Creates a task to export the resource usage details. The details are exported to an EXCEL file.|
|[DescribeUserUsageDetailDataExportTask](/intl.en-US/New API Reference/Usage query operations/DescribeUserUsageDetailDataExportTask.md)|Queries tasks that were used to export resource usage details of one or more accelerated domain names under your account. The resource usage information was collected at an interval of five minutes within a specific time range.|
|[DescribeDomainUsageData](/intl.en-US/New API Reference/Usage query operations/DescribeDomainUsageData.md)|Queries the resource usage information of specific domain names in a specified region.|
|[DeleteUserUsageDataExportTask](/intl.en-US/New API Reference/Usage query operations/DeleteUserUsageDataExportTask.md)|Deletes a task that was used to export usage history.|
|[DeleteUsageDetailDataExportTask](/intl.en-US/New API Reference/Usage query operations/DeleteUsageDetailDataExportTask.md)|Deletes a task that was used to export usage details.|

## Tag management

|API operation|Description|
|-------------|-----------|
|[DescribeTagResources](/intl.en-US/New API Reference/Tag management operations/DescribeTagResources.md)|Queries the tags of one or more resources.|
|[DescribeUserTags](/intl.en-US/New API Reference/Tag management operations/DescribeUserTags.md)|Queries user tags.|
|[UntagResources](/intl.en-US/New API Reference/Tag management operations/UntagResources.md)|Removes tags from a resource.|
|[TagResources](/intl.en-US/New API Reference/Tag management operations/TagResources.md)|Attaches one or more tags to specific resources.|

## Auxiliary tools

|API operation|Description|
|-------------|-----------|
|[DescribeIpInfo](/intl.en-US/New API Reference/Auxiliary tool operations/DescribeIpInfo.md)|Checks whether a specified IP address is assigned to an Alibaba Cloud CDN node.|
|[CreateIllegalUrlExportTask](/intl.en-US/New API Reference/Log operations/CreateIllegalUrlExportTask.md)|Creates a task to export invalid URLs.|
|[DescribeIllegalUrlExportTask](/intl.en-US/New API Reference/Log operations/DescribeIllegalUrlExportTask.md)|Queries tasks that were used to export invalid URLs.|

