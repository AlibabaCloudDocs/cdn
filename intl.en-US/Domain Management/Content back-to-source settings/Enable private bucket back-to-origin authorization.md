# Enable private bucket back-to-origin authorization {#task_187634 .task}

If your origin is Alibaba Cloud OSS, you can grant permissions to CDN domains to access the private OSS bucket to prevent resource hotlinking. This topic describes how to enable private bucket back-to-origin authorization.

You can use functions such as the referer hotlink protection and authentication provided by Alibaba Cloud CDN to protect resource security. For more information, see [Configure hotlink protection](reseller.en-US/Domain Management/Access control/Configure hotlink protection.md#) and [Configure URL authentication](reseller.en-US/Domain Management/Access control/Business type/Configure URL authentication.md#).

**Note:** 

-   Only CDN domains that use OSS as the origin are allowed to enable private bucket back-to-origin authorization.
-   Once back-to-origin authorization is performed, CDN is granted the read-only permissions to access all your buckets.
-   After back-to-origin authorization is performed and enabled for a specific CDN domain, the domain can access the resource content in your private bucket. Use caution when you decide whether to enable this function. If the content in the private bucket to be authorized is not suitable to function as the back-to-origin content of the CDN domain, do not perform authorization or enable the function.
-   If your website is at risk of attacks, note the following precautions:
    -   Make sure that you purchase Anti-DDoS Pro.
    -   Make sure that you do not perform or enable private bucket back-to-origin authorization.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Back-to-origin**.
5.  In the Private Bucket Access section, click **Authorize**. 

    ![Authorization confirmation](images/52546_en-US.png)

6.  Click **Confirm**. 

    ![Confirm](images/45826_en-US.png)

7.  In the Private Bucket Access section, turn on Private Bucket Access. For more information, see [Disable private bucket back-to-origin authorization](reseller.en-US/Domain Management/Content back-to-source settings/Disable private bucket back-to-origin authorization.md#).

