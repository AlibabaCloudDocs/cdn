---
keyword: [statistical analysis, CDN]
---

# Statistical analysis

Alibaba Cloud Content Delivery Network \(CDN\) provides statistics of your CDN service. You can query performance data within a specified time range by domain name. You can also export the data to a table. This allows you to monitor the performance of domain names accelerated by Alibaba Cloud CDN and make informed business decisions.

## Overview

Statistical analysis includes the following items. You can query data of each item from the last day to the last 90 days. You can specify a time range based on business requirements. You can export the raw data and perform analytics as needed.

**Note:**

-   The collection interval of the raw data varies based on the specified time range. If you export data by day, the data is collected every 300 seconds. If you export data by week, the data is collected every 3,600 seconds. If you export data by month, the data is collected every 14,400 seconds.
-   Data is collected and calculated by calling API operations. For more information, see the API references. The statistics are for reference only. The result may be different from the log data due to algorithms and limits. The actual log data prevails.

|Item|Description|API reference|
|----|-----------|-------------|
|**PV/UV**|Allows you to query page views \(PV\) and unique visitors \(UV\) of accelerated domain names by time.|-   [DescribeDomainPvData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainPvData.md)
-   [DescribeDomainUvData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainUvData.md) |
|**Top Client IPs**|Displays top client IP addresses based on specified query conditions. Ranking by traffic or number of requests is supported.|[DescribeDomainTopClientIpVisit](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainTopClientIpVisit.md)|
|**By Region/Provider**|Allows you to query the proportions of requests initiated through each ISP, total amount of data transfer, proportions of data transfer through each ISP, bandwidth values, number of requests, proportions of requests initiated through each ISP, and average response time within a specified time range in regions inside or outside mainland China.|-   [DescribeDomainISPData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainISPData.md)
-   [DescribeDomainRegionData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRegionData.md) |
|**Popular Referers**|Displays the amount of data transfer, data transfer proportions, number of visits, and visit proportions of popular referer headers.|[DescribeDomainTopReferVisit](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainTopReferVisit.md)|
|**Popular URLs**|Displays popular URLs based on specified query conditions. Queries by HTTP status code are supported. **Note:** The end time must be later than the start time. The time span between the start and end time must not exceed seven days.

|[DescribeDomainTopUrlVisit](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainTopUrlVisit.md)|
|**Popular Back-to-origin URLs**|Displays popular back-to-origin URLs based on specified query conditions. Queries by HTTP status code are supported. **Note:** The end time must be later than the start time. The time span between the start and end time must not exceed seven days.

|[DescribeDomainSrcTopUrlVisit](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainSrcTopUrlVisit.md)|
|**Domain Name Ranking \(Upgrading\)**|Displays the rank, amount of data transfer, data transfer proportions, peak bandwidth values, time of peak bandwidth values, and number of visits for each accelerated domain name.|[DescribeTopDomainsByFlow](/intl.en-US/New API Reference/Data monitoring operations/DescribeTopDomainsByFlow.md)|

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Monitoring & Usage Analytics** \> **Statistics**.

3.  On the **Statistics** tab, select the item that you want to query, set the query conditions, and then click **Search**.

    Data of the specified item is filtered and displayed based on the specified query conditions. You can analyze the data in the console, or export the data and then perform analytics.

    ![Statistical analysis](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1654651161/p63175.png)


