# Configure HTML optimization {#task_187634 .task}

When you enable the HTML optimization feature, CDN automatically removes redundant comments and duplicate spaces from all HTML pages. This helps reduce file size and improve page readability. This topic describes how to enable the HTML optimization feature.

When you enable the HTML optimization feature, CDN automatically removes redundant comments and duplicate spaces from all HTML pages. This helps reduce file size and improve the efficiency of content delivery.

If MD5 validation is configured for a file in the origin server, do not enable this feature. When pages are optimized, the MD5 value of the optimized file is different from that of the file in the origin server, which causes MD5 validation to fail.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Optimization**.
5.  In the HTML Optimization section, turn on HTML Optimization. 

    ![HTML Optimization](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5160/15665336647303_en-US.png)


