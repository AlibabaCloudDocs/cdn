---
keyword: [URL signing, CDN, access control]
---

# Configure URL signing

Alibaba Cloud Content Delivery Network \(CDN\) provides the URL signing feature to protect origin servers from unauthorized downloads and access. Hotlink protection provides a referer blacklist and a referer whitelist that can address some hotlink issues. However, the referer header can be forged. Origin servers require protection features that are more optimized than hotlink protection. In this case, you can enable the URL signing feature to protect your origin server.

URL signing works with both origin servers and CDN nodes to protect origin servers from hotlink issues.

-   URLs can be signed by CDN nodes. Signed URLs carry signature information that can be used for permission verification.
-   Users send signed URLs to CDN nodes.
-   CDN nodes authenticate the signatures of the URLs. If a URL passes the authentication, a response is returned. If a URL fails the authentication, the request is rejected.

For more information about sample URL signing code in Python, see [URL signing examples](/intl.en-US/Domain Management/Access control/URL signing/URL signing examples.md).

**Note:** After a request passes the authentication, the special characters such as `=` and `+` in the URL are escaped.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Access Control**.

5.  Click the **URL Signing** tab.

6.  In the **URL Signing** section, click **Modify**.

7.  Turn on the **Set URL Signing** switch and set the parameters.

    ![URL signing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1752286061/p64280.png)

    |Parameter|Description|
    |---------|-----------|
    |**Type**|Alibaba Cloud CDN supports three signing types. You can select a signing type based on your business requirements to protect resources on your origin server. Supported signing types are:

    -   [Type A signing](/intl.en-US/Domain Management/Access control/URL signing/Type A signing.md)
    -   [Type B signing](/intl.en-US/Domain Management/Access control/URL signing/Type B signing.md)
    -   [Type C signing](/intl.en-US/Domain Management/Access control/URL signing/Type C signing.md)
**Note:** If a URL signing error occurs, a 403 error is returned.

    -   MD5 calculation errors

Example: `X-Tengine-Error:denied by req auth: invalid md5hash=de7bfdc915ced05e17380a149bd760be`

    -   Time-related errors

Example: `X-Tengine-Error:denied by req auth: expired timestamp=1439469547` |
    |**Primary Key**|Specify the primary key for the selected signing type.|
    |**Secondary Key**|Specify the secondary key for the selected signing type.|

8.  Click **OK**.


To generate a signed URL, perform the following steps:

1.  In the **Generate Signed URL** section, enter the **Original URL** and signing information.

    |Parameter|Description|
    |---------|-----------|
    |**Original URL**|Enter a complete URL, for example, `https://www.aliyun.com`.|
    |**Type**|Select a signing type based on your business requirements.

    -   [Type A signing](/intl.en-US/Domain Management/Access control/URL signing/Type A signing.md)
    -   [Type B signing](/intl.en-US/Domain Management/Access control/URL signing/Type B signing.md)
    -   [Type C signing](/intl.en-US/Domain Management/Access control/URL signing/Type C signing.md) |
    |**Cryptographic Key**|Set the cryptographic key. The **Cryptographic Key** is the **Primary Key** or **Secondary Key** specified in the **URL Signing** settings.|
    |**Validity Period**|Set the validity period for the signed URL based on your business requirements. Unit: seconds. Example: 1800.|

    ![Generate an encrypted URL](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1752286061/p64282.png)

2.  Click the **Generate**.

    A **Signed URL** and a **Timestamp** are generated.

    ![URL signing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/15390/156661458050938_en-US.png)


