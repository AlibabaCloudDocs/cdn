---
keyword: [HTML optimization, performance optimization]
---

# HTML optimization

After you enable the HTML optimization feature, Alibaba Cloud Content Delivery Network \(CDN\) automatically removes redundant comments and duplicate spaces from all HTML pages. This reduces file sizes and improves page readability. This topic describes how to enable the HTML optimization feature.

After you enable the HTML optimization feature, Alibaba Cloud CDN automatically removes redundant comments and duplicate spaces from all HTML pages. This reduces file sizes and content delivery efficiency.

If MD5 verification is configured for files on origin server, do not enable this feature. After pages are optimized, the MD5 values of the optimized files are modified and therefore become different from those of the files on the origin server.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Optimization**.

5.  In the **HTML Optimization** section, turn on the **HTML Optimization** switch.

    ![HTML optimization](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8056219951/p7303.png)


