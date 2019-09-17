# Log storage {#task_187634 .task}

The CDN log storage service uses Function Compute to store logs for an extended period of time. You can analyze the logs to further understand CDN service quality and client access behavior. This can help you make more informed decisions.

The CDN log storage service uses Function Compute to store logs. You must activate Function Compute before you can use the log storage service. After you authorize CDN to access Function Compute, CDN creates a Function Compute instance to store logs. You can also log on to the [Function Compute console](https://fc.console.aliyun.com) and use an existing Function Compute instance to store logs.

-   The CDN offline log service stores logs for only one month. You can use the CDN log storage service to store logs to OSS, where logs can be stored for a longer period of time. This facilitates log storage and analysis.
-   Billing: The log storage service is free of charge. However, you will consume Function Compute resources during the log storage process. You are charged when the amount of Function Compute resources consumed in each month exceeds the specified quota. For more information about Function Compute pricing, see [Function Compute billing methods](https://www.alibabacloud.com/help/doc-detail/54301.htm).

-   CDN is seamlessly integrated with Function Compute. This allows you to configure functions for processing a wide range of events and receive only events from the domains with specific name fields. After receiving events that meet the filtering criteria, CDN automatically calls functions to process the events.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).
2.  In the left-side navigation pane, click **Logs**.
3.  On the Log Management page, click the Log Storage tab.
4.  On the Log Storage tab, click **Activate Log Storage**.
5.  In the Authorize and Activate dialog box, enter a service name in the **Service Name** field, select an OSS bucket from the **OSS Bucket** drop-down list, and click **Next**. 

    Before you click Next, select the check box to agree that fees will be incurred by Function Compute after activating Log Storage.

    ![](images/11014_en-US_source.png)

6.  Click the **Authorize** button next to Service Authentication. On the RAM page, authorize Function Compute to write data to OSS and execute functions.
7.  Click the **Authorize** button next to Authorize Trigger. On the RAM page, authorize CDN to access Function Compute.
8.  Select domains and click **Create**. 

    ![](images/11058_en-US_source.png)

9.  Click **Done**. 

    ![](images/11059_en-US_source.png)


## API {#example_q6q_p33_swv .example}

You can call API operations listed in the following table to implement the log storage function.

|Operation|Description|
|---------|-----------|
|[DescribeCustomLogConfig](../intl.en-US/New API Reference/Log operations/DescribeCustomLogConfig.md#)| |
|[DescribeDomainCustomLogConfig](../intl.en-US/New API Reference/Log operations/DescribeDomainCustomLogConfig.md#)| |
|[ListDomainsByLogConfigId](../intl.en-US/New API Reference/Log operations/ListDomainsByLogConfigId.md#)| |
|[ListUserCustomLogConfig](../intl.en-US/New API Reference/Log operations/ListUserCustomLogConfig.md#)| |
| | |

