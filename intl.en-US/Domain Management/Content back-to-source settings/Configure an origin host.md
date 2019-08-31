# Configure an origin host {#task_261642 .task}

If you want to customize the domain of the server to which CDN initiates back-to-origin requests, you must configure the domain type of the origin host. The domain types available for an origin host are CDN domain, origin domain, and custom domain.

An origin host is the domain of the origin server to which CDN initiates back-to-origin requests.

**Note:** If your origin is bound to multiple domains or servers, you must specify the domain to which the back-to-origin requests are sent. Otherwise, the back-to-origin process fails.

Differences between an origin and an origin host:

-   An origin determines the specific IP address to which CDN initiates back-to-origin requests.
-   An origin host determines the server associated with a specific IP address to which CDN initiates back-to-origin requests.

Default settings for the origin host:

-   If your origin type is **IP**, the default domain type of your origin host is **CDN Domain**.
-   If your origin type is **OSS Domain**, the default domain type of your origin host is **Origin Domain**.

Examples:

-   If your origin is `www.a.com` and your origin host is `www.b.com`, CDN initiates back-to-origin requests to `www.a.com` but the IP address that CDN obtains through IP address resolution is `www.b.com`.
-   If your origin is `1.1.1.1` and your origin host is `www.b.com`, CDN initiates back-to-origin requests to `1.1.1.1`, which maps the `www.b.com` origin server on the host.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Back-to-origin**.
5.  In the **Origin Host** section, click **Modify**.
6.  Turn on **Origin Host**, and set **Domain Type**. 

    ![Back-to-origin configuration](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5145/15672640293347_en-US.png)

7.  Click **OK**.

