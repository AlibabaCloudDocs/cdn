# Configure an SSL certificate for multiple domain names at a time

Alibaba Cloud Content Delivery Network \(CDN\) supports HTTPS secure acceleration. You can upload a custom certificate or select a certificate from Alibaba Cloud SSL Certificates Service in the Alibaba Cloud CDN console. The certificate ensures data security during transmission. This topic describes how to configure or update an SSL certificate for multiple domain names at a time.

Alibaba Cloud CDN supports only SSL certificates in the `Privacy-Enhanced Mail (PEM)` format. If your certificate is not in the `PEM` format, convert the certificate to the PEM format first. For more information, see [Certificate format conversion](/intl.en-US/Domain Management/HTTPS/Certificate formats.md).

HTTPS secure acceleration is a value-added service. After you enable HTTPS, you are charged based on the number of HTTPS requests. You cannot use CDN data transfer plans to offset the fees. For more information about the pricing of HTTPS secure acceleration, see [Billing of value-added services](/intl.en-US/Pricing/Billing method/Billing of value-added services.md).

Certificates are classified into the following types based on the validation levels:

-   A domain validated \(DV\) certificate has a safety lock. It only verifies the ownership of a domain name. A DV certificate verifies the ownership of a domain name by verifying the specified file of the domain name or the TXT record of the domain name.
-   An organization validated \(OV\) certificate is a standard SSL certificate that verifies the identity of an organization. An OV certificate is more trustable than a DV certificate, but the validation process is stricter and longer. OV certificates are typically used in the e-commerce, education, and gaming sectors.
-   An extended validation \(EV\) certificate follows the guidelines that are maintained by the Certification Authority Browser Forum, also known as the CA/Browser Forum. EV certificates are SSL certificates of the highest security level. Each EV certificate is identified by an object identifier \(OID\). Each OID indicates a complete enterprise name. EV certificates are widely used in sectors such as financial transactions and online banking.

**Note:** SSL certificates for Alibaba Cloud CDN do not support the Triple DES \(3DES\) algorithm.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Security & Protection** \> **HTTPS Center**.

3.  On the **Certificate Center** page, click **Add Certificate**.

4.  On the **Add Certificate** page, configure the certificate parameters.

    ![Certificate](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8707454061/p93743.png)

    |Parameter|Description|
    |---------|-----------|
    |**Certificate Source**|    -   **SSL Certificates Service**

You can apply for certificates of different providers and types in the [SSL Certificates Service console](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home).

    -   **Custom Certificate \(Certificate+Private Key\)**

If you cannot find a suitable certificate in the SSL Certificates Service console, upload a custom certificate. To upload a custom certificate, you must specify a certificate name and upload the certificate content and private key. The uploaded certificate is saved to SSL Certificates Service. You can check the certificate on the [SSL Certificates](https://yundun.console.aliyun.com/?spm=5176.2020520110.all.12.16df56a1u1IhI6&p=cas#/cas/home) page.

**Note:** After you set Certificate Source to **Custom Certificate \(Certificate+Private Key\)** and upload a certificate, if the system indicates that the certificate already exists, you can change the certificate name and try again.

    -   **Upload Custom Certificate \(Certificate\)**

If you cannot find a suitable certificate in the SSL Certificates Service console, upload a custom certificate. If you do not want to disclose the private key, you can select the **Upload Custom Certificate \(Certificate\)** option. In this case, you must create a Certificate Signing Request \(CSR\) file in the Alibaba Cloud CDN console and apply for a certificate from a certificate authority \(CA\). For more information, see [Create a CSR](/intl.en-US/Service Management/Security and protection/Create a CSR.md).

    -   **Free Certificate**

Free certificates are used for only HTTPS secure acceleration. You cannot manage free certificates or view their public or private keys in the SSL Certificates Service console.

        -   Free certificates are typically issued within one to two business days. During this period of time, you can upload a custom certificate or select a certificate from Alibaba Cloud SSL Certificates Service.

**Note:** After you submit the application, the certificate may be issued within several hours or two business days. The amount of time it takes depends on the verification process that is required by the certificate authority.

        -   A free SSL certificate is valid for one year. Before it expires, you do not need to apply for a new certificate each time you enable HTTPS acceleration. You must apply for a new certificate only if the current one has expired.
You can switch among **SSL Certificates Service**, **Custom Certificate \(Certificate+Private Key\)**, **Upload Custom Certificate \(Certificate\)**, and **Free Certificate**. |
    |**Certificate Name**|After you set **Certificate Source** to **SSL Certificates Service** or **Custom Certificate \(Certificate+Private Key\)**, you must specify a certificate name.|
    |**Certificate \(Public Key\)**|After you set **Certificate Source** to **Custom Certificate \(Certificate+Private Key\)** or **Upload Custom Certificate \(Certificate\)**, you must set this parameter. For more information, see **PEM Encoding Reference** under the **Certificate \(Public Key\)** field.|
    |**Private Key**|After you set **Certificate Source** to **Custom Certificate \(Certificate+Private Key\)**, you must set this parameter. For more information, see **PEM Encoding Reference** under the **Private Key** field.|

5.  Click **Next**.

6.  Associate one or more domain names with the certificate.

    **Note:**

    -   If a selected domain name is already associated with a certificate, the existing certificate will be replaced with the selected certificate in this step.
    -   If you set Certificate Source to **SSL Certificates Service**, **Custom Certificate \(Certificate+Private Key\)**, or **Upload Custom Certificate \(Certificate\)**, you can associate multiple domain names with the specified certificate at a time. If you use a free certificate, you can associate only one domain name with the certificate.
    ![Associate one or more domain names with the certificate](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4119438951/p53679.png)

7.  Click **OK** to deploy or update the certificate.


After a certificate is uploaded, it takes effect within one minute. To verify that the SSL certificate takes effect, send HTTPS requests to access resources. If the URL appears with a lock icon in the address bar of your browser, HTTPS secure acceleration is working as expected.

![Verify the settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7946219951/p3701.png)

