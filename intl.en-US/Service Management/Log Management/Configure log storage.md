# Configure log storage {#task_187634 .task}

This topic describes how to configure the CDN log storage service. The log storage service uses Function Compute to store logs for a long time period. You can analyze the logs to get your CDN service quality and client access behavior.

-   The CDN offline log service stores logs for only one month by default. However, you can use the CDN log storage service to store logs to OSS, where logs can be stored for a longer period of time.
-   -   CDN is seamlessly integrated with Function Compute. This allows you to configure functions for processing a wide range of events and receive only the events from the domains with specific name fields. After receiving the specified types of events that meet the filter criteria you have defined, CDN automatically calls the functions to process the events.
-   
1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Logs**.
3.  On the Log Management page, click the **Log Storage** tab.
4.  On the **Log Storage** tab page, click **Activate Log Storage**.
5.  In the Authorize and Activate dialog box, enter a service name in the **Service Name** field, select an OSS bucket from the **OSS Bucket** drop-down list, and click **Next**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18641/156437225511014_en-US.png)

6.  Click the **Authorize** button next to **Service Authentication**. Function Compute is authorized to write data to OSS buckets and execute functions.
7.  Click the **Authorize** button next to **Authorize Trigger**. CDN is authorized to access Function Compute.
8.  Select domains and click **Create**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18641/156437225511058_en-US.png)

9.  Click **Done**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18641/156437225511059_en-US.png)


