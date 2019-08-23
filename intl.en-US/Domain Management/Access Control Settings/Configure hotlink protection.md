# Configure hotlink protection {#task_187634 .task}

You can configure a referer blacklist or whitelist to identify and filter users, restricting access to CDN resources and improving CDN security. This topic describes how to configure hotlink protection.

-   Hotlink protection is implemented by the HTTP referer mechanism. Referer is used to track and identify where requests come from.
-   Hotlink protection enables you to configure a blacklist or whitelist. After you send a request to access resources, the request is directed to a CDN node. The CDN node will filter users based on the configured blacklist or whitelist. If the domain names of users are whitelisted, users can access the requested resources. If the domain names of users are blacklisted, users cannot access the requested resources, and a 403 error is returned.

**Note:** 

-   Hotlink protection is optional. By default, hotlink protection is disabled.
-   The blacklist and whitelist are mutually exclusive. Only either of them can take effect at any time.
-   After hotlink protection is configured, CDN automatically adds a wildcard \(\*\) to domain names. For example, if you enter a.com, the domain name will be configured as \*.a.com. Hotlink protection takes effect on all the subdomains of a.com.
-   You can specify whether to allow requests with an empty referer header to access CDN resources. You can access CDN resources by entering a URL into a web browser.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Access Control**.
5.  In the Hotlinking Protection section, click **Modify**. 

    ![Modify configurations](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5151/15665317927279_en-US.png)

6.  Configure **Blacklist** or **Whitelist** as prompted. 

    |Parameter|Description|
    |---------|-----------|
    |Type| The following two types are supported:

    -   Blacklist

Blacklisted domain names cannot be used to access CDN resources.

    -   Whitelist

Only whitelisted domain names can be used to access CDN resources.

 The blacklist and whitelist are mutually exclusive. Only either of them can take effect at any time.

 |
    |Rules|Separate multiple domain names in a referer blacklist or whitelist with carriage return characters. You can use wildcards \(\*\) to perform fuzzy matching. For example, a.\*b.com can match a.aliyun.b.com or a.img.b.com.|

7.  Click **OK**.

