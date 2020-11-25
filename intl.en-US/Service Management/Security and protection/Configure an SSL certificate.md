# Configure an SSL certificate

Hypertext Transfer Protocol Secure \(HTTPS\) is used for secure communication over networks. It provides reinforced protection for content accelerated by Alibaba Cloud Content Delivery Network \(CDN\). Secure Sockets Layer \(SSL\) secures the data transmitted between clients and servers while Alibaba Cloud CDN accelerates content delivery. This topic describes how different types of SSL certificate are validated and configured.

Alibaba Cloud CDN supports only SSL certificates in the `PEM` format. If your certificate is not in the `PEM` format, convert it to the PEM format first. For more information, see [Convert certificate formats](/intl.en-US/Domain Management/HTTPS/Overview of certificate formats.md).

HTTPS secure acceleration is a value-added service. After you enable HTTPS, you are charged based on the number of HTTPS requests. You cannot use CDN data transfer plans to offset the fees. For more information about the pricing of HTTPS secure acceleration, see [Billing of value-added services](/intl.en-US/Pricing/Billing method/Billing of value-added services.md).

SSL certificates are classified into the following types based on the validation level:

-   A domain validated \(DV\) certificate has a safety lock. It only verifies the ownership of a domain name. A DV certificate verifies the ownership of a domain name by verifying the specified file of the domain name or the TXT record of the domain name.
-   An organization validated \(OV\) certificate is a standard SSL certificate that verifies the identity of an organization. An OV certificate provides more trust than a DV certificate, but the validation process is stricter and longer. OV certificates are typically used in the e-commerce, education, and gaming sectors.
-   An extended validation \(EV\) certificate follows the guidelines maintained by the Certification Authority Browser Forum, also known as the CA/Browser Forum. EV certificates are SSL certificates of the highest security level. Each EV certificate is identified by an object identifier \(OID\), which is a complete enterprise name. EV certificates are widely used in sectors such as financial transactions and online banking.

**Note:** SSL certificates for Alibaba Cloud CDN do not support the 3DES algorithm.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Security & Protection** \> **HTTPS Center**.

3.  On the **Certificate Center** page, click **Add Certificate**.

4.  In the **Add Certificate** panel, set the certificate parameters.

    The following table describes the certificate parameters.

    ![Certificate](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8707454061/p93743.png)

    |Parameter|Description|
    |---------|-----------|
    |**Certificate Source**|    -   **SSL Certificates Service**

You can apply for SSL certificates of various providers and types in the [SSL Certificates Service console](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home).

    -   **Custom Certificate \(Certificate+Private Key\)**

If you cannot find a suitable SSL certificate, upload a custom certificate. To upload a custom certificate, you must specify a certificate name and upload the certificate content and private key. The uploaded certificate is saved to SSL Certificates Service. You can check the certificate on the [SSL Certificates](https://yundun.console.aliyun.com/?spm=5176.2020520110.all.12.16df56a1u1IhI6&p=cas#/cas/home) page.

    -   **Upload Custom Certificate \(Certificate\)**

If you cannot find a suitable SSL certificate, upload a custom certificate. You can choose to upload a **Upload Custom Certificate \(Certificate\)** if you do not want to disclose the private key. In this case, you must create a Certificate Signing Reques \(CSR\) file in the Alibaba Cloud CDN console and apply for a certificate from a certificate authority \(CA\). For more information, see [Create a CSR](/intl.en-US/Service Management/Security and protection/Create a CSR.md).

    -   **Free Certificate**

Free SSL certificates are used only for HTTPS secure acceleration. You cannot manage free SSL certificates or view their public or private keys in the SSL Certificates Service console.

        -   Free SSL certificates are typically issued within one to two business days. During this period of time, you can choose to upload a custom certificate or select a certificate from Alibaba Cloud SSL Certificates Service.

**Note:** After you submit the application, the certificate may be issued within several hours or two business days. The time it takes depends on the verification process required by the CA.

        -   A free SSL certificate is valid for one year. Before it expires, you do not need to apply for a new certificate each time you enable HTTPS acceleration. You must apply for a new certificate only if the current one has expired.
You can switch between **SSL Certificates Service**, **Custom Certificate \(Certificate+Private Key\)**, **Upload Custom Certificate \(Certificate\)**, and **Free Certificate**. |
    |**Certificate Name**|When you set **Certificate Source** to **SSL Certificates Service** or **Custom Certificate \(Certificate+Private Key\)**, you must specify a certificate name.|
    |**Certificate \(Public Key\)**|After you set **Certificate Source** to **Custom Certificate \(Certificate+Private Key\)** or **Upload Custom Certificate \(Certificate\)**, you must set this parameter. For more information, see the **Certificate \(Public Key\)** below the **PEM Encoding Reference** field.|
    |**Private Key**|When you set **Certificate Source** to **Custom Certificate \(Certificate+Private Key\)**, you must set this parameter. For more information, see the **PEM Encoding Reference** below the **Private Key** field.|

5.  Click **Next**.

    ![Associate a domain name with the certificate](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4119438951/p53679.png)

6.  Select a domain name and click **OK**.

    **Note:** If the selected domain name is already associated with an SSL certificate, this operation will replace the existing certificate.

    ![The SSL certificate is configured](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5236136061/p53683.png)

7.  Verify that the SSL certificate takes effect.

    After an SSL certificate is uploaded, it takes effect within one minute. To verify that the SSL certificate takes effect, send HTTPS requests to access resources. If the URL is displayed with a lock icon in the address bar of the browser, HTTPS secure acceleration is working as expected.

    ![Test result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7946219951/p3701.png)


