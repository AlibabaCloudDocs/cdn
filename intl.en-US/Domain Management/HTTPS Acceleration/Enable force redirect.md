# Enable force redirect {#task_261642 .task}

You can enable the Force Redirect function to redirect the original requests from a client to L1 as HTTP or HTTPS requests. This topic describes how to enable the Force Redirect function.

Make sure an HTTPS certificate is configured. For more information, see [Configure HTTPS certificates](reseller.en-US/Domain Management/HTTPS Acceleration/Configure HTTPS certificates.md#).

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the Force Redirect section, click **Modify**. 

    ![Force Redirect](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5136/15665313903708_en-US.png)

5.  In the Force Redirect dialog box that appears, set **Redirect Type**. 

    |Redirect Type|Description|
    |:------------|:----------|
    |**Default**|CDN supports both HTTP and HTTPS requests.|
    |**HTTPS -\> HTTP**|CDN redirects the requests from a client to L1 as HTTP requests.|
    |**HTTP -\> HTTPS**|CDN redirects the requests from a client to L1 as HTTPS requests.|

    Assume that you set Redirect Type to HTTP -\> HTTPS.

    When your client initiates an HTTP request, the server returns a 301 redirect response to redirect the HTTP request as an HTTPS request, as shown in the following figure.

    ![Verify the result](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5136/15665313903707_en-US.png)

6.  Click **OK**.

