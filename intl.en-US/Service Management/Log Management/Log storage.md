---
keyword: log storage
---

# Log storage

The log storage service of Alibaba Cloud Content Delivery Network \(CDN\) uses Function Compute to deliver logs to Object Storage Service \(OSS\) for a longer retention period of the logs. You can further analyze the log data to understand your CDN service quality and user behaviors. This allows you to make informed decisions

The log storage service of Alibaba Cloud CDN integrates with Function Compute to deliver logs. You must activate Function Compute before you can use the log storage service. After you authorize Alibaba Cloud CDN to access Function Compute, Alibaba Cloud CDN creates a Function Compute service to deliver logs. You can also log on to the [Function Compute console](https://fc.console.aliyun.com) and use an existing Function Compute service to deliver logs.

-   You can use the log storage service of Alibaba Cloud CDN to deliver logs to OSS, where logs can be stored for a longer period of time. This facilitates log storage and analysis.
-   To disable the log storage service, perform the following steps: Disassociate the accelerated domain name from the log storage service in the Alibaba Cloud CDN console, delete the log service configuration in the Function Compute console, and then delete the data of the bucket in the OSS console.
-   Billing: The log storage service is free of charge. However, Function Compute resources are consumed during the log storage process. You are charged at a lower price rate when the amount of Function Compute resources that are consumed in each month exceeds the specified quota. For more information about Function Compute pricing, see [Function Compute billing methods](https://www.alibabacloud.com/help/doc-detail/54301.htm).

-   Alibaba Cloud CDN is integrated with Function Compute. This allows you to configure functions to process different events and filter events by parameter such as domain name. This way, data can be collected from specific domain names. After the events that meet the filter conditions are received, Alibaba Cloud CDN automatically calls functions to process the events.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Logs**.

3.  On the **Log Management** page, click the **Log Storage** tab.

4.  On the **Log Storage** tab, click **Activate Log Storage**.

5.  In the Authorize and Activate dialog box, enter a service name in the Service Name field, select an OSS bucket from the OSS Bucket drop-down list, and then click **Next**.

    Before you can perform the next step, you must select I understand and agree that fees will be incurred by Function Compute after I activate Log Storage.

    ![Set the parameters in the Select Trigger step](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4886916061/p63361.png)

6.  Click **Authorize** next to Service Authentication.

    You are redirected to the **Role Templates** page in the Resource Access Management \(RAM\) console. Then, configure an authorization policy to authorize Function Compute to write data to OSS and execute functions.

7.  Click **Authorize** next to Trigger Role.

    On the **RAM** page, authorize Alibaba Cloud CDN to access Function Compute.

8.  Select one or more domain names to be associated with the Function Compute service and click **Create**.

    ![Select domain names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4886916061/p63249.png)

9.  Click **Done**.

    ![Done](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9019438951/p11059.png)


