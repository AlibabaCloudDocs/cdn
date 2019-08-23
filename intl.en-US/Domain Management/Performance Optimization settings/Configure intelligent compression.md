# Configure intelligent compression {#task_187634 .task}

When you enable the intelligent compression feature, static files will be automatically GZIP compressed. GZIP compression reduces the size of the transmitted files and accelerates content delivery. This topic describes how to enable the intelligent compression feature.

-   Intelligent compression supports the following formats: text/html, text/xml, text/plain, text/css, application/javascript, application/x-javascript, application/rss+xml, text/javascript、image/tiff, image/svg+xml, application/json, and application/xmltext.
-   If a request from the client includes the `Accept-Encoding: gzip` request header, the client expects the requested resource to be GZIP compressed.
-   If a response from a CDN node includes the `Content-Encoding: gzip` response header, the requested resource is GZIP compressed.

**Note:** 

-   If MD5 validation is configured for a file in the origin server, do not enable this feature. When a static file is compressed, the MD5 value of the compressed file is different from that of the file in the origin server, which will cause MD5 validation to fail.
-   Files in the origin server will be GZIP compressed only when the file size exceeds 1,024 B.
-   Internet Explorer 6 is not fully compatible with GZIP. If your customers expect to use Internet Explorer 6, we recommend you disable the intelligent compression feature.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Optimization**.
5.  In the Intelligent Compression section, turn on Intelligent Compression. 

    ![Intelligent Compression](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5159/15665337147301_en-US.png)


