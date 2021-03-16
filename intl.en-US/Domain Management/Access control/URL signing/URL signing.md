---
keyword: [URL signing, CDN, access control]
---

# URL signing

Alibaba Cloud Content Delivery Network \(CDN\) provides the URL signing feature to protect origin servers from unauthorized access and downloads. Hotlink protection provides a referer blacklist and a referer whitelist that can address some hotlink issues. However, the referer header can be forged. Origin servers require protection features that are more optimized than hotlink protection. In this case, you can enable the URL signing feature to protect your origin server.

URL signing works with both origin servers and CDN nodes to protect origin servers from hotlink issues.

-   The origin server provides a signed URL that contains authentication information.
-   A user sends a request to a CDN node by using the signed URL.
-   The CDN node verifies the authentication information in the signed URL to determine whether the request is valid. If the request is valid, the CDN node returns a response. If the request is invalid, the CDN node rejects the request.

For more information about sample URL signing code in Python, see [URL signing examples](/intl.en-US/Domain Management/Access control/URL signing/URL signing examples.md).

**Note:** After a request passes the authentication, the special characters such as equal signs \(`=`\) and plus signs \(`+`\) in the URL are escaped.

1.  Log on to the [CDN控制台](https://cdn.console.aliyun.com)[Alibaba Cloud CDN console](https://cdn.console.aliyun.com)[Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Access Control**.

5.  Click the **URL Signing** tab.

6.  In the **URL Signing** section, click **Modify**.

7.  In the **Set URL Signing** dialog box, turn on URL Signing and set the parameters.

    ![URL signing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1752286061/p64280.png)

    |Parameter|Description|
    |---------|-----------|
    |**Type**|Alibaba Cloud CDN supports three signing types. You can select a signing type based on your business requirements to protect resources on your origin server. Supported signing types are:

    -   [Type A signing](/intl.en-US/Domain Management/Access control/URL signing/Type A signing.md)
    -   [Type B signing](/intl.en-US/Domain Management/Access control/URL signing/Type B signing.md)
    -   [Type C signing](/intl.en-US/Domain Management/Access control/URL signing/Type C signing.md)
**Note:** If a URL signing error occurs, a 403 error is returned.

    -   Invalid MD5 values

Example: `X-Tengine-Error:denied by req auth: invalid md5hash=de7bfdc915ced05e17380a149bd760be`

    -   Invalid timestamps

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
    |**Validity Period**|Set the validity period of the signed URL based on your business requirements. Unit: seconds. Example: 1800.**Note:** The default validity period is 30 minutes. If you want to set a validity period of less than 30 minutes, set **Validity Period** to a negative value. For example, if you want to set the validity period to 10 seconds, set **Validity Period** to -1790. |

    ![Generate a signed URL](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1752286061/p64282.png)

2.  Click **Generate**.

    A **Signed URL** and a **Timestamp** are generated.

    ![URL signing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/15390/156661458050938_en-US.png)


