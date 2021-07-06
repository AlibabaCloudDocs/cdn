---
keyword: [HTTP response header, CDN, cross-origin request]
---

# Rewrite HTTP headers in back-to-origin requests

If you want to rewrite the HTTP headers in a back-to-origin request URL, you can customize HTTP request headers in the Alibaba Cloud Content Delivery Network \(CDN\) console. This topic describes how to rewrite an HTTP request header.

HTTP headers are components of the header section of request and response messages transmitted over HTTP.

HTTP headers include general headers, request headers, and response headers.

![Rewrite an HTTP request header](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3574297061/p87913.png)

**Note:**

-   A back-to-origin request is an HTTP message that is transmitted by Alibaba Cloud CDN to an origin server of a specific accelerated domain name.
-   A rewrite rule rewrites only HTTP headers in HTTP requests that are transmitted between an origin server and CDN nodes. It does not rewrite HTTP headers in HTTP requests that are transmitted between CDN nodes and clients.
-   Custom HTTP requests headers do not support wildcard domain names.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  Click **Custom Request Headers \(New\)**.

6.  Click **Customize**.

7.  Set the parameters in the Back-to-origin Request Headers dialog box.

    **Note:** If different operations are performed on the same request header at the same time, these operations have different priorities. The operations are prioritized in the following descending order: **Replace** \> **Add** \> **Change or Delete**. For example, if you perform the Add and Delete operations on the same request header at the same time, the request header is added and then deleted.

    -   Parameters of the Add operation

        ![Rewrite an HTTP request header](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3574297061/p87947.png)

        |Parameter|Example|Description|
        |---------|-------|-----------|
        |Operation|Add|Adds a specific request header to back-to-origin HTTP requests.|
        |Request Header|Custom Back-to-origin Request Headers|You can use the default value, or select **Custom Request Header** from the Request Header drop-down list to add a custom request header.|
        |Header Name|x-code|Adds a custom request header named x-code.|
        |Header Value|key1|You can specify one or more values for a request header. Separate values with commas \(,\).|
        |key1, key2|
        |Allow Duplicates|Yes|If **Allow Duplicates** is set to **Yes**, you can add duplicate request headers. For example, `x-code:key1` and `x-code:key2` can coexist.|
        |No|If **Allow Duplicates** is set to **No**, the latest header value overwrites the existing one that uses the same header name. For example, if you add `x-code:key1` and then add `x-code:key2`, the final header key-value pair is `x-code:key2`.|

    -   Parameters of the Delete operation

        ![Delete](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3574297061/p88664.png)

        |Parameter|Example|Description|
        |---------|-------|-----------|
        |Operation|Delete|Deletes all request headers that match the values of the Request Header and Header Name parameters. Duplicate request headers are also deleted.|
        |Request Header|Custom Back-to-origin Request Headers|You can use the default value, or select **Custom Request Header** from the Request Header drop-down list to delete custom request headers.|
        |Header Name|x-code|Deletes a custom request header named x-code.|

    -   Parameters of the Change operation

        ![Change](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3574297061/p88665.png)

        |Parameter|Example|Description|
        |---------|-------|-----------|
        |Operation|Change|You can perform the Change operation only if no duplicate request headers exist.|
        |Request Header|Custom Back-to-origin Request Headers|You can use the default value, or select **Custom Request Header** from the Request Header drop-down list to replace a custom request header.|
        |Header Name|x-code|Modifies a custom request header named x-code.|
        |Change Value To|key1, key3|You can specify one or more values for a request header. Separate values with commas \(,\).|

    -   Parameters of the Replace operation

        ![Replace](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3574297061/p88666.png)

        |Parameter|Example|Description|
        |---------|-------|-----------|
        |Operation|Replace|You can perform the Replace operation only if no duplicate request headers exist.|
        |Request Header|Custom Back-to-origin Request Headers|You can use the default value, or select **Custom Request Header** from the Request Header drop-down list to replace a custom request header.|
        |Header Name|x-code|Replaces a custom request header named x-code.|
        |Find|key|Allows you to use regular expressions to search for the value that you want to replace.|
        |Replace With|abc|Allows you to use regular expressions to replace matching values.|
        |Match|Match All|If **Match** is set to **Match All**, all matching values are replaced. For example, if you use a regular expression to replace all the "key" in `x-code:key1,key2,key3` with "abc", the key-value pair is changed to`x-code:abc1,abc2,abc3`.|
        |Match the First Only|If **Match** is set to **Match the First Only**, only the first matching value is replaced. For example, if you use a regular expression to replace the first "key" in `x-code:key1,key2,key3` with "abc", the key-value pair is changed to `x-code:abc1,key2,key3`.|

8.  Click **OK**.


**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

