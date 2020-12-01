---
keyword: [content delivery acceleration, intelligent compression, Gzip, performance improvement]
---

# Intelligent compression

After you enable the intelligent compression feature, Alibaba Cloud Content Delivery Network \(CDN\) automatically compresses static files into GUN zip \(Gzip\) files. This feature compresses files to increase the content delivery efficiency. This topic describes how to enable the intelligent compression feature.

-   Intelligent compression supports the following formats: text/html, text/xml, text/plain, text/css, application/javascript, application/x-javascript, application/rss+xml, text/javascript, image/tiff, image/svg+xml, application/json, and application/xmltext.
-   If a request from a client includes the `Accept-Encoding: gzip` request header, the client expects the requested content to be Gzip compressed.
-   If a response from Alibaba Cloud CDN includes the `Content-Encoding: gzip` response header, the returned content is Gzip compressed.

**Note:**

-   If MD5 validation is configured for a file on the origin server, do not enable this feature. When a static file is compressed, the MD5 value of the compressed file is different from that of the file on the origin server, which will cause MD5 validation to fail.
-   Files on the origin server will be Gzip compressed only when the file size exceeds 1,024 bytes.
-   Internet Explorer 6 is not fully compatible with Gzip. If you expect your users to use Internet Explorer 6, we recommend that you disable the intelligent compression feature.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Optimization**.

5.  In the **Intelligent Compression** section, enable intelligent compression.

    ![Enable intelligent compression](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8056219951/p7301.png)


