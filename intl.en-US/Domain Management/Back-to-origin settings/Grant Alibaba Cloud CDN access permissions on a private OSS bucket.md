---
keyword: [OSS domain name, private bucket, back-to-origin]
---

# Grant Alibaba Cloud CDN access permissions on a private OSS bucket

If the origin server is a private Alibaba Cloud Object Storage Service \(OSS\) bucket, you can grant Alibaba Cloud Content Delivery Network \(CDN\) access permissions on the private OSS bucket. This way, Alibaba Cloud CDN can access the private OSS bucket through the accelerated domain name. This prevents hotlink issues. This topic describes how to grant Alibaba Cloud CDN access permissions on a private OSS bucket.

After you enable access to a private OSS bucket, you can use features such as hotlink protection and URL signing provided by Alibaba Cloud CDN to ensure resource security. For more information, see [Configure hotlink protection](/intl.en-US/Domain Management/Access control/Configure hotlink protection.md) and [URL signing](/intl.en-US/Domain Management/Access control/URL signing/URL signing.md).

**Note:**

-   After you authorize Alibaba Cloud CDN to access a private OSS bucket, Alibaba Cloud CDN is granted read-only permissions on all your OSS buckets.
-   After the required permissions are granted to Alibaba Cloud CDN and enabled for an accelerated domain name, Alibaba Cloud CDN can access the objects in the specified private bucket through the accelerated domain name. Proceed with caution. If you do not want to deliver content in a private OSS bucket to the accelerated domain name, do not grant Alibaba Cloud CDN permissions on the private OSS bucket or enable access to private OSS buckets.
-   If your website is vulnerable to attacks, purchase an Anti-DDoS service. Do not grant Alibaba Cloud CDN permissions on private OSS buckets or enable access to private OSS buckets.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  In the **Alibaba Cloud OSS Private Bucket Access** section, click **Authorize**.

6.  Click **Confirm Authorization Policy**.

    **Note:** You can enable access to private OSS buckets only if the origin server is an OSS bucket.

    ![Confirm the authorization](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5179745261/p45826.png)

7.  In the **Alibaba Cloud OSS Private Bucket Access** section, turn on **Alibaba Cloud OSS Private Bucket Access**.

    Based on the preceding settings, Alibaba Cloud CDN is authorized to access unencrypted files in the specified private OSS bucket, which is the origin server. Alibaba Cloud CDN cannot access objects that are encrypted based on Key Management Service \(KMS\) in OSS. You must grant the **AliyunKMSCryptoUserAccess** permission to the Resource Access Management \(RAM\) role **AliyunCDNAccessingPrivateOSSRole**. Then, Alibaba Cloud CDN can assume this role to access encrypted objects.

    You can disable access to private OSS buckets. For more information, see [Disable access to Alibaba Cloud OSS private buckets](/intl.en-US/Domain Management/Back-to-origin settings/Disable access to Alibaba Cloud OSS private buckets.md).

8.  Grant the **AliyunKMSCryptoUserAccess** permission to the RAM role **AliyunCDNAccessingPrivateOSSRole**.

    1.  Log on to the [RAM console](https://ram.console.aliyun.com/).

    2.  In the left-side navigation pane, click **RAM Roles**.

    3.  On the **RAM Roles** page, find the RAM role **AliyunCDNAccessingPrivateOSSRole**.

    4.  Click **Add Permissions** in the Actions column. In the Add Permissions panel, the value of the **Principal** field is automatically specified.

    5.  Click **System Policy** and enter **AliyunKMSCryptoUserAccess** in the search box to search for the **AliyunKMSCryptoUserAccess** permission policy. Click the permission policy to add it to the **Selected** list.

    6.  Click **OK**.

    7.  Click **Complete**.


**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

