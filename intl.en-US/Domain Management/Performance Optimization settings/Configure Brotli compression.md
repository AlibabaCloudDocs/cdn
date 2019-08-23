# Configure Brotli compression {#task_371714 .task}

When you want to compress static text files, you can enable the Brotli compression feature to reduce the size of the transmitted content and accelerate content delivery. This topic describes how to enable the Brotli compression feature.

Brotli is a new open-source compression algorithm. With Brotli compression enabled, CDN nodes can compress the text files such as HTML, JavaScript, and CSS when it returns the requested resource. The efficiency of Brotli compression is 15 to 25% higher than that of intelligent compression.

-   If a request includes the `Accept-Encoding: br` request header, the client expects the requested resource to be Brotli compressed.
-   If a response from a CDN node includes the `Content-Encoding: br` response header, the requested resource is Brotli compressed.

**Note:** If both Brotli compression and GZIP compression are enabled, and the `Accept-Encoding` request header includes `br` and `gzip`, Brotli compression takes priority.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Optimization**.
5.  In the Brotli Compression section, turn on Brotli Compression. 

    ![Brotli Compression](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301855/156653374948022_en-US.png)


