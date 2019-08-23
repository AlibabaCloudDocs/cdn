# Configure object chunking {#task_187634 .task}

Object chunking allows the client to notify the origin server to return partial content within a specified range. It helps accelerate delivery of large files. This feature also helps reduce the consumption of back-to-origin traffic and improve resource response speed. This topic describes how to enable object chunking and related precautions.

When you configure object chunking, take note of the following points:

-   Ensure that the origin server supports range requests. If the HTTP request header contains the range field, the origin server must be able to return 206 Partial Content.
-   Object chunking is optional and is disabled by default.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Video**.
5.  In the Object Chunking section, click **Modify**. 

    ![Object chunking](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5157/156653384146660_en-US.png)

6.  Object Chunking can be set to On, Off, or Force. 

    |Object chunking|Description|Example|
    |:--------------|:----------|:------|
    |On|Requests with the Range parameter can be sent to the origin server. The origin server returns a file that has the number of bytes within the range specified by the Range parameter. CDN nodes return the file to the client.|When a request sent from the client to a CDN node contains `range: 0-100`, the request received by the origin server also contains `range: 0-100`. The origin server returns a file with 101 bytes in the range of 0 to 100 to the CDN node. Then, the CDN node returns this file to the client.|
    |Off|A CDN node redirects a request for the entire file on the origin server. The client automatically disconnects the HTTP connection to the CDN node after receiving a file that has the number of bytes within the range specified by the Range parameter. The requested file is not cached on the CDN node. This results in a low cache hit rate and large back-to-origin traffic.|When a request sent from the client to a CDN node contains `range: 0-100`, the request received by the origin server does not contain the Range parameter. The origin server returns a complete file to the CDN node. However, the CDN node returns a file with the first 101 bytes to the client. Because the HTTP connection is disconnected, this file is not cached on the CDN node.|
    |Force|The requests with the range parameter are forcibly sent to the origin server.|When you set Object Chunking to Force, make sure that the origin server supports the Range parameter.|

    **Note:** 

    When you set Object Chunking to Force, all chunked requests are forcibly sent to the origin server.

7.  Click **OK**.

