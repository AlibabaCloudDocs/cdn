---
keyword: [access permissions on private buckets, private buckets]
---

# Disable access to Alibaba Cloud OSS private buckets

This topic describes how to revoke access permissions on your Alibaba Cloud Object Storage Service \(OSS\) private buckets from an accelerated domain. You can log on to the Resource Access Management \(RAM\) console and revoke permissions of the RAM role for Alibaba Cloud Content Delivery Network \(CDN\). This allows you to disable access to the private buckets.

If your accelerated domain name is used to accelerate the delivery of content from a private bucket, do not disable access to the private bucket or revoke access permissions on the private bucket.

1.  Log on to the [RAM console](https://ram.console.aliyun.com/overview).

2.  In the left-side navigation pane, click **RAM Roles**.

3.  On the RAM Roles page, click the RAM role name **AliyunCDNAccessingPrivateOSSRole**.

    ![RAM Roles](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/5143/156726420345856_en-US.png)

4.  Click **Remove Permission** in the Actions column of the RAM role.

5.  In the Remove Permission dialog box, click **OK**.

6.  Return to the **RAM Roles** page, click **Delete** in the Actions column of the RAM role.

7.  In the **Delete RAM Role** message, click **OK**.


