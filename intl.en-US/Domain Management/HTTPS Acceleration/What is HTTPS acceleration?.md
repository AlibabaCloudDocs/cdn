# What is HTTPS acceleration? {#concept_yk4_cj5_k2b .concept}

This topic provides an overview of HTTPS acceleration, including its working principles, benefits, and considerations. HTTPS acceleration allows HTTPS-based encryption between clients and CDN nodes, ensuring data security during transmission.

## What is HTTPS? {#section_54k_eg0_1u7 .section}

Hypertext Transfer Protocol \(HTTP\) transmits content in plaintext and does not encrypt data in any form. As an extension of HTTP, Hypertext Transfer Protocol Secure \(HTTPS\) is an HTTP channel designed to enhance security. Secure Sockets Layer \(SSL\) or Transport Layer Security \(TLS\) is used as a sublayer under the regular HTTP application to authenticate users and encrypt data. HTTPS is widely used for services such as payment transactions that involve sensitive user data.

According to a report released by Electronic Frontier Foundation \(EFF\) in 2017, more than 50% of Web traffic across the globe is transmitted by using HTTPS.

## Working principles {#section_vpo_41m_bwy .section}

After you enable HTTPS in the Alibaba Cloud CDN console, the requests from your client to Alibaba Cloud CDN nodes are encrypted by using HTTPS. The CDN node obtains the requested resources from the origin site and then returns them to your client based on the origin configuration. We recommend that you configure and enable HTTPS on the origin site to allow end-to-end HTTPS encryption.

The following figure shows the HTTPS encryption process.

![Flowchart](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15469/156587028147884_en-US.png)

1.  The client sends an HTTPS access request.
2.  The server generates a public key and a private key, which you can prepare on your own or apply for from a professional organization.
3.  The server sends the public key certificate file to the client.
4.  The client parses the certificate file to check the file correctness.

    -   If the certificate file is correct, the client generates a random number \(key\) and uses this key to encrypt and transmit data to the server.
    -   If the certificate file is incorrect, the SSL handshake between the client and server fails.
    **Note:** A correct certificate file meets the following requirements: The certificate has not expired. The certificate is issued by a trusted certificate authority \(CA\). The digital signature of the issuer in the certificate can be decrypted by using the public key of the issuer. The domain name in the certificate is the same as that of the server.

5.  The server decrypts the private key to obtain a random number \(key\).
6.  The server uses the obtained key to encrypt and transmit data to the client.
7.  The client uses the key to decrypt the data.

## Benefits {#section_uw1_jft_zgb .section}

-   HTTPS can defend against the following security threats, which are common in HTTP:
    -   Eavesdropping: Third parties can intercept the data.
    -   Tampering: Third parties can alter the transmitted data.
    -   Spoofing: Third parties can impersonate the identity of a user.
    -   Hijacking: includes traffic hijacking, link hijacking, and DNS hijacking.
-   Benefits of HTTPS transmission:
    -   HTTPS encrypts sensitive information such as session IDs and cookies before transmission, preventing security threats caused by sensitive information leakage.
    -   HTTPS is the new norm. An increasing number of mainstream browsers such as Google Chrome and Mozilla Firefox automatically identified HTTP websites as insecure in 2018. If an organization insists on using HTTP, they will face security vulnerabilities. Furthermore, when users visit the organization's website by using these browsers, they will be prompted that this website is insecure, which compromises user experience and hence reduces visits to this website.
    -   Major network service providers such as Google and Baidu prioritize HTTPS websites in the search results. Additionally, mainstream browsers must support HTTPS to support HTTP/2. HTTPS is the more reliable choice in terms of security, market presence, and user experience. Therefore, we recommend that you upgrade your access protocol to HTTPS.

## Scenarios {#section_yh4_zft_zgb .section}

The following table describes the five scenarios of HTTPS.

|Scenario|Description|
|--------|-----------|
|Enterprise application|HTTPS protects confidential information such as customer relationship management \(CRM\) data and enterprise resource planning \(ERP\) data on enterprise websites from being hijacked or intercepted.|
|Government website|HTTPS protects authoritative information on government websites against vulnerabilities such as phishing and hijacking. Leakage of such information may cause the public trust in the government to decline.|
|Payment system|HTTPS protects sensitive data such as the customer names and phone numbers that are involved in payment transactions against hijacking and spoofing. If HTTPS is not used, the customer may receive information about the order they have placed and may be tricked into making a duplicate payment, which causes losses to both the customer and the enterprise.|
|API|APIs use HTTPS to encrypt important information such as sensitive data and crucial operation instructions, so that the information cannot be hijacked.|
|Enterprise website|HTTPS makes users feel more secure. Web browsers display a green lock icon in the address bar for websites with domain validated \(DV\) and organization validated \(OV\) certificates. The enterprise name is displayed together with the green lock for websites with extended validated \(EV\) certificates.|

## Considerations {#section_s4o_tue_gju .section}

The following table describes the considerations for using the HTTPS acceleration function.

|Category|Consideration|
|--------|-------------|
|Configuration| -   The following types of business support HTTPS acceleration:
    -   [Images and small files](../../../../reseller.en-US/Product Introduction/Scenarios/Images and small files.md#) 

Web portals, e-commerce websites, news websites and applications, government or enterprise official websites, and entertainment or gaming websites and applications.

    -   [Large file download](../../../../reseller.en-US/Product Introduction/Scenarios/Large file download.md#) 

Video or audio applications and websites that provide content for users to download.

    -   [VOD](../../../../reseller.en-US/Product Introduction/Scenarios/VOD.md#) 

Websites and applications that provide audio and video content such as movies, online education, news, and social networking.

    -   [Live Streaming](../../../../reseller.en-US/Product Introduction/Scenarios/Live Streaming.md#) 

Websites and live streaming platforms of industry verticals that provide live streaming content such as interactive online education, esports, talent show, or event broadcasts.

-   You can enable HTTPS for wildcard domains.
-   You can enable or disable HTTPS acceleration as needed.
    -   When HTTPS acceleration is enabled: You can modify certificates. The system supports HTTP and HTTPS requests by default. In addition, you can [Enable force redirect](reseller.en-US/Domain Management/HTTPS Acceleration/Enable force redirect.md#) to customize request methods.
    -   When HTTPS acceleration is disabled: The system no longer supports HTTPS requests and no longer keeps certificate or private key information. To enable certificates again, you must re-upload the certificates or private keys. For more information, see [Configure HTTPS certificates](reseller.en-US/Domain Management/HTTPS Acceleration/Configure HTTPS certificates.md#).
-   You can view certificates but not private keys. Keep certificate-related information safe.
-   You can update certificates. However, exercise caution when performing this operation. HTTPS certificates take effect within one minute after they are updated.

 |
|Billing| HTTPS acceleration is a value-added service. After you enable HTTPS, HTTPS requests incur additional fee. For more information about the billing standards, see [Static HTTPS Requests](../../../../reseller.en-US/Pricing/Billing method/Value-added service.md#section_jdt_lwl_zdb).

**Note:** The fee is separately charged based on HTTPS requests and is not covered by the CDN data transfer plan. Before you enable HTTPS acceleration, make sure that your account has a sufficient balance. If your balance becomes empty, the CDN services are suspended.

 |
|Certificates| -   You need to upload certificate and private key files in `PEM` format for domains for which HTTPS acceleration is enabled.

**Note:** The Tengine Web server used by CDN is designed based on the NGINX Web server architecture, and therefore supports only certificate files in the NGINX-compatible `PEM` format. For more information, see [Overview of certificate formats](reseller.en-US/Domain Management/HTTPS Acceleration/Overview of certificate formats.md#).

-   The uploaded certificate file must match the private key. Otherwise, the authentication fails.
-   A private key cannot carry a password.
-   Only SSL and TLS handshakes carrying SNIs are supported.

 |

## Related functions {#section_j9y_dnt_f6u .section}

You can enable the following functions as needed to increase data security.

|Function|Description|
|--------|-----------|
|[Configure HTTPS certificates](reseller.en-US/Domain Management/HTTPS Acceleration/Configure HTTPS certificates.md#)|Allows for HTTPS acceleration.|
|[Enable HTTP/2](reseller.en-US/Domain Management/HTTPS Acceleration/Enable HTTP__2.md#)|HTTP/2 is the most advanced HTTP protocol, which is used by major browsers such as Google Chrome, Internet Explorer 11, Safari, and Mozilla Firefox.|
|[Enable force redirect](reseller.en-US/Domain Management/HTTPS Acceleration/Enable force redirect.md#)|Supports force redirects on original request methods of end users.|
|[Configure TLS](reseller.en-US/Domain Management/HTTPS Acceleration/Configure TLS.md#)|Helps to ensure communication security and data integrity.|
|[Configure HSTS](reseller.en-US/Domain Management/HTTPS Acceleration/Configure HSTS.md#)|Forces clients such as browsers to establish HTTPS connections with servers, reducing hijacking risks in the first access requests.|

