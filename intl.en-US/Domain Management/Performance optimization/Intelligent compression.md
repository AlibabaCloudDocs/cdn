---
keyword: [accelerate content delivery, intelligent compression, Gzip, performance optimization]
---

# Intelligent compression

After you enable the intelligent compression feature, Alibaba Cloud Content Delivery Network \(CDN\) automatically compresses static files into GUN zip \(Gzip\) files. This feature compresses files to increase the content delivery efficiency. This topic describes how to enable the intelligent compression feature.

-   Intelligent compression supports the following formats: text/html, text/xml, text/plain, text/css, application/javascript, application/x-javascript, application/rss+xml, text/javascript, image/tiff, image/svg+xml, application/json, and application/xmltext.
-   If a request from a client includes the `Accept-Encoding: gzip` request header, the client expects the requested content to be compressed in Gzip.
-   If a response from Alibaba Cloud CDN includes the `Content-Encoding: gzip` response header, the returned content is Gzip compressed.

**Note:**

-   If MD5 validation is configured for a file on the origin server, do not enable this feature. After a static file is compressed, it uses a different MD5 value than the file on the origin server, which will cause MD5 validation to fail.
-   Files on the origin server will be Gzip compressed only when the file size exceeds 1,024 bytes.
-   Internet Explorer 6 is not fully compatible with Gzip. If you expect your users to use Internet Explorer 6, we recommend that you disable the intelligent compression feature.
-   If both the HTML optimization feature and the intelligent compression feature are enabled, the HTML optimization feature does not take effect. Alibaba Cloud CDN only compresses files.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Optimization**.

5.  In the **Intelligent Compression** section, enable intelligent compression.

    ![Enable intelligent compression](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8056219951/p7301.png)


