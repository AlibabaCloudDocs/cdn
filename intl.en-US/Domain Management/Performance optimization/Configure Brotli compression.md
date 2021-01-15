---
keyword: [Brotli compression, performance optimization]
---

# Configure Brotli compression

After you enable the Brotli compression feature, static text files are compressed into Brotli files. This reduces file sizes and accelerates content delivery. This topic describes how to enable the Brotli compression feature.

Brotli is a new open source compression algorithm. After Brotli compression is enabled, Content Delivery Network \(CDN\) nodes can compress text files in formats such as HTML, JavaScript, and CSS when the nodes return the requested resources. Brotli compression is 15% to 25% more efficient than intelligent compression.

-   If a request includes the `Accept-Encoding: br` request header, Alibaba Cloud CDN uses Brotli to compress requested resources before it returns the requested resources to the client.
-   If a response from the origin server includes the `Content-Encoding: br` response header, it indicates that the requested resources are compressed based on Brotli.

**Note:**

-   If both Brotli compression and GNU zip \(Gzip\) compression are enabled, and the `Accept-Encoding` request header includes the `br` and `gzip` fields, Brotli compression takes priority.
-   If compression is enabled on the origin server, and the response includes the `content_encoding` response header, Brotli compression is not supported.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Optimization**.

5.  In the **Brotli Compression** section, turn on the **Brotli Compression** switch.


