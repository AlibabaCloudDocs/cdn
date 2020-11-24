---
keyword: log storage
---

# Log storage

The log storage service of Alibaba Cloud Content Delivery Network \(CDN\) uses Function Compute to deliver logs to Object Storage Service for a longer retention period of the logs. You can analyze the log data to further understand your CDN service quality and user behaviors. This helps you make informed decisions.

The log storage service of Alibaba Cloud CDN integrates with Function Compute to deliver logs. You must activate Function Compute before you can use the log storage service. After you authorize Alibaba Cloud CDN to access Function Compute, Alibaba Cloud CDN creates a Function Compute service to deliver logs. You can also log on to the [Function Compute console](https://fc.console.aliyun.com) and use an existing Function Compute service to deliver logs.

-   The offline log service of Alibaba Cloud CDN stores logs for only one month. You can use the log storage service of Alibaba Cloud to deliver logs to OSS, where logs can be stored for a longer period of time. This facilitates log storage and analysis.
-   Billing: The log storage service is free of charge. However, you will consume Function Compute resources during the log storage process. You are charged at a lower price rate when the amount of Function Compute resources consumed in each month exceeds the specified quota. For more information about Function Compute pricing, see [Function Compute billing methods](https://www.alibabacloud.com/help/doc-detail/54301.htm).

-   Alibaba Cloud CDN is seamlessly integrated with Function Compute. This allows you to configure functions for processing different events and filter events by parameter such as domain name to collect data from specific domain names. After receiving events that meet the filter conditions, Alibaba Cloud CDN automatically calls functions to process the events.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Logs**.

3.  On the **Log Management** page, click the **Log Storage** tab.

4.  On the **Log Storage** tab, click **Activate Log Storage**.

5.  In the Authorize and Activate dialog box, enter a service name in the Service Name field, select an OSS bucket from the OSS Bucket drop-down list, and then click **Next**.

    You must select I understand and agree that fees will be incurred by Function Compute after I activate Log Storage before you can perform the next step.

    ![Set the parameters on the Select Trigger page](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4886916061/p63361.png)

6.  Click **Authorize** next to Service Authentication.

    On the RAM page, authorize Function Compute to write data to OSS and execute functions.

7.  Click **Authorize** next to Authorize Trigger.

    On the RAM page, authorize Alibaba Cloud CDN to access Function Compute.

8.  Select domain names to be associated with the Function Compute service and click **Create**.

    ![Select domain names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4886916061/p63249.png)

9.  Click **Done**.

    ![The service is created](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9019438951/p11059.png)


## Call an API operation to use the log storage service.

You can call API operations listed in the following table to use the log storage service.

|API|Description|
|---|-----------|
|[DescribeCustomLogConfig](/intl.en-US/New API Reference/Log operations/DescribeCustomLogConfig.md)|Queries the detailed information about a custom log configuration.|
|[DescribeDomainCustomLogConfig](/intl.en-US/New API Reference/Log operations/DescribeDomainCustomLogConfig.md)|Queries the custom log configuration of an accelerated domain name.|
|[ListDomainsByLogConfigId](/intl.en-US/New API Reference/Log operations/ListDomainsByLogConfigId.md)|Queries all accelerated domain names associated with a custom log configuration.|
|[ListUserCustomLogConfig](/intl.en-US/New API Reference/Log operations/ListUserCustomLogConfig.md)|Queries all custom log configurations under your account.|

