# Log storage {#task_187634 .task}

The CDN log storage service uses Function Compute to store logs for an extended period of time. You can analyze the logs to further understand CDN service quality and client access behavior. This can help you make more informed decisions.

-   The CDN offline log service stores logs for only one month. You can use the CDN log storage service to store logs to OSS, where logs can be stored for a longer period of time. This facilitates log storage and analysis.
-   -   CDN is seamlessly integrated with Function Compute. This allows you to configure functions for processing a wide range of events and receive only events from the domains with specific name fields. After receiving events that meet the filtering criteria, CDN automatically calls functions to process the events.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Logs**.
3.  On the Log Management page, click the Log Storage tab.
4.  On the Log Storage tab, click **Activate Log Storage**.
5.  In the Authorize and Activate dialog box, enter a service name in the **Service Name** field, select an OSS bucket from the **OSS Bucket** drop-down list, and click **Next**. 

    Before you click Next, select the check box to agree that fees will be incurred by Function Compute after activating Log Storage.

    ![Select trigger](http://icms-static-translation.oss-cn-hangzhou.aliyuncs.com/SP_19/DNCDN11828177/images/11014_zh-CN.png?Expires=1565490623&OSSAccessKeyId=LTAIJfoPL6wmrirR&Signature=A3xw9ZkgKD8GhmnOMcmJFE68TlA%3D)

6.  Click the **Authorize** button next to Service Authentication. On the RAM page, authorize Function Compute to write data to OSS and execute functions.
7.  Click the **Authorize** button next to Authorize Trigger. On the RAM page, authorize CDN to access Function Compute.
8.  Select domains and click **Create**. 

    ![Select domains](http://icms-static-translation.oss-cn-hangzhou.aliyuncs.com/SP_19/DNCDN11828177/images/11058_zh-CN.png?Expires=1565490624&OSSAccessKeyId=LTAIJfoPL6wmrirR&Signature=BljLxtYJINRB%2BDIe8Epijo1LXXw%3D)

9.  Click **Done**. 

    ![Done](http://icms-static-translation.oss-cn-hangzhou.aliyuncs.com/SP_19/DNCDN11828177/images/11059_zh-CN.png?Expires=1565490624&OSSAccessKeyId=LTAIJfoPL6wmrirR&Signature=nKYIKcAXuAXjQ7kHi%2BQBPvhdMek%3D)


