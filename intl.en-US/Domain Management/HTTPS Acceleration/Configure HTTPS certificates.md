# Configure HTTPS certificates {#task_261642 .task}

HTTPS is an HTTP channel designed to enhance security. HTTPS provides better protection for content transmission through CDN, allowing clients to browse website content more securely and effectively at a high speed. This topic describes how to authenticate and configure HTTPS certificates.

You must purchase an advanced HTTPS certificate or apply for a free HTTPS certificate in the [Alibaba Cloud Security console](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home).

Your HTTPS certificate files must be in `PEM` format. For more information, see [Convert certificate formats](reseller.en-US/Domain Management/HTTPS Acceleration/Overview of certificate formats.md#section_cn2_rql_xdb).

HTTPS acceleration is a value-added service. After you enable HTTPS, HTTPS requests incur additional fees. The fee is separately charged based on HTTPS requests and is not covered by the CDN data transfer plan. For more information about the billing standards, see [Value-added service](../reseller.en-US/Pricing/Billing method/Value-added service.md#).

HTTPS certificates are divided into the following three types based on certification levels:

-   A domain validated \(DV\) certificate has a safe lock and authenticates only the ownership of a domain, that is, the content of specified files in the domain or the .txt records related to the domain.
-   An organization validated \(OV\) certificate is a standard SSL certificate that verifies the identity of an organization. OV certificates feature stricter authentication and a longer authentication period, therefore they are more secure than DV certificates. OV certificates are mostly used in the e-commerce, education, and gaming sectors.
-   An extended validated \(EV\) certificate follows the guidelines maintained by the Certification Authority Browser Forum, also known as the CA/Browser Forum. An EV certificate is the SSL certificate of the highest certification level. Each EV certificate is identified by an object identifier \(OID\), which is a complete enterprise name. EV certificates are widely used in sectors such as financial payment and online banking.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the HTTPS Certificate section, click **Modify**. 

    ![Modify HTTPS Settings](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/156653122811413_en-US.png)

5.  In the Modify HTTPS Settings dialog box, turn on **HTTPS Secure Acceleration** and set the HTTPS certificate parameters. 

    After you turn on HTTPS Secure Acceleration, the system displays a message, stating that HTTPS acceleration is charged in addition to CDN traffic and asking you whether you want to enable this function. For more information about HTTPS billing standards, see [Value-added service](../reseller.en-US/Pricing/Billing method/Value-added service.md#).

    |Parameter|Description|
    |---------|-----------|
    |Certificate Type|     -   Alibaba Cloud Certificate

You can apply for a free certificate or purchase an advanced certificate in the [Alibaba Cloud Security console](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home).

    -   Custom

If you cannot find a suitable certificate, you can upload a custom one. To do so, you need to set the certificate name, and then upload the certificate content and private key. Custom certificates are saved to Alibaba Cloud Security Certificate Service. You can check the certificate in [My Certificate](https://yundun.console.aliyun.com/?spm=5176.2020520110.all.12.16df56a1u1IhI6&p=cas#/cas/home).

    -   Free Certificate

Free certificates are free Digicert DV SSL certificates provided by Alibaba Cloud. Free certificates are used only for HTTPS acceleration. Therefore, you cannot manage free certificates or view their public and private keys in the Alibaba Cloud Security console.

        -   Applying for a free certificate takes 5 to 10 minutes. During this period, you can also choose to re-upload a custom certificate or Alibaba Cloud Security certificate.
        -   Free certificates are valid for one year and are automatically renewed upon expiration.
        -   When you turn off and then again turn on HTTPS Secure Acceleration while a free certificate is in use, the free certificate that has not expired takes effect immediately. If the free certificate expires, you must apply for a new one.
 You can switch between Alibaba Cloud certificates, custom certificates, and free certificates.

 |
    |Certificate Name|When **Certificate Type** is set to **Alibaba Cloud Certificate** or **Custom**, you must enter the certificate name.|
    |Content|When **Certificate Type** is set to **Custom**, you must enter the certificate content. For more information, click **PEM Encoding Reference** under the **Content** field.|
    |Private Key|When **Certificate Type** is set to **Custom**, you must enter the private key. For more information, click **PEM Encoding Reference** under the **Private Key** field.|

6.  Click **OK**. 

    You can disable, enable, and modify the HTTPS certificate. After the HTTPS certificate is disabled, the system deletes the certificate information. To enable the HTTPS certificate again, you must re-upload the certificate or private key.

7.  Verify that the HTTPS certificate takes effect. 

    An updated HTTPS certificate takes effect on the entire network within one minute. To verify if the HTTPS certificate takes effect, use HTTPS to access resources. If the URL in the address bar of the browser displays https in green, HTTPS acceleration is in effect.

    ![Verify the result](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/15665312293701_en-US.png)


