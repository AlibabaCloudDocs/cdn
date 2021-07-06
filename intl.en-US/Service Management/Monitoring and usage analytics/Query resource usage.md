---
keyword: [query resource usage, CDN/DCDN resource plan]
---

# Query resource usage

Alibaba Cloud Content Delivery Network \(CDN\) allows you to query resource usage and resource billing details in mainland China or in other billable regions. You can query network traffic, bandwidth values, the number of requests, and the number of log entries that are delivered to a specified location in real time. You can export billing details about all billable items by day or by month, and resource usage details about accelerated domain names in each billable region that are collected every 5 minutes. These details help you monitor the billable items and resource usage of Alibaba Cloud CDN.

## Overview

You can perform the following operations to query resource usage or billing details based on specified query conditions.

|Operation|Description|API references|
|---------|-----------|--------------|
|**Usage**|Allows you to query resource usage of accelerated domain names. You can set different filter conditions to query specific usage information. For example, you can query bandwidth values, network traffic, and the number of HTTPS or QUIC requests. You can query information by accelerated domain name, time range, and billable region. **Note:** If the metering method is pay-by-95th-percentile-bandwidth per month, the system displays the estimated 95th percentile bandwidth values within the specified time range. The estimated bandwidth values are represented by a dotted line in the bandwidth chart. The estimated bandwidth values are for reference only. The actual bandwidth values in the bills that are issued on the first day of each month shall prevail. The bill of the current month is issued on the first day of the next month.

|[DescribeDomainUsageData](/intl.en-US/New API Reference/Usage query operations/DescribeDomainUsageData.md)|
|**Bill Query**|Allows you to query bills of Alibaba Cloud CDN by day or by month. The billable items include data transfer, real-time log delivery, value-added services, and QUIC requests. -   Query bills by day

You can query bills generated on the current day or within the last 355 days. For example, the billing cycle can be from 00:00:00 \(UTC+8\) on July 8, 2019 to 23:59:59 \(UTC+8\) on July 8, 2019.

-   Query bills by month

You can query bills generated in the current month or within the last 11 months. For example, the billing cycle can be from 00:00:00 \(UTC+8\) on June 1, 2019 to 23:59:59 \(UTC+8\) on June 30, 2019.


|[DescribeCdnUserBillHistory](/intl.en-US/New API Reference/Usage query operations/DescribeCdnUserBillHistory.md)|
|**Bill Export**|Allows you to export bills of Alibaba Cloud CDN by day or by month. You can export billing details to a PDF file, and check the billing details in the PDF file.|-   [CreateUserUsageDataExportTask](/intl.en-US/New API Reference/Usage query operations/CreateUserUsageDataExportTask.md)
-   [DescribeUserUsageDataExportTask](/intl.en-US/New API Reference/Usage query operations/DescribeUserUsageDataExportTask.md) |
|**Details Export**|Allows you to create tasks to export billing details. You can export billing details within the last 31 days. After a task is created, it exports billing details to a file on your on-premises computer. The billing details of each billable item are collected every 5 minutes. The billing details are export to an EXCEL file. You can check the billable items and the billing details to ensure that the fees are correctly calculated.

|-   [CreateUsageDetailDataExportTask](/intl.en-US/New API Reference/Usage query operations/CreateUsageDetailDataExportTask.md)
-   [DescribeUserUsageDetailDataExportTask](/intl.en-US/New API Reference/Usage query operations/DescribeUserUsageDetailDataExportTask.md) |
|**Resource Plans**|Allows you to query details about resource plans. You can query the total capacity, remaining capacity, effective time, expiration time, and status of each resource plan.|[DescribeCdnUserResourcePackage](/intl.en-US/New API Reference/Service management operations/DescribeCdnUserResourcePackage.md)|

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Monitoring & Usage Analytics** \> **Usage**.

3.  On the **Usage** page, select the item and set the query conditions.

    The system displays data based on the specified item and query conditions.

    ![Query resource usage](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5378191161/p8923.png)


