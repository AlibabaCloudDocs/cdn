# Enable HTTP/2 {#task_261642 .task}

HTTP/2 is the latest version of HTTP, which has improved resource access efficiency and security. This topic describes the concept and benefits of HTTP/2, and how to enable it.

Make sure an HTTPS certificate is configured. For more information, see [Configure HTTPS certificates](reseller.en-US/Domain Management/HTTPS Acceleration/Configure HTTPS certificates.md#). 

**Note:** 

-   If this is the first time that you configure an HTTPS certificate, you must wait for the certificate to take effect before enabling HTTP/2.
-   If you disable HTTPS acceleration after enabling HTTP/2, HTTP/2 is automatically disabled.

HTTP/2, originally named HTTP 2.0, is the latest version of HTTP. It is supported by all major browsers such as Google Chrome, Internet Explorer 11, Safari, and Mozilla Firefox. HTTP/2 provides optimized performance and is compatible with HTTP/1.1 semantics. HTTP/2 is similar to SPDY but differs greatly from HTTP/1.1.

Benefits of HTTP/2:

-   Binary encoding: Unlike HTTP 1.x that parses data into texts, HTTP/2 splits the data to be transmitted into messages and frames and encodes them into binary formats. Binary encoding makes HTTP/2 more scalable. For example, frames can be introduced to transmit data and instructions.
-   Content security: HTTP/2 is designed based on HTTPS, protecting content security while maintaining network performance.
-   Multiplexing: HTTP/2 allows multiplexing of multiple concurrent streams on a single connection. Specifically, you can initiate countless requests at the same time over one connection by using a browser, and the server returns the responses to these requests at the same time. In addition, you can set stream dependencies, which the client uses to inform the server of the importance of a given stream relative to other streams on the same connection, so that resources can be allocated appropriately.
-   Header compression: HTTP headers carry large volumes of information, which is transmitted repeatedly. HTTP/2 compresses HTTP headers into the HPACK format, allowing both ends of the communications to each cache a copy of the HTTP header indexes and hence transmit only index numbers for duplicate HTTP headers. This increases transmission speed and efficiency.
-   Server push: Like SPDY, HTTP/2 can push messages to clients. HTTP/2 is widely adopted by many websites, such as Google.com, Amazon.com, and Taobao.com. You can use Google Chrome to log on to the Alibaba Cloud CDN console and check whether HTTP/2 is enabled.

    **Note:** SPDY is an application layer protocol developed by Google based on TCP. SPDY minimizes network latency to accelerate network access and improve user experience. SPDY is not a replacement for HTTP but serves as an enhancement to HTTP. Similar to HTTP/2, SPDY also provides multiplexing, request prioritization, and HTTP header compression.


1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  On the **HTTP/2** tab, turn on **HTTP/2**. 

    ![HTTP/2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5137/156653128047106_en-US.png)


