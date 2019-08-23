# Enable private bucket back-to-origin authentication {#concept_ljh_42y_wdb .concept}

## Function overview {#section_zvk_bxc_xdb .section}

Private bucket back-to-origin authentication is performed when traffic of a CDN domain is diverted to the bucket marked as private under a user account. After authentication is successful and authentication configuration is enabled, domain names enabled with private bucket authentication have the permission to access the private bucket.

You can use functions such as the referer anti-leech protection and authorization provided by CDN to protect resource security.

**Warning:** 

-   After authentication is successful and the private bucket function of corresponding domains are enabled, the CDN domain can be used to access the resource content in your private bucket. Consider carefully when you decide whether to enable this function. If the content in the private bucket to be authorized is not suitable to function as the back-to-origin content of the CDN domain, do not perform authorization or enable the function.
-   If your website faces attack risks, please buy Anti-DDoS service and do not perform authorization or enable the private bucket function.

## Procedure {#section_qrl_jxc_xdb .section}

Enable private bucket back-to-origin authorization

1.  Log on to the [CDN console](https://cdnnext.console.aliyun.com/domain/list)
2.  In the left-side navigation pane, choose **Domain Names**. In the main workspace, select a domain, and in the **Actions** column click **Manage**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/156653413945538_en-US.png)

3.  On the page that is displayed, choose **Back-to-Origin** from the left-side navigation pane, and enable the function in the **Private bucket back-to-origin** area on the **Back-to-origin configuration** tab page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/15665341407351_en-US.png)

4.  After authorization is successful, enable private bucket back-to-origin configuration for the domain and click **Confirm**.

Disable private bucket back-to-origin authorization

**Note:** If your CDN domain is sending back-to-origin requests with the private bucket as the origin site, do not disable or delete private bucket authorization.

1.  Choose **Access Control** \> **Role Management**.
2.  Delete AliyunCDNAccessingPrivateOSSRole authorization.
3.  Private bucket authorization is successfully deleted.

