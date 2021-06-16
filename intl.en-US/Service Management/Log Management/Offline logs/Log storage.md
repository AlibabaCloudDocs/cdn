---
keyword: log storage
---

# Log storage

The log storage feature of Alibaba Cloud Content Delivery Network \(CDN\) uses Function Compute to deliver log data to Object Storage Service \(OSS\) to retain the log data for a longer period of time. You can further analyze the log data to monitor your CDN service and user behaviors. This allows you to make informed decisions

The log storage feature of Alibaba Cloud CDN integrates with Function Compute to deliver log data. You must activate Function Compute before you can use the log storage feature. After you authorize Alibaba Cloud CDN to access Function Compute, Alibaba Cloud CDN creates a Function Compute service to deliver log data. You can also log on to the [Function Compute console](https://fc.console.aliyun.com) and use an existing Function Compute service to deliver log data.

-   The offline log feature of Alibaba Cloud CDN stores log data for only three months. You can use the log storage feature of Alibaba Cloud CDN to deliver log data to OSS, which retains log data for a longer period of time. This facilitates log storage and analytics.
-   If you need to disable the log storage feature, you must first disassociate the Function Compute service from the domain name in the Alibaba Cloud CDN console. Then, you can delete the Function Compute service in the Function Compute console and delete the data stored in the OSS bucket.
-   Billing: The log storage feature is free of charge. However, Function Compute resources are consumed during the log storage process. You are charged at a lower price rate when the amount of Function Compute resources that are consumed in each month exceeds the specified quota. For more information, see [Function Compute billing methods](https://www.alibabacloud.com/help/doc-detail/54301.htm).
-   Alibaba Cloud CDN is integrated with Function Compute. This allows you to configure functions to process different events and filter events by parameter such as domain name. This way, data can be collected from specific domain names. After the events that meet the filter conditions are received, Alibaba Cloud CDN automatically calls functions to process the events.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Logs**.

3.  On the **Log Management** page, click the **Log Storage** tab.

4.  On the **Log Storage** tab, click **Activate Log Storage**.

5.  In the Authorize and Activate dialog box, enter a service name in the Service Name field, select an OSS bucket from the OSS Bucket drop-down list, and then click **Next**.

    Before you can perform the next step, you must select I understand and agree that fees will be incurred by Function Compute after I activate Log Storage.

    ![Set the parameters in the Select Trigger step](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4886916061/p63361.png)

6.  Click Authorize next to **Service Authentication**.

    On the RAM page, authorize Function Compute to write data to OSS and execute functions.

7.  Click **Authorize** next to Trigger Role.

    On the RAM page, authorize Alibaba Cloud CDN to access Function Compute.

8.  Select one or more domain names to be associated with the Function Compute service and click **Create**.

    ![Select domain names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4886916061/p63249.png)

9.  Click **Done**.

    ![Done](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9019438951/p11059.png)


