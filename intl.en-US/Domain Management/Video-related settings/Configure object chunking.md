---
keyword: [range, back-to-origin]
---

# Configure object chunking

This topic describes how to configure the object chunking feature in the Alibaba Cloud Content Delivery Network \(CDN\) console and the usage notes. The object chunking feature reduces the amount of network traffic generated during the back-to-origin process and the response time. This feature facilitates the delivery of large files.

The object chunking feature specifies that the origin server returns only specified file chunks to clients. When you configure object chunking, take note of the following rules:

-   Make sure that the origin server supports HTTP requests that contain the Range field, and the origin server can respond to requests with the 206 HTTP status code \(partial content message\).
-   Object chunking is optional and disabled by default.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Video**.

5.  In the **Object Chunking** section, click **Modify**.

6.  Set **Object Chunking** to **On**, **Off**, or **Force**.

    ![Object chunking](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7913772161/p64294.png)

    |Value|Description|Example|
    |:----|:----------|:------|
    |**On**|If you want the origin server to return only the specified chunks of files, you can select this value to enable object chunking. This feature improves content delivery efficiency. After you enable this feature, the origin server determines the chunks of files to be returned based on the Range header field in the request. Then, the CDN node returns the file chunks determined by the origin server to the client.**Note:** If the request contains the Range header field, the response also contains the Range header field. Only the first request sent from a client can fetch content in the size specified by the Range header field. For other requests, content is returned to the client as chucks in the size of 512 KB.

|If a client sends a request that contains `range:0-100`, the request is redirected to the origin server with `range:0-100` retained. The origin server returns a file chunk that contains 101 bytes to the CDN node based on the Range header field. The CDN node then returns the file chunk to the client.|
    |**Off**|If you want the origin server to return all content in the requested file to clients, select this value to disable object chunking. After you disable this feature, CDN nodes retrieve all content in the requested file from the origin server. However, the HTTP connection between the client and CDN node automatically closes after the client receives the requested content. The file is not cached on the CDN node. Therefore, the cache hit ratio decreases and the amount of network traffic generated during the back-origin process increases.|If a client sends a request that contains `range:0-100`, the request is redirected to the origin server with range:0-100 ignored. The origin server returns the entire file to the CDN node. However, the CDN node returns only 101 bytes to the client based on the Range header field. The HTTP connection between the client and CDN node automatically closes after the client receives the 101 bytes. Therefore, the file is not cached on the CDN node.|
    |**Force**|If you want all requests that contain the Range header field to be redirected to the origin server, select this value. After you set **Object Chunking** to **Force**, all chunked requests are forcibly sent to the origin server. The requested content is returned to clients as chunks in the size of 512 KB, regardless of whether the requests contain the Range header field.|N/A|

7.  Click **OK**.


