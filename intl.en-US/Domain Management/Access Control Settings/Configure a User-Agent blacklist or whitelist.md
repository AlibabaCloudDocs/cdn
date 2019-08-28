# Configure a User-Agent blacklist or whitelist {#task_371735 .task}

You can configure a User-Agent blacklist or whitelist to identify and filter visitors, restricting access to CDN resources and improving CDN security. This topic describes how to configure a User-Agent blacklist or whitelist.

If you want to implement access control based on the User-Agent field, you must configure a User-Agent blacklist or whitelist to filter requests.

-   User-Agent blacklist: The User-Agent fields on the blacklist cannot be used to access resources.

    If your User-Agent field is added to the blacklist, a request with the User-Agent field can still be sent to a CDN node. However, the request will be rejected by the CDN node, and a 403 error will be returned. Requests that contain the User-Agent fields on the blacklist are still recorded in CDN logs.

-   User-Agent whitelist: Only User-Agent fields on the whitelist can be used to access resources.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Access Control**.
5.  Click **UserAgent Blacklist/Whitelist**.
6.  On the UserAgent Blacklist/Whitelist tab, click **Modify**. 

    ![User-Agent blacklist or whitelist](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301857/156698432350946_en-US.png)

7.  Configure **Blacklist** or **Whitelist** as prompted. 

    |Parameter|Description|
    |---------|-----------|
    |Type| The following two types are supported:

    -   Blacklist

The User-Agent fields on the blacklist cannot be used to access resources.

    -   Whitelist

Only User-Agent fields on the whitelist can be used to access resources.

 The blacklist and whitelist are mutually exclusive. Only either of them can take effect at any time.

 |
    |Rules|When you configure the User-Agent field, use vertical bars \(|\) to separate multiple values. The User-Agent field can contain wildcards \(\*\). For example, \*curl\*|\*IE\*|\*chrome\*|\*firefox\*.|

8.  Click **OK**.

