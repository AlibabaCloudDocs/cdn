---
keyword: [statistical analysis, CDN]
---

# Statistical analysis

Alibaba Cloud Content Delivery Network \(CDN\) provides statistics for your CDN service. You can query performance data within the last day or a custom time range by domain name. This allows you to monitor the performance of your CDN service.

The following metrics are collected: page view \(PV\), unique visitor \(UV\), top N client IP addresses, region, Internet service provider \(ISP\), top N referer headers, frequently requested URLs, top N back-to-origin URLs, and frequently visited domain names. You can export detailed raw data such as network bandwidth, network traffic, domain name ranked by traffic proportion, and request distribution by visitor or ISP.

**Note:** The time interval at which raw data is collected varies based on the specified time range. If you export data by day, the data is collected every 300 seconds. If you export data by week, the data is collected every 3,600 seconds. If you export data by month, the data is collected every 14,400 seconds.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Monitoring & Usage Analytics** \> **Statistics**.

3.  On the **Statistics** page, select the monitoring item and metric that you want to query and click **Search**.

    ![Statistical analysis](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8494136061/p63175.png)

    |Item|Metric|Supported time range|
    |:---|:-----|:-------------------|
    |**PV/UV**|PV, UV, user distribution by region, and PV and UV proportion distributed by ISP.|Yesterday, last 7 days, last 30 days, and a custom time range that is within the last 90 days.|
    |**Top Client IPs**|Network traffic and the number of requests.|Yesterday, last 7 days, last 30 days, and a custom time range that is within the last 90 days.|
    |**By Region/Provider**|Ranking, region, total traffic, total traffic proportion distributed by region or ISP, number of visits, visit proportion distributed by region or ISP, and response time|Yesterday, last 7 days, last 30 days, and a custom time range that is within the last 90 days.|
    |**Popular Referers**|Traffic, traffic proportion distributed by URL, number of visits, and visit proportion distributed by referer|Yesterday and a specified day that is within the last 90 days.|
    |**Popular URLs**|Traffic, traffic proportion distributed by URL, number of visits, and visit proportion distributed by referer header.|Yesterday and a specified day that is within the last 90 days. **Note:** The data is collected from the top 100 most requested URLs within every minute and based on the network traffic of and number of visits to the selected domain name. The data returned to you includes both the preceding data and the network traffic or number of requests within the queried time range. The data of each metric is returned separately. The returned data may not include log data of all requested URLs because the data is collected from only the top 100 most requested URLs. The data is also separated by network traffic and the number of requests. Therefore, the data of most requested URLs may be slightly different from the actual data. The data is for reference only. It takes a long time to retrieve data from the access log. If you require completely accurate data, we recommend that you query data from the access log on the Log Download tab. You can then use the data to produce more accurate analysis results. For more information, see [Download logs](/intl.en-US/Service Management/Log Management/Download logs.md). |
    |**Popular Back-to-origin URLs**|Traffic, traffic proportion distributed by URL, number of visits, and visit proportion distributed by referer header.|Yesterday and a specified day that is within the last 90 days.|
    |**Domain Name Ranking**|Request ranking, traffic, traffic proportion distributed by domain, peak bandwidth values, peak hours, and number of visits to each domain name.|Yesterday, last 7 days, last 30 days, and a custom time range that is within the last 90 days.|


