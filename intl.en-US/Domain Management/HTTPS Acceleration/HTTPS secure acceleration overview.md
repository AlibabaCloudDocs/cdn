# HTTPS secure acceleration overview {#concept_yk4_cj5_k2b .concept}

This topic provides an overview of HTTPS secure acceleration, including its working principles, scenarios, benefits, notes, and related functions. HTTPS secure acceleration allows for HTTPS-based encryption between clients and CDN nodes, ensuring the level of security for data that is being transmitted.

## What is HTTPS? {#section_54k_eg0_1u7 .section}

Hypertext Transfer Protocol Secure \(HTTPS\) is the secure version of Hypertext Transfer Protocol \(HTTP\), which transmits data in plaintext. In HTTPS, Secure Sockets Layer \(SSL\) or Transport Layer Security \(TLS\) is used as a sublayer under the regular HTTP application layering to authenticate users and encrypt data. HTTPS is widely used for such services as transactional payment that involve sensitive user data.

According to a report released by Electronic Frontier Foundation \(EFF\) in 2017, more than 50% of web traffic across the globe is transmitted by using HTTPS.

## Working principles {#section_vpo_41m_bwy .section}

After you enable HTTPS on the Alibaba Cloud CDN console, the requests from your client to an Alibaba Cloud CDN node are encrypted by using HTTPS. This CDN node obtains the requested resources from the serving origin and then returns them to your client according to the origin configuration. We recommend that you also enable HTTPS on the origin to allow for full-link HTTPS encryption.

The following figure shows the HTTPS encryption process.

![HTTPS principle](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15469/156505452847884_en-US.png)

1.  The client sends an HTTPS access request.
2.  The server generates a public key and a private key, which you can prepare on your own or apply for from a professional organization.
3.  The server sends the public key certificate file to the client.
4.  The client parses the certificate file to check the file correctness.

    -   If the certificate file is correct, the client generates a random number \(key\) and uses this key to encrypt and transmit data to the server.
    -   If the certificate file is incorrect, the SSL handshake between the client and server fails.
    **Note:** A correct certificate file meets the following requirements:

    -   The certificate has not expired.
    -   The certificate is issued by a trustable CA.
    -   The digital signature of the issuer in the certificate can be decrypted by using the public key of the issuer.
    -   The domain name in the certificate is the same as that of the server.
5.  The server decrypts the private key to obtain a random number \(key\).
6.  The server uses the obtained key to encrypt and transmit data to the client.
7.  The client uses the key it has obtained to decrypt the data.

## Benefits {#section_uw1_jft_zgb .section}

-   HTTPS can defend against the following security threats, which are common in HTTP:
    -   Eavesdropping: A third party can intercept the data that is being transmitted.
    -   Unauthorized change: A third party can alter the data that is being transmitted.
    -   Spoofing: A third party can spoof the identify of a user in communication.
    -   Traffic hijacking: includes page hijacking and DNS hijacking.
-   HTTPS protects your data such as session IDs and cookies from being captured.
-   HTTPS checks data security to protect your DNS or content from being hijacked or altered.
-   HTTPS is becoming a trend. An increasing number of leading browsers such as Google Chrome 70 or later and Mozilla Firefox identify HTTP websites as insecure. If an organization insists on using HTTP, they will face security vulnerabilities. Furthermore, when users visit the organization's website by using these browsers, they will be prompted that this website is insecure, which compromises user experience and hence reduces visits to this website.
-   HTTPS is more secure, caters to the market, and can make user experience better. Major service providers such as Baidu and Google add search weights to HTTPS websites. Additionally, leading browsers must support HTTPS so that they support HTTP/2. Therefore, we recommend that you upgrade your access protocol to HTTPS.

## Scenarios {#section_yh4_zft_zgb .section}

HTTPS is used in the following five scenarios.

|Scenario|Description|
|--------|-----------|
|Enterprise application|HTTPS protects confidential information such as customer relationship management \(CRM\) data and enterprise resource planning \(ERP\) data at the website of an enterprise from being hijacked or intercepted. If such data is hijacked or intercepted, the enterprise faces disastrous damages.|
|Government website|HTTPS protects authoritative, correct information at government websites against vulnerabilities such as phishing and hijacking. Leakage of such information may incur a public or trust crisis against the government.|
|Payment system|HTTPS protects sensitive data such as the customer name and phone number involved in a payment against hijacking and spoofing. If HTTPS is not used, the customer may receive details such as the name and address about the order they have placed and then may be tricked into making a duplicate payment, which incurs losses to both the customer and the enterprise.|
|API|HTTPS enables APIs to encrypt important information such as sensitive data and crucial operation instructions, so that the information will not be hijacked when it is being transmitted.|
|Enterprise website|HTTPS makes users feel more secure. When HTTPS is enabled, a safe lock icon is displayed in the address box for DV and OV. For EV, however, a safe lock icon is displayed in the address box, which is in green, with the enterprise name incorporated.|

## Notes {#section_s4o_tue_gju .section}

|Category|Notes|
|--------|-----|
|Configuration| -   The following are service types that support HTTPS secure acceleration:
    -   [Image and Small File](../../../../intl.en-US/Product Introduction/Scenarios/Image and Small File.md#): This service is suitable for web portals, e-commerce websites, news websites and applications, government or enterprise official websites, and entertainment or gaming websites and applications.
    -   [Acceleration for large static files](../../../../intl.en-US/.md#): This service is suitable to audio and video applications and to websites that provides content for users to download.
    -   [VOD](../../../../intl.en-US/Product Introduction/Scenarios/VOD.md#): This service is suitable to websites and applications that provide audio and video content such as movies, online education, news, and social networking.
    -   [Live Streaming](../../../../intl.en-US/Product Introduction/Scenarios/Live Streaming.md#): This service is suitable to suitable to websites and vertical industry portals that provide live streaming content such as interactive online education and live game, show, or event broadcasts.
    -   [DCDN](../../../../intl.en-US/Product Introduction/Scenarios/DCDN.md#): This service is suitable to e-commerce, social networking, government, enterprise, gaming, and finance platforms.
-   You can enable HTTPS for wildcard domains.
-   You can enable or disable HTTPS secure acceleration as needed.
    -   When HTTPS secure acceleration is enabled: You can modify certificates. The system supports HTTP and HTTPS requests by default. In addition, you can enable the Force Redirect function to customize request methods. For more information, see [Enable Force Redirect](intl.en-US/Domain Management/HTTPS Acceleration/Enable Force Redirect.md#).
    -   When HTTPS secure acceleration is disabled: The system no longer supports HTTPS requests. In addition, the system no longer reserve certificate or private key information. To enable certificates again, you need to re-upload the certificates or private keys. For more information, see [Configure HTTPS certificates](intl.en-US/Domain Management/HTTPS Acceleration/Configure HTTPS certificates.md#).
-   You can view certificates but not private keys. Keep certificate-related information safe.
-   You can update certificates but with caution. An HTTPS certificate takes effect on the entire network after being updated.

 |
|Billing| HTTPS secure acceleration is a value-added service. It is independently charged based on the number of HTTPS requests. For more information about the billing standards, see [Value-added service](../../../../intl.en-US/Pricing/Billing method/Value-added service.md#).

**Note:** The charges for HTTPS secure acceleration are not counted in the CDN service package. Before you enable HTTPS secure acceleration, make sure that your account has a sufficient balance. If your balance is used up, your CDN services become unavailable.

 |
|Certificates| -   You need to upload certificate and private files in PEM format for domains for which HTTPS secure acceleration is enabled.

**Note:** The Tengine web server used by CDN is designed based on the Nginx web server architecture and therefore supports only certificate files in PEM format, which can be read by Nginx. For more information, see [Overview of certificate formats](intl.en-US/Domain Management/HTTPS Acceleration/Overview of certificate formats.md#).

-   The uploaded certificate file must match the private key. Otherwise, the authentication fails.
-   A private key cannot carry a password.
-   Only SSL and TLS handshakes carrying SNIs are supported.

 |

## Related functions {#section_j9y_dnt_f6u .section}

You can enable the following functions as needed to increase data security:

|Function|Description|
|--------|-----------|
|[Configure HTTPS certificates](intl.en-US/Domain Management/HTTPS Acceleration/Configure HTTPS certificates.md#)|Allows for HTTPS secure acceleration.|
|[Enable HTTP/2](intl.en-US/Domain Management/HTTPS Acceleration/Enable HTTP__2.md#)|The most advanced HTTP protocol, which is used by most major browsers such as Google Chrome, Internet Explorer 11, Safari, and Mozilla Firefox.|
|[Enable Force Redirect](intl.en-US/Domain Management/HTTPS Acceleration/Enable Force Redirect.md#)|Supports force redirects on users' original request methods.|
|[EN-US\_TP\_41679.md\#](intl.en-US/Domain Management/HTTPS Acceleration/Configure TLS.md#)|Helps to ensure communication security and data integrity.|
|[Configure HSTS](intl.en-US/Domain Management/HTTPS Acceleration/Configure HSTS.md#)|Forces clients such as browsers to establish HTTPS connections with servers, reducing hijacking risks in the first access requests.|

