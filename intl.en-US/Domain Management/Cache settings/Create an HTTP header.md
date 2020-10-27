---
keyword: [HTTP response header, CDN, cross-origin request]
---

# Create an HTTP header

HTTP headers define the resources being requested, the behavior of the client or server, and the operation parameters of an HTTP transaction. This topic describes how to create an HTTP response header.

HTTP headers are components of the header section of request and response messages transmitted over Hypertext Transfer Protocol \(HTTP\).

HTTP header fields include the General-header, Client Request-header, and Server Response-header fields.

**Note:**

-   The configurations of the HTTP response header of an accelerated domain name affect the response behavior of all client programs such as browsers in this domain. However, the configurations do not affect the behavior of the cache server.
-   Alibaba Cloud Content Delivery Network \(CDN\) does not allow you to configure response headers for wildcard domain names.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Cache**.

5.  Click the **Custom HTTP Response Header** tab.

6.  On the **Custom HTTP Response Header** tab, click **Customize**.

7.  In the Cache Response Headers dialog box, set the parameters to create an HTTP response header.

    Alibaba Cloud CDN provides 10 types of HTTP response header. You can also create a custom HTTP response header. The following table lists different types of HTTP response header. If you need to create a custom HTTP response header that is not included in the preceding types,[submit a ticket](https://workorder-intl.console.aliyun.com).

    **Note:** When you add an HTTP header to responses, you can set the **Allow Duplicates** parameter to specify whether duplicate headers are allowed. A value of **Yes** indicates that duplicate headers are allowed. The header returned from the origin server and the header added to the response are both returned to the client. A value of **No** indicates that duplicate headers are not allowed. The header returned from the origin server is overwritten by the header added to the response.

    ![Set HTTP header parameters](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7875973061/p69929.png)

    |Parameter|Description|Example|
    |:--------|:----------|-------|
    |Content-Type|Specifies the MIME type of the content returned to the client program.|image|
    |Cache-Control|Specifies the cache policy that requests and responses follow.|no-cache|
    |Content-Disposition|Specifies the default file name when the requested content is saved as a file on the client program.|123.txt|
    |Content-Language|Specifies the language of the returned content for the intended audience.|zh-CN|
    |Expires|Specifies the date and time after which the response is considered stale.|Wed, 21 Oct 2015 07:28:00 GMT|
    |Access-Control-Allow-Origin|Specifies the origin servers from which cross-origin requests are allowed.|\* **Note:** You can enter an asterisk \(`*`\) in the Header Value field to specify all domain names. You can also enter a specific domain name, for example, `www.aliyun.com`. |
    |Access-Control-Allow-Headers|Specifies the fields that are allowed in cross-origin requests.|X-Custom-Header|
    |Access-Control-Allow-Methods|Specifies the request methods that are allowed for cross-origin requests.|POST and GET**Note:** Separate POST and GET with a comma \(,\). |
    |Access-Control-Max-Age|Specifies the time-to-live \(TTL\) value during which the response can be cached on the client program for a request that prefetches a particular resource.|600|
    |Access-Control-Expose-Headers|Specifies the headers that can be exposed as part of the response.|Content-Length|

8.  Click **OK**.

    In the **Custom HTTP Response Header** list, you can click **Modify** or **Delete** in the Actions column to modify or delete HTTP response headers.


