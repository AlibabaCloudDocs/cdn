---
keyword: [HTTP response header, CDN, cross-origin request]
---

# Create a custom HTTP response header

HTTP header fields define the required resources, the behavior of clients or servers that process the messages, and the parameters of an HTTP transaction. This topic describes how to create a custom HTTP response header.

HTTP headers are components of the header section of request and response messages that are transmitted over HTTP.

HTTP headers include general headers, request headers, and response headers.

**Note:**

-   The configurations of an HTTP response header of an accelerated domain name affect the response behavior of all resources that belong to the domain name. When a user sends a request from a client, such as a browser, to the resources, the response behavior of the resources is affected, but the behavior of the cache server is not affected.
-   Alibaba Cloud Content Delivery Network \(CDN\) does not allow you to configure response headers for wildcard domain names.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  Click the **Custom HTTP Response Header** tab.

6.  On the **Custom HTTP Response Header** tab, click **Customize**.

7.  In the Cache Response Headers dialog box, set the parameters to create an HTTP response header.

    Alibaba Cloud CDN provides multiple types of HTTP response header. You can also create a custom HTTP response header. The following table describes different types of HTTP response header. If you want to create a custom HTTP response header that is not included in the preceding types, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

    **Note:** When you create an HTTP response header, you can set the **Allow Duplicates** parameter to specify whether duplicate headers are allowed. Valid values:

    -   A value of **Yes** indicates that duplicate headers are allowed. The header returned from the origin server and the header added to the response are both returned to the client.
    -   A value of **No** indicates that duplicate headers are not allowed. The header returned from the origin server is overwritten by the header added to the response.
    |Header|Description|Example|
    |:-----|:----------|-------|
    |Custom|Alibaba Cloud CDN supports custom HTTP response headers. The header name can be 1 to 100 characters in length, and can contain letters, hyphens \(-\), and digits.|Test-Header|
    |Cache-Control|Specifies the cache policy that requests and responses follow.|no-cache|
    |Content-Disposition|Specifies the default file name when the requested content is saved as a file on the client program.|123.txt|
    |Content-Type|Specifies the type of the content that is returned to the client program.|image|
    |Content-Language|Specifies the language of the intended audience for the content that is returned to the client program.|zh-CN|
    |Pragma|Pragma HTTP/1.0 is an implementation-specific header that has various effects along the request-response chain. It is used for compatibility with HTTP/1.1 caches.|no-cache|
    |Access-Control-Allow-Origin|Specifies the origin servers from which cross-origin requests are allowed.|\* **Note:** You can enter an asterisk \(`*`\) in the Header Value field to specify all domain names. You can also enter a specific domain name, for example, `www.aliyun.com`. |
    |Access-Control-Allow-Methods|Specifies the cross-origin request methods that are allowed.|POST and GET**Note:** Separate POST and GET with a comma \(,\). |
    |Access-Control-Allow-Headers|Specifies the fields that are allowed in cross-origin requests.|X-Custom-Header|
    |Access-Control-Expose-Headers|Specifies the headers that can be exposed as part of the response.|Content-Length|
    |Access-Control-Allow-Credentials|Specifies whether the response of a request can be exposed to the frontend code. If it is set to true, the response is exposed to the frontend code. Other values indicate that the response is not exposed to the frontend code.|true|
    |Access-Control-Max-Age|Specifies the time-to-live \(TTL\) value during which the response can be cached on the client program for a request that prefetches a particular resource.|600|

8.  Click **OK**.

    In the **Custom HTTP Response Header** list, you can click **Modify** or **Delete** in the Actions column to modify or delete HTTP response headers.


