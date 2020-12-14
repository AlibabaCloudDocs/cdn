---
keyword: [force redirect, CDN, HTTPS secure acceleration]
---

# Configure the force redirect feature

You can enable the force redirect feature to redirect the requests from clients to L1 nodes of Alibaba Cloud Content Delivery Network \(CDN\) as HTTP or HTTPS requests. This topic describes how to enable the force redirect feature.

Make sure an HTTPS certificate is configured. For more information, see [Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md).

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **HTTPS**.

5.  In the **Force Redirect** section, click **Modify**.

6.  In the **Force Redirect** dialog box, set the **Redirect Type** parameter.

    |Redirect type|Description|
    |:------------|:----------|
    |**Default**|Alibaba Cloud CDN supports both HTTP and HTTPS requests.|
    |**HTTPS -\> HTTP**|Alibaba Cloud CDN redirects requests from clients to L1 nodes as HTTP requests.|
    |**HTTP -\> HTTPS**|Alibaba Cloud CDN redirects requests from clients to L1 nodes as HTTPS requests.|

    ![Force Redirect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7465297061/p64228.png)

    In the following example, the **Redirect Type** parameter is set to HTTP -\> HTTPS.

    When a client initiates an HTTP request, an L1 node returns a 301 response. This is used to redirect the request to the HTTPS version of the web page. The following figure shows an example.

    ![Verify the result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7581247061/p3707.png)

7.  Click **OK**.


