---
keyword: [real-time monitoring, CDN]
---

# Real-time Monitoring

Alibaba Cloud Content Delivery Network \(CDN\) supports the real-time monitoring feature. This feature allows you to query the basic information, back-to-origin traffic, and acceleration performance of an accelerated domain name. The basic information includes bandwidth, network traffic, the number of requests, and the number of queries per second. Real-time monitoring helps you detect anomalies in network traffic and locate errors at the earliest opportunity.

## Overview

The real-time monitoring feature collects monitoring data every minute. You can query monitoring data collected 3 minutes before the current time \(data is delayed by 3 minutes\) to the last seven days. You can specify a time range, which cannot exceed 24 hours. The data collection rules, including collection intervals, applied to real-time monitoring are different from the rules applied to resource monitoring and usage query. Therefore, the monitoring data provided by real-time monitoring may be different from that provided by resource monitoring or usage query.

The following table describes the monitored items. You can query metrics such as bandwidth and network traffic by setting query conditions, for example, domain name, region, Internet service provider \(ISP\), and time range.

**Note:** Data is collected and calculated by calling API operations. For more information, see the API references.

|Metric|Description|API references|
|------|-----------|--------------|
|**Basic Data**|Monitors the bandwidth values, network traffic, number of requests, and number of queries per second for accelerated domain names.|-   [DescribeDomainRealTimeBpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeBpsData.md)
-   [DescribeDomainRealTimeQpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeQpsData.md)
-   [DescribeDomainRealTimeTrafficData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeTrafficData.md) |
|**Back-to-origin Statistics**|Monitors the back-to-origin bandwidth values and back-to-origin network traffic for accelerated domain names.|-   [DescribeDomainRealTimeSrcBpsData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeSrcBpsData.md)
-   [DescribeDomainRealTimeSrcTrafficData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeSrcTrafficData.md) |
|**Quality Monitoring**|Monitors the cache ratios, byte hit ratios, HTTP 2xx status codes, HTTP 3xx status codes, HTTP 4xx status code, and HTTP 5xx status codes for accelerated domain names.|-   [DescribeDomainRealTimeReqHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeReqHitRateData.md)
-   [DescribeDomainRealTimeByteHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeByteHitRateData.md)
-   [DescribeDomainRealTimeHttpCodeData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeHttpCodeData.md) |

## Differences between resource monitoring and real-time monitoring

The resource monitoring and real-time monitoring features are different in terms of data collection interval, data delay, and valid time range.

|Feature|Data collection interval|Data delay|Valid time range|
|-------|------------------------|----------|----------------|
|Resource monitoring|5 minutes|About 15 minutes|Within the last 90 days|
|Real-time monitoring|1 minute|About 3 minutes|Within the last 7 days|

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Monitoring & Usage Analytics** \> **Real-time Monitoring**.

3.  On the **Real-time Monitoring** page, select the item and metric that you want to query and click **Search**.

    The system displays monitoring data based on the specified item and query conditions. Then, you can analyze the data.

    ![Real-time monitoring](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9035315261/p231752.png)


