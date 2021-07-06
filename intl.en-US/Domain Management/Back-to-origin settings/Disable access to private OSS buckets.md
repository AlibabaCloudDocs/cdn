---
keyword: [access permissions on private OSS buckets, private buckets]
---

# Disable access to private OSS buckets

This topic describes how to revoke access permissions on private Object Storage Service \(OSS\) buckets from an accelerated domain name. You can log on to the Resource Access Management \(RAM\) console and revoke permissions of the RAM role for Alibaba Cloud Content Delivery Network \(CDN\). This allows you to disable access to private OSS buckets.

If your accelerated domain name is used to accelerate the delivery of content from a private OSS bucket, do not disable access to the private OSS bucket or revoke access permissions on the private OSS bucket.

1.  Log on to the [RAM console](https://ram.console.aliyun.com/overview).

2.  In the left-side navigation pane, click **RAM Roles**.

3.  On the **RAM Roles** page, find the RAM role **AliyunCDNAccessingPrivateOSSRole**.

    ![RAM Roles](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/5143/156726420345856_en-US.png)

4.  Revoke all permissions that are granted to the RAM role **AliyunCDNAccessingPrivateOSSRole**.

    1.  Click **Remove Permission** in the Actions column.

    2.  In the Remove Permission message, click **OK**.

5.  Go to the **RAM Roles** page and delete the RAM role **AliyunCDNAccessingPrivateOSSRole**.

    1.  Find the RAM role **AliyunCDNAccessingPrivateOSSRole** and click **Delete** in the Actions column.

    2.  In the **Delete RAM Role** message, click **OK**.


**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

