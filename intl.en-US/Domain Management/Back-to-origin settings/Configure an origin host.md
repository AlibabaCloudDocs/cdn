---
keyword: [origin host, CDN nodes to origin servers]
---

# Configure an origin host

If you want to specify the domain name of the server to which Alibaba Cloud CDN redirects requests, you must first specify the domain type of the origin host. The origin host supports the following types of domain name: accelerated domain name, domain name of an origin server, and custom domain name.

An origin host is the domain name of the origin server to which Alibaba Cloud CDN redirects requests. If the origin server is shared by multiple services, each back-to-origin request can include an origin host that specifies the service for which the request is destined.

**Note:**

-   If the origin server is associated with multiple domain names or websites, you must specify a domain name to which requests are redirected. Otherwise, the back-to-origin process fails.
-   If the accelerated domain name is a wildcard domain name, and the protocol used to redirect requests is HTTP, you must specify a specific domain name as the origin host. Otherwise, requests cannot be redirected to the origin server.

Differences between an origin server and an origin host:

-   An origin server defines a specific IP address to which back-to-origin requests are redirected.
-   An origin host defines a specific site that is hosted on a specific IP address. Back-to-origin requests are redirected to the IP address.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  In the **Origin Host** section, click **Modify**.

6.  Turn on **Origin Host** and set **Domain Type**.

    ![Back-to-origin settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5699197061/p64119.png)

    |Parameter|Description|
    |---------|-----------|
    |**CDN Domain**|Specify the domain name that you want Alibaba Cloud CDN to accelerate. The domain name is the one that users access. For example, the accelerated domain name is `cdntest.com`. If you set Domain Type to **CDN Domain**, the accelerated domain name is specified as the origin host, which is `cdntest.com`. |
    |**Origin Domain**|Specify the domain name of the origin server. The domain name is the one to which Alibaba Cloud CDN redirects requests. For example, the domain name of the origin server is `origin.com`. If you set Domain Type to **Origin Domain**, the domain name of the origin server is specified as the origin host, which is `origin.com`. |
    |**Custom Domain**|If you set Domain Type to **Custom Domain**, a custom domain name is specified as the origin host. If the origin server is associated with multiple domain names, you must specify a domain name to which requests are redirected. Otherwise, the back-to-origin process fails. |

7.  Click **OK**.


**Example 1:** The address of the origin server is a domain name.

|Feature status|Domain name|Description|
|--------------|-----------|-----------|
|The origin host is disabled.|Accelerated domain name:`cdntest.com`

Address of the origin server:

`origin.com`

|-   If you set Domain Type to **CDN Domain**, the origin host is set to `cdntest.com`.
-   If you set Domain Type to **Origin Domain**, the origin host is set to `origin.com`.
-   If you set Domain Type to **Custom Domain**, the origin host is set to the specified custom domain name. |

**Example 2:** The address of the origin server is an IP address.

|Feature status|Domain name|Description|
|--------------|-----------|-----------|
|The origin host is disabled.|Accelerated domain name:`cdntest.com`

Address of the origin server:

`1.1.1.1`

|-   If you set Domain Type to **CDN Domain**, the origin host is set to `cdntest.com`.
-   If you set Domain Type to **Custom Domain**, the origin host is set to the specified custom domain name.

**Note:** The address of the origin server is an IP address. Therefore, the **Origin Domain** option is dimmed. |

**Example 3:** The address of the origin server is an Object Storage Service \(OSS\) endpoint.

|Feature status|Domain name|Description|
|--------------|-----------|-----------|
|The origin host is disabled.|Accelerated domain name:`cdntest.com`

Address of the origin server:

`test.oss-cn-hangzhou.aliyuncs.com`

|-   If you set Domain Type to **CDN Domain**, the origin host is set to `cdntest.com`.
-   If you set Domain Type to **Origin Domain**, the origin host is set to `test.oss-cn-hangzhou.aliyuncs.com`.
-   If you set Domain Type to **Custom Domain**, the origin host is set to the specified custom domain name.

**Note:** If the address of the origin server is an OSS endpoint, the origin host is enabled. You must set the following parameters:

Domain Type: select Origin Domain

Address of the origin server: `test.oss-cn-hangzhou.aliyuncs.com` |

**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

