# Brotli compression {#task_371714 .task}

This topic describes Brotli compression and how to enable it in the CDN console. Brotli compression helps to reduce content size and expedite content delivery.

Brotli is a new, open-source compression algorithm. It enables a CDN node to compress and optimize the requested HTML, JS, and CSS, and other static text files at speeds that are 15% to 25% higher than Gzip.

-   If the request message from a client carries the `Accept-Encoding: br` request header, the client wants the requested resources to be compressed by using Brotli.
-   If the response message from the server carries the `Conetnt-Encoding: br` response header, the server returns the requested resources that are compressed by using Brotli.

**Note:** If Brotli compression and Gzip compression are both enabled and the `Accept-Encoding` request header in the request message from the client carries both the `br` and `gzip` options, the CDN node as a priority uses Brotli to compress the requested content.

1.  Log on to the [CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **Domain Names**.
3.  Locate the domain name you want to set, and click **Manage** in the **Actions** column.
4.  In the left-side navigation pane, click **Performance Optimization**.
5.  In the Brotli Compression section, turn on Brotli compression. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301855/156047553648022_en-US.png)


