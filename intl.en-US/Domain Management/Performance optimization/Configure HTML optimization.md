---
keyword: [HTML optimization, performance optimization]
---

# Configure HTML optimization

Alibaba Cloud Content Delivery Network \(CDN\) supports the HTML optimization feature. This feature enables Alibaba Cloud CDN to automatically remove redundant content from web pages, such as comments and additional whitespace characters in HTML pages and CSS or JavaScript code. This reduces file sizes, accelerates content delivery, and improves website readability.

## Precautions

-   If MD5 verification is configured for files on the origin server, do not enable HTML optimization.

    The HTML optimization feature changes the MD5 value of a file. After the file is optimized, the MD5 value of the file is no longer the same as the original file stored on the origin server.

-   If the origin server has Gzip or Brotli compression enabled, HTML optimization does not take effect. Alibaba Cloud CDN directly returns compressed files to clients.

    If you want to enable HTML optimization without disabling Gzip or Brotli compression on the origin server, you can set Alibaba Cloud CDN to delete the Accept-Encoding header from requests before they are redirected to the origin server. This way, both HTML optimization and Gzip or Brotli compression can work at the same time. For more information about how to delete the Accept-Encoding header, see [Customize an HTTP request header](/intl.en-US/Domain Management/Back-to-origin settings/Customize an HTTP request header.md).

-   If both HTML optimization and Intelligent or Brotli compression are enabled, HTML optimization does not take effect. Alibaba Cloud CDN only compresses files.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Optimization**.

5.  In the **HTML Optimization** section, you can turn on **HTML Optimization**, **CSS Optimization**, or **JavaScript Optimization**.

    **Note:** The HTML Optimization switch controls only HTML optimization. If you want to enable CSS or JavaScript optimization, you must first turn on HTML Optimization, and then turn on CSS Optimization or JavaScript Optimization.

    ![Enable HTML optimization](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5816717161/p7303.png)

    -   Turn on **HTML Optimization**: Alibaba Cloud CDN optimizes HTML pages.
    -   Turn on **CSS Optimization**: Alibaba Cloud CDN optimizes CSS styling.
    -   Turn on **JavaScript Optimization**: Alibaba Cloud CDN optimizes JavaScript code.

## Related API operations

[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

