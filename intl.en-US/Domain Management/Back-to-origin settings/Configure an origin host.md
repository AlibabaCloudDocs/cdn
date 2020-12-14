---
keyword: [origin host, back-to-origin requests]
---

# Configure an origin host

If you want to customize the domain name of the server to which Alibaba Cloud CDN initiates back-to-origin requests, you must first configure the domain type of the origin host. The origin host supports the following domain name types: accelerated domain name, origin domain name, and custom domain name.

An origin host is the domain name of the origin server to which Alibaba Cloud CDN initiates back-to-origin requests. If the origin server is shared by multiple content delivery services, each back-to-origin request can include a different origin host to specify the required content delivery service.

**Note:** If the origin server is associated with multiple domain names or sites, you must specify a custom domain name to which the back-to-origin requests are sent. Otherwise, the back-to-origin process fails.

Differences between an origin server and an origin host:

-   An origin server defines a specific IP address to which back-to-origin requests are redirected.
-   An origin host defines a specific site that is hosted on a specific IP address. Back-to-origin requests are redirected to the IP address.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  In the **Origin Host** section, click **Modify**.

6.  Turn on **Origin Host** and set **Domain Type**.

    ![Back-to-origin configuration](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5699197061/p64119.png)

    |Parameter|Description|
    |---------|-----------|
    |**CDN Domain**|This option specifies an accelerated domain name. Clients access this domain name to accelerate content delivery by using Alibaba Cloud CDN. For example, `cdntest.com` can be specified. If you set Domain Type to **CDN Domain**, an accelerated domain name is specified as the origin host, for example, `cdntest.com`.|
    |**Origin Domain**|This option specifies the domain name of an origin server. To retrieve content from the origin server, Alibaba Cloud CDN must access this domain name. For example, `origin.com` can be specified. If you set Domain Type to **Origin Domain**, the domain name of an origin server is specified as the origin host, for example, `origin.com`.|
    |**Custom Domain**|If you set Domain Type to **Custom Domain**, a custom domain name is specified as the origin host. If the origin server is associated with multiple domain names, you must specify a domain name to which the back-to-origin requests are sent. Otherwise, the back-to-origin process fails.|

    |Example|Origin information|Feature status|Domain name|Description|
    |-------|------------------|--------------|-----------|-----------|
    |Example 1|Domain name|By default, the Origin Host feature is disabled.|Accelerated domain name: `cdntest.com`

 Address of the origin server:

 `origin.com`

|    -   If you set Domain Type to **CDN Domain**, the origin host is set to `cdntest.com`.
    -   If you set Domain Type to **Origin Domain**, the origin host is set to `origin.com`.
    -   If you set Domain Type to **Custom Domain**, the origin host is set to the specified custom domain name. |
    |Example 2|IP address|By default, the Origin Host feature is disabled.|Accelerated domain name: `cdntest.com`

 Address of the origin server:

 `1.1.1.1`

|    -   If you set Domain Type to **CDN Domain**, the origin host is set to `cdntest.com`.
    -   If you set Domain Type to **Custom Domain**, the origin host is set to the specified custom domain name.
 **Note:** The address of the origin server is an IP address. Therefore, the **Origin Domain** option is unavailable for the Domain Type parameter. |
    |Example 3|OSS bucket domain name|By default, the Origin Host feature is enabled.|Accelerated domain name: `cdntest.com`

 Address of the origin server:

 `test.oss-cn-hangzhou.aliyuncs.com`

|    -   If you set Domain Type to **CDN Domain**, the origin host is set to `cdntest.com`.
    -   If you set Domain Type to **Origin Domain**, the origin host is set to `test.oss-cn-hangzhou.aliyuncs.com`.
    -   If you set Domain Type to **Custom Domain**, the origin host is set to the specified custom domain name.
 **Note:** Default settings:

Domain Type: Origin Domain

Address of the origin server: `test.oss-cn-hangzhou.aliyuncs.com` |

7.  Click **OK**.


