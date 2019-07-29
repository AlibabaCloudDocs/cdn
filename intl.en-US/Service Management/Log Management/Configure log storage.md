# Configure log storage {#task_187634 .task}

This topic describes how to configure the CDN log storage service. The log storage service uses Function Compute to store logs for a long time period. You can analyze the logs to get your CDN service quality and client access behavior.

Function Compute must be activated. After CDN is authorized with Function Compute, you can create a Function Compute instance to store logs. Alternatively, you can log on to the [Function Compute console](https://fc.console.aliyun.com) and use an existing Function Compute instance to store logs.

-   The CDN offline log service stores logs for only one month by default. However, you can use the CDN log storage service to store logs to OSS, where logs can be stored for a longer period of time.
-   The log storage service is free of charge. However, you will consume Function Compute resources during the log storage process. As such, you are billed when the amount of Function Compute resources you consume in a month exceeds the specified quota. For more information about Function Compute pricing, see [Function Compute billing methods](https://www.alibabacloud.com/help/doc-detail/54301.htm?spm=a2c63.p38356.b99.147.6eef451elyOlo2).

-   CDN is seamlessly integrated with Function Compute. This allows you to configure functions for processing a wide range of events and receive only the events from the domains with specific name fields. After receiving the specified types of events that meet the filter criteria you have defined, CDN automatically calls the functions to process the events.
-   Function Compute supports such CDN services as log storage, refresh and preload, resource release, domain name addition and deletion, and domain name enabling and disabling. For more information, see [CDN events trigger](https://www.alibabacloud.com/help/doc-detail/73333.htm).


1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **Logs**.
3.  On the Log Management page, click the **Log Storage** tab.
4.  On the **Log Storage** tab page, click **Activate Log Storage**.
5.  In the Authorize and Activate dialog box, enter a service name in the **Service Name** field, select an OSS bucket from the **OSS Bucket** drop-down list, and click **Next**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18641/156437232511014_en-US.png)

6.  Click the **Authorize** button next to **Service Authentication**. Function Compute is authorized to write data to OSS buckets and execute functions.
7.  Click the **Authorize** button next to **Authorize Trigger**. CDN is authorized to access Function Compute.
8.  Select domains and click **Create**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18641/156437232611058_en-US.png)

9.  Click **Done**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18641/156437232611059_en-US.png)


