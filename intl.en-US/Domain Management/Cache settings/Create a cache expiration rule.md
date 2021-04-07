---
keyword: [cache expiration rules, TTL values of cached resources, CDN]
---

# Create a cache expiration rule

Alibaba Cloud Content Delivery Network \(CDN\) allows you to set a time-to-live \(TTL\) value for static resources that are cached on CDN nodes. You can specify directories and files. CDN nodes automatically delete resources that are expired. Requests received by CDN nodes are considered invalid if the requested resources have already expired. These requests are redirected to origin servers to retrieve resources. The retrieved resources are cached on CDN nodes again. This topic describes how cache expiration rules work on CDN nodes and how to create a cache expiration rule.

The following figure shows the expiration rules for resources that are cached on CDN nodes.

![Cache expiration rules](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8422096061/p67212.png)

-   If you have not created a cache expiration rule on your origin server or in the Alibaba Cloud CDN console, the default cache expiration rule applies. The default TTL value for cached resources is 10 seconds and the maximum is 3,600 seconds. You can modify the TTL value in the Alibaba Cloud CDN console. The amount of back-to-origin network traffic and fees vary based on the TTL value. We recommend that you set a TTL value based on your business requirements. A small TTL value may cause CDN nodes to frequently redirect requests to the origin server and increase the amount of network traffic on the origin server.
-   If an origin server has a cache expiration rule configured, the priority of this rule is lower than the cache expiration rules set on CDN nodes. If an origin server does not have a cache expiration rule configured, you can set a cache expiration rule by specifying the directory or file type. You can specify a full path.
-   A CDN node may remove cached files that are not frequently requested before they expire.
-   If the ETag value from the origin server and the If-Match value from the client are the same, the CDN node that is nearest to the client returns the cached content to the client. If the ETag value from the origin server and the If-Match value from the client are different, the CDN node retrieves the latest content from the origin server and returns it to the client. The CDN node also updates the cached content with the retrieved content. CDN nodes compare the If-Match value with the ETag value before the nodes apply the cache expiration rules.

## Scenarios

CDN nodes respond to requests based on the cache status. If the requested resource is not cached on CDN nodes, the request is redirected to the origin server to retrieve the resource. After the resource is retrieved from the origin server, an HTTP 2XX status code is returned to the CDN node. The retrieved resource is cached on the CDN node and also returned to the client.

If resources on your origin server are updated but the resources cached on CDN nodes are not, CDN nodes may return outdated resourced to clients or respond to requests slowly. In this case, you can create a cache expiration rule. After resources expire based on the cache expiration rule, CDN nodes retrieve the latest resources from the origin server. We recommend that you set a greater TTL value for infrequently requested resources. This increases the cache hit ratio and accelerates content delivery.

## Procedure

When you update resources on the origin server, we recommend that you use different names for different versions of the same resource. This separates outdated and updated resources on the origin server. You can use version numbers to indicate different versions of a resource, for example, img-v1.0.jpg and img-v2.1.jpg.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  On the **Cache Expiration** tab, click **Create Rule**.

6.  In the **Create Expiration Rule** dialog box, set the parameters.

    ![Create a cache expiration rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4954796061/p64132.png)

    |Parameter|Description|
    |---------|-----------|
    |**Type**|You can select **Directory** or **File Extension**. Select a type based on your business requirements.     -   **Directory**: specifies the resources that are cached in the specified directory.
    -   **File Extension**: specifies the file types of the cached resources. |
    |**Object**|    -   If you select **Directory**, take note of the following rules:
        -   You can add only one directory in each rule.
        -   You can enter a full path. It must start with a forward slash \(/\), for example, /directory/aaa.
    -   If you select **File Extension**, take note of the following rules:
        -   You can enter one or more file extensions. Separate multiple file extensions with commas \(,\), for example, `JPG,TXT`.
        -   You cannot use an asterisk \(\*\) to specify all file types. |
    |**Expire In**|Specify the TTL value of the cached resources. You can set the TTL value to at most three years.     -   Specify a TTL value of one month or longer for static files that are infrequently updated, such as images and application packages.
    -   Specify a TTL value based on your actual workloads for static files that are frequently updated, such as JS and CSS files.
    -   Specify a TTL value of 0 seconds to disable caching for dynamic files, such as PHP, JSP, and ASP files. |
    |**Weight**|Specify the weight of the cache expiration rule. The weight indicates the priority of the cache expiration rule. Valid values are from 1 to 99. A greater value indicates a higher priority. **Note:**

    -   We recommend that you specify a different weight for each cache expiration rule. If rules have the same weight, they are randomly applied.
    -   If you have created multiple cache expiration rules for a cached resource, only the first matched rule is applied. |

7.  Click **OK**.

    After a cache expiration rule is created, it is displayed on the **Cache Expiration** tab. You can **Modify** or **Delete** the rule.


## Examples

In the following examples, three cache expiration rules are created for the accelerated domain name `example.aliyun.com`. Rule 1 has the highest priority. If Rule 1 is applied, other rules are ignored.

-   Rule 1: The TTL value of all JPG and PNG files is set to one month. The weight of the rule is set to 90.
-   Rule 2: The TTL value of the directory example.aliyun.com is set to 1 hour. The weight of the rule is set to 70.
-   Rule 3: The TTL value of the full path /www/dir/aaa/example.php is set to 0 seconds. The weight of the rule is set to 80.

## Related API operations

[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

