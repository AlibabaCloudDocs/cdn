---
keyword: export billing details
---

# Export billing details

Alibaba Cloud Content Delivery Network \(CDN\) allows you to create tasks to export billing details. You can also download exported billing details and save them to an Excel file. Billing details help you control your expenses. This topic describes how to export and download billing details.

You can export billing details by traffic and bandwidth, request, account, domain name, or resource group. This allows you to check and calculate your expenses.

The billing details of each billable item are collected every five minutes.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Monitoring & Usage Analytics** \> **Usage**.

3.  On the Usage page, click the **Details Export** tab.

4.  On the **Details Export** tab, click **Create Task**.

5.  Set the export task parameters based on your business requirements.

    |Parameter|Description|
    |---------|-----------|
    |**Task Name**|The name of the export task.|
    |**Data Type**|The type of data that you want to export. Valid values:     -   Traffic/Bandwidth
    -   Requests |
    |**Query Period**|The beginning and end of the time range to export the billing details. You can export data of up to the last 31 days in each task. Specify the time in the YYYY-MM-DD HH:mm:ss format.|
    |**Export Content**|The content that you want to export. Valid values:     -   Account
    -   Domain
    -   Group |
    |**Domain Name**|If you set **Export Content** to **Domain**, you must select an accelerated domain name. You can select up to 100 accelerated domain names for each export task.|
    |**Please select group**|If you set **Export Content** to **Group**, you must select a resource group. After you select a group, billing details of all domain names in the resource group are exported. You can select up to 100 resource groups for each export task.|

    ![Export billing details](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4345136061/p63478.png)

6.  Click **OK**.

7.  After you create an export task, you can click **Download** or **Delete** in the Actions column to download or delete exported billing details.


## API operations

You can call API operations listed in the following table to export billing details.

|API|Description|
|---|-----------|
|[DescribeUserUsageDetailDataExportTask](/intl.en-US/New API Reference/Usage query operations/DescribeUserUsageDetailDataExportTask.md)|Queries tasks that were used to export resource usage details of one or more accelerated domain names under your Alibaba Cloud account. Resource usage information is collected every five minutes within a specific time range.|
|[CreateUsageDetailDataExportTask](/intl.en-US/New API Reference/Usage query operations/CreateUsageDetailDataExportTask.md)|Creates a task to export the resource usage details. Usage details are exported to an Excel file.|

