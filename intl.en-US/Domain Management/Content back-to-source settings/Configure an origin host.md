# Configure an origin host {#task_261642 .task}

This topic describes how to configure the origin host of a domain. You can customize the domain name of the server to which CDN routes back-to-origin requests.

An origin host is the domain of the origin server to which CDN routes back-to-origin requests. It determines the IP address to which CDN routes back-to-origin requests. An origin host also determines the server associated with a specific IP address to which CDN routes back-to-origin requests.

**Note:** 

-   If your origin is associated with multiple domains or servers, you must specify a domain for receiving back-to-origin requests.
-   If you do not specify a domain, back-to-origin requests cannot be routed.

The differences between an origin and an origin host are as follows:

-   An origin determines the IP address to which CDN routes back-to-origin requests.
-   An origin host determines the server associated with a specific IP address to which CDN routes back-to-origin requests.

The domain types available for an origin host are **CDN Domain**, **Origin Domain**, and **Custom Domain**:

-   If your origin type is **IP**, the default domain type of your origin host is **CDN Domain**.
-   If your origin type is **OSS Domain**, the default domain type of your origin host is **Origin Domain**.

Examples:

-   If your origin is `www.a.com` and your origin host is `www.b.com`, CDN routes back-to-origin requests to `www.a.com` but the IP address that CDN obtains through IP address resolution is `www.b.com`.
-   If your origin is `1.1.1.1` and your origin host is `www.b.com`, CDN routes back-to-origin requests to `1.1.1.1`, which maps the `www.b.com` origin server on the host.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the domain you want to set, and in the **Actions** column click **Manage**.
4.  In the left-side navigation pane, click **Back-to-origin**.
5.  Click the **Back-to-origin Configurations** tab and in the **Origin Host** section click **Modify**.
6.  Turn on the **Origin Host** switch, select a domain type, and click **OK**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5145/15639619753347_en-US.png)


