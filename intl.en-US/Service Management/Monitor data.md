# Monitor data {#task_261642 .task}

The Data Monitoring module includes resource monitoring and real-time monitoring. You can use the data monitoring function to learn about the running status of CDN.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, choose **Monitoring** \> **Resource Monitoring** or **Real-time Monitoring**.
3.  On the Resource Monitoring or Real-time Monitoring page, select monitoring items and metrics as needed and click **Search**. 
    -   Resource monitoring

        You can view and download the details about the following metrics by domain name, region, provider, time granularity \(1 minute, 5 minutes, or 1 hour\), and time range \(today, yesterday, last seven days, last 30 days, or a custom period\).

        |Item|Metric|
        |:---|:-----|
        |Traffic/Bandwidth|Bandwidth and traffic|
        |Back-to-origin Statistics|Back-to-origin bandwidth and back-to-origin traffic|
        |Visits|Requests and QPS|
        |Hit Rate|None|
        |HTTPCODE|5xx, 4xx, 3xx, and 2xx status codes|

        ![Resource monitoring](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15915/156826934352270_en-US.png)

        The data shown in the resource monitoring line chart differs slightly from the billing data. For example, a 30-day resource statistics line chart is plotted at 14,400s intervals, while the billing data is plotted at 300s intervals. The line chart does not take into account certain points and is mainly used to show the bandwidth trend. The billing data has finer granularity to help you calculate the actual bandwidth usage.

    -   Real-time monitoring

        You can view the details about the following metrics by domain name, region, provider, and time range \(last hour, last 6 hours, last 12 hours, or a custom period\).

        |Item|Metric|
        |:---|:-----|
        |Basic Data|Bandwidth, traffic, requests, and QPS|
        |Back-to-origin Statistics|Back-to-origin bandwidth and back-to-origin traffic|
        |Quality Monitoring|Request hit rate, byte hit rate, 5xx, 4xx, 3xx, and 2xx status codes|

        ![User interface](images/8909_en-US_source.png)


## API {#example_jag_lyi_ioh .example}

You can call API operations listed in the following table to implement the data monitoring function.

|Operation|Description|
|:--------|:----------|
|[DescribeDomainSrcHttpCodeData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcHttpCodeData.md#)|Queries the proportions of HTTP status codes based on back-to-origin statistics with a minimum time granularity of five minutes.|
|[DescribeDomainTopReferVisit](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainTopReferVisit.md#)|Queries frequently referenced URLs on a specified day and sorts the URLs.|
|[DescribeDomainTopUrlVisit](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainTopUrlVisit.md#)|Queries frequently referenced URLs on a specified day.|
|[DescribeDomainAverageResponseTime](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainAverageResponseTime.md#)|Queries the average response time of CDN domain names.|
|[Describedomainfilesizeproportiondata](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainFileSizeProportionData.md#)|Queries the proportions of file sizes with a minimum time granularity of one hour.|
|[DescribeDomainBpsDataByTimeStamp](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainBpsDataByTimeStamp.md#)|Queries the bandwidth data of domain names at a specified time. The bandwidth is measured in bit/s.|
|[DescribeDomainISPData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainISPData.md#)|Queries the proportions of Internet service providers \(ISPs\) with a time granularity of one day.|
|[DescribeCdnRegionAndIsp](../reseller.en-US/New API Reference/Data monitoring operations/DescribeCdnRegionAndIsp.md#)|Queries the list of Internet service providers \(ISPs\) in each region.|
|[DescribeRangeDataByLocateAndIspService](../reseller.en-US/New API Reference/Data monitoring operations/DescribeRangeDataByLocateAndIspService.md#)|Queries the bandwidth data at a specified time for Internet service providers \(ISPs\) in various regions. The bandwidth is measured in bit/s.|
|[DescribeDomainRealTimeBpsData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeBpsData.md#)|Queries the bandwidth data with a time granularity of one minute.|
|[DescribeDomainRealTimeSrcBpsData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeSrcBpsData.md#)|Queries the bandwidth data based on back-to-origin statistics with a time granularity of one minute.|
|[DescribeDomainRealTimeSrcHttpCodeData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeSrcHttpCodeData.md#)|Queries the proportions of HTTP status codes based on back-to-origin statistics with a time granularity of one minute.|
|[DescribeDomainRealTimeSrcTrafficData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeSrcTrafficData.md#)|Queries the network traffic based on back-to-origin statistics with a time granularity of one minute. The network traffic is measured in bits.|
|[DescribeDomainRealTimeByteHitRateData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeByteHitRateData.md#)|Queries byte hit rates with a time granularity of one minute.|
|[DescribeDomainRealTimeQpsData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeQpsData.md#)|Queries the number of visits per second with a time granularity of one minute.|
|[DescribeDomainRealTimeHttpCodeData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeHttpCodeData.md#)|Queries the proportions of HTTP status codes with a time granularity of one minute.|
|[DescribeDomainRealTimeTrafficData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeTrafficData.md#)|Queries the network traffic data with a time granularity of one minute. The network traffic is measured in bytes.|
|[DescribeDomainRealTimeReqHitRateData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeReqHitRateData.md#)|Queries the request hit rates with a time granularity of one minute.|
|[DescribeDomainBpsData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainBpsData.md#)|Queries the bandwidth data. The bandwidth is measured in bit/s.|
|[DescribeDomainSrcBpsData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcBpsData.md#)|Queries the bandwidth data based on back-to-origin statistics. The bandwidth is measured in bit/s.|
|[DescribeDomainSrcTrafficData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcTrafficData.md#)|Queries the network traffic based on back-to-origin statistics. The network traffic is measured in bits.|
|[DescribeDomainQpsData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainQpsData.md#)|Queries the number of queries per second \(QPS\).|
|[DescribeDomainsUsageByDay](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainsUsageByDay.md#)|Queries the monitoring data of domain names with a time granularity of one day.|
|[DescribeDomainHitRateData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainHitRateData.md#)|Queries the byte hit rate for domain names. The hit rate is measured in percentage.|
|[DescribeL2VipsByDomain](../reseller.en-US/New API Reference/Data monitoring operations/DescribeL2VipsByDomain.md#)|Queries the origin IP addresses of L2 cache nodes by domain name.|
|[DescribeDomainReqHitRateData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainReqHitRateData.md#)|Queries the request hit rate. The hit rate is measured in percentage.|
|[DescribeDomainHttpCodeData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainHttpCodeData.md#)|Queries the proportions of HTTP status codes with a minimum time granularity of five minutes.|
|[DescribeDomainTrafficData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainTrafficData.md#)|Queries the network traffic data. The network traffic data is measured in bytes.|
|[DescribeTopDomainsByFlow](../reseller.en-US/New API Reference/Data monitoring operations/DescribeTopDomainsByFlow.md#)|Queries Top N domains ranked by network traffic.|
|[DescribeDomainRegionData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainRegionData.md#)|Queries the visitor data classified by region with a time granularity of one day.|
|[DescribeDomainUvData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainUvData.md#)|Queries the unique visitor \(UV\) data with a minimum time granularity of one hour.|
|[DescribeDomainPvData](../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainPvData.md#)|Queries the page view \(PV\) data with a minimum time granularity of one hour.|

