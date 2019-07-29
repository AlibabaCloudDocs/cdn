# Configure HTTPS certificates {#task_261642 .task}

This topic describes how to configure HTTPS certificates. After you configure HTTP certificates, you must then upload the certificates to CDN in a PEM format to enable HTTP security acceleration.

-   HTTPS certificate files must be in PEM format. For more information, see [Certificate Format](intl.en-US/Domain Management/HTTPS Acceleration/Certificate Format.md#).
-   You must purchase an advanced HTTPS certificate or apply for a free HTTPS certificate at [Alibaba Cloud Security Certificate Service](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home).

HTTPS certificates are divided into the following three types based on certification levels:

-   Domain Validation \(DV\) certificates

    A DV certificate has a safe lock and authenticates only the ownership of a domain, that is, the content of specified files in the domain or the .txt records related to the domain.

-   Organization Validation \(OV\) certificates

    An OV certificate is a standard SSL certificate that verifies the identity of an enterprise. OV certificates feature stricter authentication and a longer authentication period, therefore they are more secure than DV certificates. OV certificates are mostly used in the e-commerce, education, and gaming sectors.

-   Extended Validation \(EV\) certificates

    EV certificates follow the guidelines maintained by the Certification Authority Browser Forum, also known as the CA/Browser Forum. They are SSL certificates of the highest certification level. Each EV certificate is identified by an object identifier \(OID\), which is a complete enterprise name. EV certificates are widely used in such sectors as financial payment and online banking.


1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the domain name you want to set, and in the **Actions** column click **Manage**.
4.  In the left-side navigation pane, click **HTTPS**.
5.  In the **HTTPS Certificate** section, click **Modify**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/156440886511410_en-US.png)

6.  In the Modify HTTPS Settings dialog box, turn on the **HTTPS Secure** switch and set the HTTPS certificate parameters. 

    After you turn on the **HTTPS Secure** switch, the system displays a message, stating that HTTPS secure acceleration is charged in addition to CDN traffic and asking you whether you want to enable this function. For more information about HTTPS pricing, see [Value-added service](../../../../intl.en-US/Pricing/Billing method/Value-added service.md#).

    |Parameter|Description|
    |---------|-----------|
    |Certificate Type|This parameter has three values:     -   Alibaba Cloud Certificate

You can apply for a free certificate or purchase an advanced certificate at [Alibaba Cloud Security Certificate Service](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home).

    -   Custom

If you cannot find a suitable certificate, you can customize one. To do so, you need to enter the certificate name, content, and private key. Custom certificates are saved to [Alibaba Cloud Security Certificate Service](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home).

    -   Free Certificate

Free certificates are used only for HTTPS secure acceleration. Therefore, you cannot manage free certificates or view their public and private keys at [Alibaba Cloud Security Certificate Service](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home).

        -   Applying for a free certificate takes 5 minutes to 10 minutes. During the wait time, you can turn to purchase an advanced certificate at [Alibaba Cloud Security Certificate Service](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home) or customize one.
        -   The validity period of a free certificate is one year. When a free certificate expires, its validity period is automatically renewed.
        -   When you turn off and then again turn on the **HTTPS Secure** switch while a free certificate is in use:
            -   If the free certificate has not expired, it takes effect immediately.
            -   If the free certificate expires, you must apply for a new one.
 You can switch between **Alibaba Cloud Certificate**, **Custom**, and **Free Certificate**.

 |
    |Certificate Name|When **Certificate Type** is set to **Alibaba Cloud Certificate** or **Custom**, you must enter the certificate name.|
    |Content|When **Certificate Type** is set to **Custom**, you must enter the certificate content. For more information, click **PEM Encoding Format** below the **Content** field.|
    |Private Key|When **Certificate Type** is set to **Custom**, you must enter the private key. For more information, click **PEM Encoding Format** below the **Private Key** field.|

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/156440886511413_en-US.png)

7.  Click **OK**. 

    You can enable, disable, or modify the HTTPS certificate. After the HTTPS certificate is disabled, the system deletes the certificate information. To enable the HTTPS certificate again, you must re-enter the certificate or private key information.

8.  Verify that the HTTPS certificate takes effect. 

    After you update the HTTPS certificate, the updated HTTPS certificate takes effect in 1 minute. To verify that the HTTPS certificate takes effect, use HTTPS to access resources. If the URL in the address bar of the browser displays *https* in green, HTTPS secure acceleration takes effect.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/15644088663701_en-US.png)


