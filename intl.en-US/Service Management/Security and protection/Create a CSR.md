# Create a CSR

If you need to configure an SSL certificate for an accelerated domain name, you must create a Certificate Signing Request \(CSR\) to apply for an SSL certificate from a certificate authority \(CA\). This topic describes how to create a CSR.

You can use the following methods to upload a custom SSL certificate. The differences between the two methods are:

-   **Upload Custom Certificate \(Certificate\)**

    You can create a private key and a CSR in the Alibaba Cloud Content Delivery Network \(CDN\) console, and use the CSR to apply for an SSL certificate from a CA. After the application is approved, upload the certificate to Alibaba Cloud CDN. If you use this method, your private key file is exposed to only Alibaba Cloud CDN. This method is more secure than the other method.

    **Note:** After you create a CSR, you can download it in the Alibaba Cloud CDN console. However, you cannot download the private key in the console. If you need to download both the CSR and private key, create them by using tools other than the Alibaba Cloud CDN console. For more information,see [How do I create a CSR file?](https://www.alibabacloud.com/help/doc-detail/42218.htm)

-   **Upload Custom Certificate \(Certificate+Private Key\)**

    You must obtain an SSL certificate and a private key file from a CA and then upload the certificate and the private key file to Alibaba Cloud CDN.


1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Security & Protection** \> **HTTPS Center**.

3.  On the **Certificate Center** page, click **CSR Generator**.

4.  In the **CSR Generator** dialog box, set the required parameters.

    ![Create a CSR](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6611036061/p76515.png)

    |Parameter|Description|Example|
    |---------|-----------|-------|
    |**Country**|Enter the code of the country where your organization is located. For more information, see [CSR country codes](/intl.en-US/Service Management/Security and protection/CSR country codes.md).|CN|
    |**Province/State/Region**|Enter the name of the province, state, or region where your organization is located. Chinese Pinyin is supported.|Zhejiang|
    |**City**|Enter the name of the city where your organization is located. Chinese Pinyin is supported.|Hangzhou|
    |**Organization**|Enter the name of your organization. Chinese Pinyin is supported.|Alibaba Inc.|
    |**Organization Unit**|Enter the name of your department. Chinese Pinyin is supported.|IT Department|
    |**Email**|Enter your email address.|1234567@qq.com|
    |**Common Name**|Enter the Common Name \(CN\) used to apply for the SSL certificate.|aliyun.com|
    |**SANs**|This parameter is required if you want to apply for the same SSL certificate for more than one domain name. Separate multiple domain names with commas \(,\).|a.com,b.com,c.com|

5.  Click **Generate CSR**.

    ![A CSR is created](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6611036061/p76516.png)

6.  Click **Download**.

    You can save the CSR as a local file. You can then use the CSR to apply for an SSL certificate from a CA.

7.  Upload the SSL certificate and associate it with domain names.

    After you obtain the SSL certificate, you must upload it to Alibaba Cloud CDN and associate the certificate with domain names that need to use this certificate. For more information, see [Configure an SSL certificate](/intl.en-US/Service Management/Security and protection/Configure an SSL certificate.md).

    **Note:** When you upload an SSL certificate, you must set **Certificate Source** to **Upload Custom Certificate \(Certificate\)**.


