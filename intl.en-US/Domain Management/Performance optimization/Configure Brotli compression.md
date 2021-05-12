---
keyword: [Brotli compression, performance optimization]
---

# Configure Brotli compression

Brotli is an open source compression algorithm. After you enable the Brotli compression feature, text files are compressed into Brotli files before they are returned to users. This reduces file sizes, accelerates content delivery, and reduces bandwidth usage.

You can use intelligent compression or Brotli compression to compress files that are larger than 1,024 bytes. This reduces file sizes and accelerates content delivery. Brotli compression outperforms Gzip compression by about 15% to 25%.

-   Brotli compression supports the following formats: text/xml, text/plain, text/css, application/javascript, application/x-javascript, application/rss+xml, text/javascript, image/tiff, image/svg+xml, application/json, and application/xml.
-   If a request includes the `Accept-Encoding: br` request header, the client expects the requested resources to be Brotli compressed.
-   If a response from the origin server includes the `Content-Encoding: br` response header, the resources returned to the client are Brotli compressed.

## Considerations

-   If MD5 verification is configured for files on the origin server, do not enable intelligent compression.

    The intelligent compression feature changes the MD5 value of a file. After a file is compressed, the MD5 value of the file is no longer the same as that of the original file stored on the origin server.

-   If compression is enabled on the origin server and the response includes `content_encoding`, compression on CDN nodes does not take effect.
-   If both Brotli compression and Gzip compression are enabled, and the `Accept-Encoding` request header includes both `br` and `gzip`, only Brotli compression takes effect.
-   If both HTML optimization and Intelligent or Brotli compression are enabled, HTML optimization does not take effect. Alibaba Cloud CDN only compresses files.
-   Gzip is supported by almost all browsers, whereas Brotli is supported only by certain browsers. You can click [here](https://caniuse.com) to query whether a browser supports Gzip or Brotli.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Optimization**.

5.  In the **Brotli Compression** section, turn on **Brotli Compression** and set the parameters.

    After you enable Brotli compression, you can compare the sizes of a file before and after compression is performed. If the file size is reduced, it indicates that the file is compressed.


## Related API operations

[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

