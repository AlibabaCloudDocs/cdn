---
keyword: [HTML optimization, performance optimization]
---

# HTML optimization

After you enable the HTML optimization feature, Alibaba Cloud Content Delivery Network \(CDN\) automatically removes redundant comments and duplicate spaces from all HTML pages. This reduces file sizes and improves page readability. This topic describes how to enable the HTML optimization feature.

After you enable the HTML optimization feature, Alibaba Cloud CDN automatically removes redundant comments and duplicate spaces from all HTML pages. This reduces file sizes and increases content delivery efficiency.

If MD5 verification is configured for files on the origin server, do not enable this feature. After pages are optimized, the MD5 values of the optimized files are modified. In this case, the files on the origin server and CDN nodes use different MD5 values.

**Note:**

-   If the origin server has Gzip compression enabled, the HTML optimization feature does not take effect. Alibaba Cloud CDN directly returns compressed files to clients. If you want to enable the HTML optimization feature but cannot disable Gzip compression on the origin server, modify the back-to-origin settings. Enable Alibaba Cloud CDN to delete the Accept-Encoding header from requests. This way, the HTML optimization feature can work as expected. For more information about how to delete the Accept-Encoding header, see [Create a custom HTTP response header](/intl.en-US/Domain Management/Cache settings/Create a custom HTTP response header.md).
-   If both the HTML optimization feature and the intelligent compression feature are enabled, the HTML optimization feature does not take effect. Alibaba Cloud CDN only compresses files.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Optimization**.

5.  In the **HTML Optimization** section, turn on **HTML Optimization**.

    ![Turn on HTML Optimization](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5816717161/p7303.png)


