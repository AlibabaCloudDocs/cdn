# Configure URL authentication {#task_187634 .task}

The URL authentication feature protects origin server resources from unauthorized download and access. You can prevent some hotlinking issues by configuring a referer blacklist or whitelist with hotlink protection. However, this method cannot completely protect resources on the origin server because referer content can be forged. URL authentication is a more secure and effective method to protect resources on the origin server.

URL authentication is a more secure and reliable method that integrates CDN nodes with the origin server to protect resources on the origin server.

-   The origin server provides encrypted URLs that contain permission verification information.
-   You can send a request to a CDN node by accessing an encrypted URL.
-   The CDN node authenticates the permission information in the encrypted URL to determine whether the request is valid. If the request is valid, the CDN node returns a successful response. If the request is invalid, the CDN node rejects the request.

For more information about sample Python authentication code, see [Sample authentication code](reseller.en-US/Domain Management/Access Control Settings/Business type/Sample authentication code.md#).

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Access Control**.
5.  Click **URL Authentication**.
6.  In the URL Authentication section, click **Modify**. 

    ![URL Authentication](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15390/156661457910073_en-US.png)

7.  Turn on the **URL Authentication** switch as prompted to configure URL authentication. 

    |Parameter|Description|
    |---------|-----------|
    |Type| CDN supports three authentication types. You can select an authentication type based on your need to protect resources on the origin server. The following URL authentication types are supported:

    -   [Authentication type A](reseller.en-US/Domain Management/Access Control Settings/Business type/Authentication type A.md#)
    -   [Authentication Type B](reseller.en-US/Domain Management/Access Control Settings/Business type/Authentication Type B.md#)
    -   [Authentication type C](reseller.en-US/Domain Management/Access Control Settings/Business type/Authentication type C.md#)
 |
    |Primary Key|The primary password corresponding to the selected authentication type.|
    |Secondary Key|The secondary password corresponding to the selected authentication type.|

8.  Click **OK**.

You can perform the following steps to generate a signed URL.

1.  In the Generate Signed URL section, configure **Original URL** and authentication information.

    |Parameter|Description|
    |---------|-----------|
    |Original URL|The complete original URL. For example, https://www.aliyun.com.|
    |Type| The authentication type. Select one of the following URL authentication types:

    -   [Authentication type A](reseller.en-US/Domain Management/Access Control Settings/Business type/Authentication type A.md#)
    -   [Authentication Type B](reseller.en-US/Domain Management/Access Control Settings/Business type/Authentication Type B.md#)
    -   [Authentication type C](reseller.en-US/Domain Management/Access Control Settings/Business type/Authentication type C.md#)
 |
    |Cryptographic Key|The authentication password. Cryptographic Key can be Primary Key or Secondary Key configured in the Set URL Authentication dialog box.|
    |Validity Period|The validity period for URL authentication. Unit: seconds. Example value: 1,800.|

    ![Generate signed URL](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15390/156661458053097_en-US.png)

2.  Click **Generate**.

    Obtain **Authentication URL** and **Timestamp**.

    ![URL authentication](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15390/156661458050938_en-US.png)


