---
keyword: [TTL of HTTP status codes, CDN]
---

# Create a cache expiration rule for HTTP status codes

This topic describes how to set a time-to-live \(TTL\) value for HTTP status codes that are returned to requests for resources in a specified directory or with specified file extensions. This way, Alibaba Cloud Content Delivery Network \(CDN\) nodes can directly return HTTP status codes, excluding 2xx status codes, to requests. This reduces loads on origin servers.

## Scenarios

HTTP 2xx status codes indicate that CDN nodes have retrieved the requested resources from the origin server. In this case, the origin server returns an HTTP 2xx status code to the CDN nodes. Then, the CDN nodes process the requests based on cache expiration rules. If the origin server fails to return an HTTP 2xx status code to the CDN nodes, and you do not want the origin server to respond to every request, you can set a TTL value for HTTP status codes. Then, CDN nodes directly return HTTP status codes to requests and reduce loads on the origin server. The HTTP status codes returned from CDN nodes do not include 2xx status codes.

You can set a TTL value for the following HTTP status codes:

-   4xx: 400, 401, 403, 404, 405, 407, and 414.
-   5xx: 500, 501, 502, 503, 504, 509, and 514.

**Note:**

-   303, 304, 401, 407, 600, and 601 status codes are not supported.
-   If the Cache-Control header is configured on the origin server, Alibaba Cloud CDN caches the following HTTP status codes based on the Cache-Control rule: 204, 305, 400, 403, 404, 405, 414, 500, 501, 502, 503, and 504. If you do not set a TTL value for these HTTP status codes, the TTL value is set to 1 second by default.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  Click the **Status Code Expiration** tab.

6.  Click **Create Rule** to create an expiration rule for HTTP status codes.

    ![Create an expiration rule for HTTP status codes](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7192077161/p64200.png)

    |Type|Description|
    |:---|:----------|
    |**Type**|You can select **Directory** or **File Extension**. Select a type based on your business requirements. **Note:** If you set TTL values for the HTTP status codes of both a directory and files with specified extensions, whichever rule that is set first takes effect. All other rules are ignored. |
    |**Object**|    -   If you select **Directory**, take note of the following rules:
        -   You can add only one directory in each rule.
        -   You can enter a full path. It must start with a forward slash \(/\), for example, /directory/aaa.
    -   If you select **File Extension**, take note of the following rules:
        -   You can enter one or more file extensions. Separate multiple file extensions with commas \(,\), for example, `JPG,TXT`.
        -   You cannot use an asterisk \(\*\) to specify all file types. |
    |**Expire In**|    -   You can set a TTL value for 4xx and 5xx HTTP status codes. The TTL value is measured in seconds. Separate multiple HTTP status codes with commas \(,\), for example, 403=10,404=15.
    -   You cannot set a TTL value for 2xx or 3xx status codes. You can set a TTL value for specific HTTP status codes, including 201 and 302 status codes. For example, you can set 201=10,302=15. |

7.  Click **OK**.

    After an expiration rule for HTTP status codes is created, it is displayed on the **Expire In** tab. You can **Modify** or **Delete** the rule.


## Related API operations

[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

