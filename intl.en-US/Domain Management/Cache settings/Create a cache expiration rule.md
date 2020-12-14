---
keyword: [cache expiration rules, time-to-live \(TTL\) values of cached resources, CDN]
---

# Create a cache expiration rule

Alibaba Cloud Content Delivery Network \(CDN\) allows you to create cache expiration rules to expire static resources of specified file types or in specified directories. You can also specify a priority for each cache expiration rule. When a static resource expires, the resource is automatically deleted from the CDN node that caches the resource. This topic describes the rules that are used to expire cached resources on a CDN node and how to create a cache expiration rule.

When you update a resource file on the origin server, we recommend that you include the version number in the name of the update file instead of using the same name as the existing resource file. For example, you can name two update files img-v1.0.jpg and img-v2.1.jpg. Then, you can set a cache expiration rule for the resource file.

The following figure shows the expiration rules of the resources that are cached on CDN nodes.

![Cache expiration rules](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8422096061/p67212.png)

**Note:**

-   If you have not set a cache expiration time on your origin server or CDN nodes, the CDN nodes use the default TTL value of 3,600 seconds to expire cached resources. After you add a domain name to Alibaba Cloud CDN, you can modify the TTL value. The amount of back-to-origin traffic and fees vary based on the TTL value. We recommend that you set a TTL value based on your business requirements. A small TTL value may cause CDN nodes to frequently redirect requests to the origin server and increase the amount of network traffic consumed by the origin server.
-   If an origin server has a caching rule configured, the cache expiration rule on the CDN node has a higher priority than the caching rule that is configured on the origin server. If an origin server has no caching rule configured, you can set a cache expiration rule by directory or by file extension. You can set a full-path cache expiration rule.
-   A CDN node may remove the cached files before they expire if they are not frequently updated.
-   If the response from an origin server contains the ETag header, the request from a client contains the If-Match header, and the value of the If-Match header matches the value of the ETag header, the CDN node that is closest to the client returns the cached content to the client. If the value of the If-Match header does not match the value of the ETag header, the CDN node retrieves the latest content from the origin server and returns it to the client. At the same time, the CDN node updates the cached content with the latest content. The matching rule between the If-Match header and the ETag header has a higher priority than the cache expiration rule that is configured on CDN nodes.

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

    You can click **Modify** or **Delete** in the Actions column of the cache expiration rule to modify or delete the rule.


