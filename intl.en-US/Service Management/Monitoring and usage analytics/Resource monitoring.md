---
keyword: [resource monitoring, CDN]
---

# Resource monitoring

Alibaba Cloud Content Delivery Network \(CDN\) supports the resource monitoring feature, which allows you to query monitoring data of domain names accelerated by Alibaba Cloud CDN. The monitoring data includes network traffic, bandwidth, back-to-origin traffic, back-to-origin bandwidth, the number of requests, the number of queries per second, cache hit ratios, HTTP status codes, and HTTP status codes returned to requests that are redirected to the origin servers. You can make informed business decisions based on the monitoring data.

## Overview

Monitoring data of resources can be collected every 5 minutes or 1 hour. You can query monitoring on the current day or within the last 90 days. You can specify a time range to query based on business requirements.

The resource monitoring feature monitors the following metrics. You can specify filter conditions, such as accelerated domain names, regions, and Internet service providers \(ISPs\), to filter monitoring data. You can also export monitoring data.

**Note:**

-   The monitoring data of the monitored items may be different from the data of the billable items in your bills. Assume that the billing cycle is 30 days. In the line chart of the monitoring data, the data is collected every 14,400 seconds. However, the data of the billable items is collected every 300 seconds. In this case, the line chart contains fewer data points because the line chart is intended to show the bandwidth usage trend. If you want to query more detailed monitoring data of the billable items, you can [Query resource usage](/intl.en-US/Service Management/Monitoring and usage analytics/Query resource usage.md).
-   Data is collected and calculated by calling API operations. For more information, see the API references.

|Metric|Monitored item|Related API operation|
|:-----|:-------------|---------------------|
|**Traffic/Bandwidth**|Bandwidth and network traffic of accelerated domain names. You can query monitoring data by region, ISP, and protocol. Supported protocols are HTTP, HTTPS, QUIC, IPv4, and IPv6.|-   [DescribeDomainBpsDataByLayer](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainBpsDataByLayer.md)
-   [DescribeDomainsUsageByDay](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainsUsageByDay.md) |
|**Back-to-origin Statistics**|Back-to-origin bandwidth and back-to-origin traffic of accelerated domain names.|-   [DescribeDomainSrcBpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcBpsData.md)
-   [DescribeDomainSrcTrafficData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcTrafficData.md) |
|**Visits**|The number of requests and the number of queries per second \(QPS\) to accelerated domain names.You can query monitoring data by region, ISP, and protocol. Supported protocols are HTTP, HTTPS, QUIC, IPv4, and IPv6.|[DescribeDomainQpsDataByLayer](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainQpsDataByLayer.md)|
|**Hit Rate**|Byte hit ratios and request hit ratios of accelerated domain names.|-   [DescribeDomainHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainHitRateData.md)
-   [DescribeDomainReqHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainReqHitRateData.md) |
|**HTTPCODE**|HTTP status codes, including HTTP 2xx, HTTP 3xx, HTTP 4xx, and HTTP 5xx status codes, returned from accelerated domain names.|[DescribeDomainHttpCodeDataByLayer](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainHttpCodeDataByLayer.md)|
|**HTTPCODE \(Back-to-origin\)**|HTTP status codes, including HTTP 2xx, HTTP 3xx, HTTP 4xx, and HTTP 5xx status codes, returned from origin servers.|[DescribeDomainSrcHttpCodeData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcHttpCodeData.md)|

## Differences between resource monitoring and real-time monitoring

The resource monitoring and real-time monitoring features are different in terms of data collection interval, data delay, and valid time range.

|Feature|Data collection interval|Data delay|Valid time range|
|-------|------------------------|----------|----------------|
|Resource monitoring|5 minutes|About 15 minutes|Within the last 90 days|
|Real-time monitoring|1 minute|About 3 minutes|Within the last 7 days|

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Monitoring & Usage Analytics** \> **Resource Monitoring**.

3.  On the **Resource Monitoring** page, select the monitoring item and metric that you want to query and click **Search**.

    The system displays monitoring data based on the specified metrics and filter conditions. Then, you can analyze or export the monitoring data.

    ![Resource monitoring](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0654651161/p93734.png)


