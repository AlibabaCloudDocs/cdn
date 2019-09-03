# Query bills {#task_423040 .task}

You can query CDN bills by day or by month as needed. CDN supports billing by data traffic, by value-added services, or by real-time log entries. You can query CDN bills to understand the billing details in a timely manner and make better business decisions. This topic describes how to query bills.

When you query bills, note the following:

-   Query by day

    You can query bills only for the current day or the previous 355 days. For example, the billing cycle can be from 2019-07-08 00:00:00 to 2019-07-08 23:59:59.

-   Query by month

    You can query bills only for the previous 12 months. For example, the billing cycle can be from 2019-06-01 00:00:00 to 2019-06-30 23:59:59.


1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).
2.  In the left-side navigation pane, click **Usage**.
3.  Click the Bill Query tab.
4.  On the Bill Query tab, select **Select Date** or **Select Month**, set a specific time range, and then click **Search**. 

    ![Query a bill](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/341856/156749339651215_en-US.png)

    For more information about how to export bills or details, see [Export a bill](intl.en-US/Service Management/Usage Query/Export a bill.md#) or [Export details](intl.en-US/Service Management/Usage Query/Export details.md#).


## API operations {#example_p66_wgi_f2m .example}

You can call the API to query the bill of a CDN domain for a specific billing cycle. For more information, see [DescribeDomainUsageData](../intl.en-US/New API Reference/Usage query operations/DescribeDomainUsageData.md#).

