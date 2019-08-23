# Configure bandwidth cap {#task_187634 .task}

The bandwidth cap feature specifies the maximum bandwidth for a domain name. When the average bandwidth measured during each statistical cycle \(five minutes\) exceeds the specified maximum bandwidth, your domain name will automatically go offline to protect itself. All requests will be redirected to the origin server, and CDN will stop acceleration services to avoid excessive fees produced by abnormal traffic. After your domain name goes offline, you can re-enable it in the console. This topic describes how to enable the bandwidth cap feature and related precautions.

When you configure the bandwidth cap feature, take note of the following points:

-   If you intend to enable this feature by using a RAM user account, you must log on to the [RAM console](https://ram.console.aliyun.com/permissions) to create the AliyunCDNFullAccess policy. This policy grants the RAM user account permission to manage CDN.
-   This feature is not applicable to wildcard domain names. Even if you set this feature for a wildcard domain name, this feature does not take effect.
-   After you enable this feature, your services may go offline due to the bandwidth cap. To ensure that your domain name can provide normal services, we recommend you set the maximum bandwidth based on a reasonable estimation.
-   If your CDN service goes offline due to the bandwidth cap, you can go to the Domain Names page in the CDN console, select the check box corresponding to the domain name, and then click **Enable**.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Advanced**.
5.  In the Bandwidth Cap section, click **Modify**.
6.  Turn on **Bandwidth Cap** to set the maximum bandwidth. 

    ![Bandwidth cap](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5175/156653407932303_en-US.png)

    **Note:** 

    -   You can only specify units at intervals of 1000. For example, 1 Tbit/s is equal to 1000 Gbit/s, and 1 Gbit/s is equal to 1000 Mbit/s.
    -   You can choose to enable or disable this feature based on the actual usage of your domain name.
    -   If this feature is being upgraded, you cannot enable it.
7.  Click **OK**.

