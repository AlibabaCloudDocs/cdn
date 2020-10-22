---
keyword: [query resource usage, CDN/DCDN resource plan]
---

# Query resource usage information

Alibaba Cloud Content Delivery Network \(CDN\) allows you to query resource usage information such as the bandwidth, network traffic, and requests of accelerated domain names. You can query resource usage information within a specific time period to make informed business decisions. This topic describes how to query resource usage information in the Alibaba Cloud CDN console.

You can use the following filter conditions to query specific usage information.

-   Accelerated domain name.
-   Network traffic, bandwidth value, and the number of HTTPS or QUIC requests.
-   Time range. You can select today, yesterday, last 7 days, last 30 days, or specify a custom time range.
-   Region. For more information, see [Pricing of basic services](/intl.en-US/Pricing/Billing method/Pricing of basic services.md).

The Resource Monitoring and Usage pages display usage information that is calculated based on different items. The differences are:

-   The Resource Monitor page displays resource usage information that is summarized based on your Alibaba Cloud account. The resource usage information is collected based on the region \(country, province, or city\) to which the user IP address belongs and their ISP.
-   The Usage page displays resource usage information that is summarized based on CDN nodes. The resource usage information is collected based on the region \(mainland China, North America, or South America\) to which the CDN node belongs.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Monitoring & Usage Analytics** \> **Usage**.

3.  On the **Usage** tab, click **Search**.

    ![Query resource usage information](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9909438951/p8923.png)

    You can set different filter conditions to query specific usage information. For example, you can query bandwidth values, network traffic, and the number of HTTPS or QUIC requests. You can query information by accelerated domain name, time range, and region.

    **Note:** If your CDN service uses the pay-by-95th-percentile billing method, the estimated bandwidth values within the specified time range are returned. The bandwidth monitoring chart displays the estimated bandwidth values that are represented by dotted lines. The estimated values are for reference only, and the actual usage is shown in the bills. The bill of the current month is generated on the first day of the following month.


## Related topics

You can call API operations listed in the following table to export resource usage details.

|API|Description|
|---|-----------|
|[DescribeUserUsageDataExportTask](/intl.en-US/New API Reference/Usage query operations/DescribeUserUsageDetailDataExportTask.md)|Queries export tasks that were created in the last three months. The tasks were used to export resource usage information.|
|[CreateUserUsageDataExportTask](/intl.en-US/New API Reference/Usage query operations/CreateUserUsageDataExportTask.md)|Creates a task to export your resource usage history. The information is exported to a PDF file.|

