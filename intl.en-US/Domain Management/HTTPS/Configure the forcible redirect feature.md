---
keyword: [forcible redirect, CDN, HTTPS secure acceleration]
---

# Configure the forcible redirect feature

Alibaba Cloud Content Delivery Network \(CDN\) provides the forcible redirect feature that can redirect client requests to HTTP or HTTPS URLs. This topic describes how to configure the forcible redirect feature.

An SSL certificate is configured. For more information, see [Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md).

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **HTTPS**.

5.  In the **Force Redirect** section, click **Modify**.

6.  In the **Force Redirect** dialog box, set the **Redirect Type** parameter.

    |Redirect type|Description|
    |:------------|:----------|
    |**Default**|Supports both HTTP and HTTPS requests.|
    |**HTTPS -\> HTTP**|Redirects client requests from HTTPS URLs to corresponding HTTP URLs.|
    |**HTTP -\> HTTPS**|Redirects client requests from HTTP URLs to corresponding HTTPS URLs.|

    ![Forcible redirect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7465297061/p64228.png)

    In the following example, the **Redirect Type** parameter is set to HTTP -\> HTTPS.

    When a client initiates an HTTP request, the server returns a 301 response to redirect the request to the HTTPS version of the web page, as shown in the following figure.

    ![Result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7581247061/p3707.png)

7.  Click **OK**.


