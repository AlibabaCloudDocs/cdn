---
keyword: [CDN cache hit ratio, cache rule]
---

# Configure cache rules for resources

When the ETag or Last-Modified response header is not returned, the requested static resource fails to be cached. This reduces the cache hit ratio in Alibaba Cloud Content Delivery Network \(CDN\). To improve the cache hit ratio of Alibaba Cloud CDN, you can configure a cache rule for this resource. As a result, the resource can be cached on CDN nodes based on the cache rule. This topic describes how to configure cache rules for resources.

[Alibaba Cloud account registration](https://account.alibabacloud.com/register/intl_register.htm) and [real-name verification](https://account-intl.console.aliyun.com/#/intlAuth) are completed.

When no cache rule is configured, if the ETag and Last-Modified response headers are not returned, a static file cannot be cached on a CDN node. The following steps show how to configure a cache rule for the static file.

The x-swift response header shows that the time-to-live \(TTL\) value of the static file on a CDN node is zero seconds, as shown in the following figure. This indicates that Alibaba Cloud CDN will not cache this static file because the ETag and Last-Modified response headers are not returned.

![Response header exception](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1484208061/p50553.png)

If the origin server is configured with the following response headers, Alibaba Cloud CDN will not cache the static file even if you have configured a cache rule. This is because these response headers have the highest priority in terms of CDN cache rules.

-   One of `s-maxage=0`, `max-age=0`, `no-cache`, `no-store`, and `private`
-   `s-maxage` or `s-maxage=0`
-   `Pragma: no-cache`

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  On the **Cache Expiration** tab, click **Create Rule**.

6.  In the Create Expiration Rule dialog box, set Type to Directory or File Extension, and set the parameters that are described in the following table.

    ![Cache expiration rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4954796061/p64132.png)

    |Parameter|Description|
    |---------|-----------|
    |**Type**|    -   Directory: specifies the resources that are cached in the specified directory.
    -   File Extension: specifies the resources that are cached in files with the specified file extensions. |
    |**Object**|    -   If you set Type to Directory, enter a directory name in the Object field. The directory name must start with a forward slash \(/\), for example, /directory/aaa.
    -   If you set Type to File Extension, enter one or more file extensions in the File Extension field. Separate multiple file extensions with commas \(,\), for example, `jpg,txt`. |
    |**Expire In**|Set a TTL value of the cached resources. A CDN node can cache resources for up to three years. We recommend that you set this parameter based on the following rules:     -   Specify a TTL value of one month or longer for static files such as images and applications that are not frequently updated.
    -   Specify a TTL value based on your actual workloads for static files such as JavaScript and CSS files that are frequently updated.
    -   Specify a TTL value of 0 seconds to disable caching for dynamic files such as PHP, JSP, and ASP files. |
    |**Weight**|Set the priority of the cache expiration rule. **Note:**

    -   The value must be an integer from 1 to 99. A higher value specifies a higher priority. A rule with a higher priority prevails over rules with lower priorities.
    -   We recommend that you do not set the same priority for different rules. If different rules have the same priority value, one of these rules is applied at random.
    -   After a cache expiration rule is applied, other cache expiration rules are no longer matched.
For example, if you set the following rules for `example.aliyun.com`, Rule 1 is preferentially applied over the other two rules:

    -   Rule 1: Type is set to File Extension, File Extension is set to jpg,png, Expire In is set to 1 month, and Weight is set to 90.
    -   Rule 2: Type is set to Directory, Object is set to /www/dir/aaa, Expire In is set to 1 hour, and Weight is set to 70.
    -   Rule 3: Type is set to Directory, Object is set to /www/dir/aaa/example.php, Expire In is set to 0 seconds, and Weight is set to 80. |

7.  Click **OK**.


To check whether the cached resource can be hit, perform the following steps:

1.  Open the browser Google Chrome and press F12.
2.  In the panel that appears, click the **Network** tab.
3.  Check the value of the `X-Cache` field in the response header of the specified URL.
    -   A value of `HIT` indicates that the resource that is cached on the CDN node is hit.
    -   A value of `MISS` indicates that the requested resource has not been cached on the CDN node and is retrieved from the origin server.

