---
keyword: [resource monitoring, real-time monitoring]
---

# Data monitoring

Data monitoring including resource monitoring and real-time monitoring. Data monitoring provides up-to-date information about your Content Delivery Network \(CDN\) service.

What are the differences between resource monitoring and usage query? These features collect data based on different metrics. The differences are:

-   Resource monitoring collects visit data based on user statistics. It collects resource usage data based on client IP addresses, geographic locations such as country, province, and city, and Internet service providers \(ISPs\).
-   Usage query collects billing data based on node statistics. It collects resource usage data based on the billable regions such as mainland China, North America, and South America.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Monitoring & Usage Analytics** \> **Resource Monitoring** or **Real-time Monitoring**.

3.  On the **Resource Monitoring** or **Real-time Monitoring** page, select the metrics that you want to query and click **Search**.

    -   Resource monitoring

        ![Resource monitoring](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7631136061/p93734.png)

        You can view and download details about the following metrics by domain name, region, ISP, time interval, and time range. You can view metrics of the current day, the last day, the last 7 days, the last 30 days, or a custom time range. You can query data collected every five minutes or one hour.

        |Item|Metric|
        |:---|:-----|
        |**Traffic/Bandwidth**|Bandwidth and traffic.|
        |**Back-to-origin Statistics**|Back-to-origin bandwidth and back-to-origin traffic.|
        |**Visits**|The number of requests and queries per second \(QPS\).|
        |**Hit Rate**|None.|
        |**HTTPCODE**|5xx status codes, 4xx status codes, 3xx status codes, and 2xx status codes.|
        |**HTTPCODE \(Back-to-origin\)**|5xx status codes, 4xx status codes, 3xx status codes, and 2xx status codes.|

        The data shown in the resource monitoring line chart slightly differs from the billing data. For example, a 30-day resource statistics line chart is plotted at 14,400-second intervals. The billing data is plotted at 300-second intervals. The line chart does not take certain points into account and is mainly used to show the bandwidth trend. You can view the billing data at a finer granularity to calculate the actual bandwidth usage.

    -   Real-time monitoring

        ![Console interface](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8909438951/p8909.png)

        You can view details about the following metrics by domain name, region, ISP, and time range. You can view metrics of the last hour, the last 6 hours, the last 12 hours, or a custom time range.

        |Item|Metric|
        |:---|:-----|
        |**Basic Data**|Bandwidth, traffic, requests, and QPS.|
        |**Back-to-origin Statistics**|Back-to-origin bandwidth and Back-to-origin traffic.|
        |**Quality Monitoring**|Request hit ratio, byte hit ratio, 5xx status codes, 4xx status codes, 3xx status codes, and 2xx status codes|


## Related API operations

You can call API operations listed in the following table to monitor your CDN service.

|API|Description|
|---|-----------|
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

