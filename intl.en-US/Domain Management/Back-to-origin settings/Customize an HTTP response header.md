# Customize an HTTP response header

The Alibaba Cloud Content Delivery Network \(CDN\) console provides a Custom Response Headers tab where you can customize HTTP response headers. This topic describes how to customize an HTTP response header on the Custom Response Headers tab.

HTTP headers are components of the header section of request and response messages that are transmitted over HTTP.

HTTP headers include general headers, request headers, and response headers.

![Responses to back-to-origin requests](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6305297061/p88049.png)

**Note:**

-   A back-to-origin request is an HTTP message that is transmitted by Alibaba Cloud CDN to an origin server of a specific accelerated domain name.
-   Custom HTTP response headers are used only in the HTTP responses from an origin server. The back-to-origin settings do not change the HTTP responses from Alibaba Cloud CDN to clients.
-   Custom HTTP response headers do not support wildcard domain names.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  Click the **Custom Response Headers**.

6.  On the **Custom Response Headers** tab, click **Customize**.

7.  Set the parameters in the Custom Response Headers dialog box.

    **Note:** If different operations are performed on the same response header at the same time, these operations have different priorities. The operations are prioritized in the following order: **Replace** \> **Add** \> **Change or Delete**. For example, if you perform the Add and Delete operations on the same response header at the same time, the response header is added and then deleted.

    -   Parameters of the Add operation

        ![Customize an HTTP response header](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6305297061/p88069.png)

        |Parameter|Example|Description|
        |---------|-------|-----------|
        |Operation|Add|Adds a response header to a back-to-origin HTTP request.|
        |Response Header|Custom Cache Response Headers|You can use the default value, or select **Response Header** from the Response Header drop-down list to add a custom response header.|
        |Header Name|x-code|Adds a custom response header named x-code.|
        |Header Value|key1|You can specify multiple values for a response header. Separate multiple values with commas \(,\).|
        |key1, key2|
        |Allow Duplicates|Yes|If **Allow Duplicates** is set to **Yes**, you can add duplicate response headers. For example, `x-code:key1` and `x-code:key2` can coexist.|
        |No|If **Allow Duplicates** is set to **No**, the new header value overwrites the existing one that uses the same header name. For example, if you add `x-code:key1` and then add `x-code:key2`, the final header name-value pair is `x-code:key2`.|

    -   Parameters of the Delete operation

        ![Delete](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6305297061/p88647.png)

        |Parameter|Example|Description|
        |---------|-------|-----------|
        |Operation|Delete|Deletes all response headers that match the values of the Response Header and Header Name parameters. Duplicate response headers are also deleted.|
        |Response Header|Custom Cache Response Headers|You can use the default value, or select **Response Header** from the Response Header drop-down list to delete a custom response header.|
        |Header Name|x-code|Deletes the custom response header named x-code.|

    -   Parameters of the Change operation

        ![Change](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6305297061/p88648.png)

        |Parameter|Example|Description|
        |---------|-------|-----------|
        |Operation|Change|You can perform the Change operation only if no duplicate response header exists.|
        |Response Header|Custom Cache Response Headers|You can use the default value, or select **Response Header** from the Response Header drop-down list to change a custom response header.|
        |Header Name|x-code|Changes the custom response header named x-code.|
        |Change Value To|key1, key3|You can specify one or more values for a response header. Separate multiple values with commas \(,\).|

    -   Parameters of the Replace operation

        ![Replace](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6305297061/p88654.png)

        |Parameter|Example|Description|
        |---------|-------|-----------|
        |Operation|Replace|You can perform the Replace operation only if no duplicate response header exists.|
        |Response Header|Custom Cache Response Headers|You can use the default value, or select **Response Header** from the Response Header drop-down list to replace a custom response header.|
        |Header Name|x-code|Replaces the custom response header named x-code.|
        |Find|key|Allows you to use regular expressions to search for the value that you want to replace.|
        |Replace With|abc|Allows you to use regular expressions to replace matching values.|
        |Match|Match All|If **Match** is set to **Match All**, all matching values will be replaced. For example, if you use a regular expression to replace all the "key" in `x-code:key1,key2,key3` with "abc", the name-value pair is changed to `x-code:abc1,abc2,abc3`.|
        |Match the First Only|If **Match** is set to **Match the First Only**, only the first matching value will be replaced. For example, if you use a regular expression to replace the first "key" in `x-code:key1,key2,key3` with "abc", the name-value pair is changed to `x-code:abc1,key2,key3`.|

8.  Click **OK**.


