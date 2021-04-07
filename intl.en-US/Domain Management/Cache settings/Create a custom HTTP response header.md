---
keyword: [HTTP response header, CDN, cross-origin request]
---

# Create a custom HTTP response header

HTTP response headers are an important part of an HTTP message. HTTP response headers describe the requested resource, server or client behavior, and operation parameters in an HTTP transaction. Alibaba Cloud Content Delivery Network \(CDN\) allows you to add response headers to responses returned from your origin servers. You can configure this feature to enable cross-origin resource sharing \(CORS\).

HTTP headers are components of the header section of requests and responses that are transmitted over HTTP. HTTP headers include general headers, request headers, and response headers.

CORS is a standard cross-origin solution provided by HTML5 to allow web application servers to control cross-origin access. This solution secures data transmission.

## Scenarios

You can enable CORS by adding response headers to responses. After Alibaba Cloud CDN receives a cross-origin request, CORS rules are triggered for permission checks. Alibaba Cloud CDN compares the cross-origin request with CORS rules one after one. Alibaba Cloud CDN uses the first rule that the request matches to process the requests and adds a header to the responses. If the request fails to match the CORS rules, no header is added to the response.

An HTTP response header applies to a specified domain name. After you create an HTTP response header, it is added to all responses returned from the domain name. An HTTP response header affects the response behavior of only clients such as browsers. It does affect the caching behavior of CDN nodes. You cannot create a custom HTTP response header for wildcard domain names.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  Click the **Custom HTTP Response Header** tab.

6.  Click **Customize** and set the parameters.

    In the following example, a custom HTTP response header is created.

    ![Create a custom HTTP response header](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2314077161/p69929.png)

    |Parameter|Description|
    |---------|-----------|
    |**Operation**|You can add, delete, modify, or replace specified response headers.|
    |**Response Header**|Select a response header. For more information, see [Response headers](#section_wj7_ax2_xre).|
    |**Header Name**|If you select **Custom**, you must specify a header name. Take note of the following rules:    -   The name can contain letters, underscores \(-\), and digits.
    -   The name must be 1 to 100 characters in length. |
    |**Header Value**|Specify the header value. For more information, see [Response headers](#section_wj7_ax2_xre).|
    |**Allow Duplicates**|    -   **Yes**: Duplicate headers are allowed. Duplicate headers added by Alibaba Cloud CDN and returned from the origin server are all retained.
    -   **No**: Duplicate header are not allowed. The header added by Alibaba Cloud CDN overwrites the duplicate header returned from the origin server. |

7.  Click **OK**.

    After a custom response header is created, it is displayed on the **Custom HTTP Response Header** tab. You can **Modify** or **Delete** the header.


## Response headers

|Response header|Description|Example|
|:--------------|:----------|-------|
|Custom|Allows you to create a custom response header based on your business requirements. When you specify the header name, take note of the following rules:-   The name can contain letters, underscores \(-\), and digits.
-   The name must be 1 to 100 characters in length.

|Test-Header|
|Cache-Control|Specifies the cache policy that requests and responses follow.|no-cache|
|Content-Disposition|Specifies the default file name when the retrieved content is saved as a file on the client program.|123.txt|
|Content-Type|Specifies the media type of the resource returned to clients.|image|
|Pragma|Pragma HTTP/1.0 is an implementation-specific header that has various effects along the request-response chain. It is compatible with HTTP 1.1.|no-cache|
|Access-Control-Allow-Origin|Specifies the origin servers with which the response can be shared. You can enter an asterisk \(\*\) in the Header Value field to specify all domain names. You can also enter a specific domain name, for example, `www.aliyun.com`.|\*|
|Access-Control-Allow-Methods|Specifies the request methods that can be used in cross-origin requests. You can specify one or more request methods. Separate multiple request methods with commas \(,\).|POST,GET|
|Access-Control-Allow-Headers|Specifies the header fields that can be used in cross-origin requests.|X-Custom-Header|
|Access-Control-Expose-Headers|Allows a server to specify which response headers are available to scripts that are running in the browser.|Content-Length|
|Access-Control-Allow-Credentials|Specifies whether browsers can expose responses to frontend JavaScript code. -   true: Browsers can expose responses to frontend JavaScript code.
-   Other values: Browsers cannot expose responses to frontend JavaScript code.

|true|
|Access-Control-Max-Age|Specifies how long the results of a preflight request can be cached, in seconds.|600|

## Related API operations

[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

