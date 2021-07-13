---
keyword: [HTTPS secure acceleration, CDN]
---

# What is HTTPS secure acceleration?

This topic describes the benefits and usage notes of HTTPS secure acceleration and how it works. HTTPS secure acceleration is used to encrypt HTTPS connections between clients and Alibaba Cloud CDN nodes. HTTPS ensures data security during transmission.

## HTTPS overview

HTTP transmits data in plaintext and does not encrypt data. As an extension of HTTP, HTTPS is an HTTP channel designed to ensure data security. In HTTPS, the communication protocol is encrypted by using Transport Layer Security \(TLS\) or Secure Sockets Layer \(SSL\). HTTPS is used to authenticate users and encrypt connections. HTTPS is widely used to protect sensitive user data for services such as payment transactions.

A report released by Electronic Frontier Foundation \(EFF\) in 2017 shows that more than 50% of web traffic worldwide is transmitted over HTTPS.

## How it works

After you enable HTTPS in the Alibaba Cloud CDN console, requests are transmitted from clients to Alibaba Cloud CDN nodes over encrypted HTTPS connections. CDN nodes retrieve requested resources from origin servers and then return the resources to clients based on the HTTPS settings of the origin servers. We recommend that you configure and enable HTTPS for your origin server to implement end-to-end HTTPS encryption.

The following figure shows how HTTPS works.

![How HTTPS works](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3946219951/p47884.png)

1.  The client sends a request over HTTPS.
2.  The server has the public and private keys prepared.

    **Note:** You can bring your own public and private keys, apply for public and private keys from a professional organization, or apply for a free certificate in the Alibaba Cloud CDN console.

3.  The server sends the public key to the client.
4.  The client verifies the certificate.

    -   If the certificate is valid, the client generates a random number as a private key. The client uses the public key to encrypt the random number and transmits the number \(private key\) to the server.
    -   If the certificate is invalid, the SSL handshake fails. You must upload another certificate for authentication.
    **Note:** A certificate is considered valid if the following requirements are met:

    -   The certificate is not expired.
    -   The certificate is issued by a trusted certificate authority \(CA\).
    -   The public key of the certificate can decrypt the signature of the server certificate.
    -   The domain name on the server certificate is the same as the actual domain name that is hosted on the server.
5.  The server uses the private key to decrypt the encrypted random number.
6.  The server uses the random number to encrypt data transmitted from the server.
7.  The client uses the random number to decrypt the received data.

## Benefits

HTTPS secure acceleration provides the following benefits:

-   HTTPS secure acceleration protects communications from eavesdropping, tampering, impersonation attacks, and man-in-the-middle \(MITM\) attacks.
-   HTTPS encrypts sensitive information such as session IDs and cookies before transmission. This minimizes the risk of sensitive information leaks.
-   HTTPS checks data integrity during transmission to protect the data from MITM attacks, such as DNS hijacking and tampering.
-   HTTPS is the new standard. An increasing number of mainstream browsers such as Google Chrome 70 and later and Mozilla Firefox have labeled HTTP web URLs as not secure since 2018. If you choose to use HTTP, your website may be exposed to security risks. Users who visit your website by using these browsers are prompted that this website is not secure. This compromises user experience and may reduce visits to the website.
-   Mainstream browsers prioritize HTTPS web URLs in the search results. In addition, mainstream browsers must support HTTPS before they can support HTTP/2. HTTPS is a more reliable choice in terms of security, market presence, and user experience. Therefore, we recommend that you upgrade your communication protocol to HTTPS.

## Scenarios

The following table describes the scenarios of HTTPS secure acceleration.

|Scenario|Description|
|--------|-----------|
|Enterprise application|HTTPS protects confidential information on enterprise websites from being hijacked or intercepted. Confidential information, such as customer relationship management \(CRM\) data and enterprise resource planning \(ERP\) data, is protected during transmission.|
|Public service websites|HTTPS protects sensitive information on public service websites against attacks such as phishing and hijacking. Leaks of such information may compromise public trust.|
|Payment systems|HTTPS protects sensitive data such as customer names and phone numbers used in payment transactions against hijacking and spoofing. If sensitive data is leaked, attackers can use such data to trick customers into making duplicate payments. This causes losses to both the customer and the enterprise.|
|API operations|API operations can use HTTPS to encrypt important information, such as sensitive data and important instructions. This protects the information against hijacking.|
|Enterprise websites|HTTPS improves user trust and experience. Web browsers display a lock icon in the address bar for websites with domain validated \(DV\) or organization validated \(OV\) certificates. The enterprise name is displayed together with the lock icon for websites that include extended validated \(EV\) certificates.|

## Usage notes

The following table describes the usage notes of HTTPS secure acceleration.

|Category|Usage note|
|--------|----------|
|Configuration|-   The following scenarios support HTTPS secure acceleration:
    -   [Image and small file distribution](/intl.en-US/Product Introduction/Scenarios.md)

Accelerates content delivery for web portals, e-commerce websites, news websites, entertainment websites, and game websites.

    -   [Large file distribution](/intl.en-US/Product Introduction/Scenarios.md)

Accelerates the delivery of files that are larger than 20 MB, such as game installation packages, application updates, ROM upgrades, and application packages.

    -   [On-demand audio and video streaming](/intl.en-US/Product Introduction/Scenarios.md)

Accelerates content delivery for websites and applications that provide audio and video content, such as movies, online education, news, and social networking.

-   You can enable HTTPS for wildcard domain names.
-   You can enable or disable HTTPS secure acceleration based on your business requirements.
    -   When HTTPS secure acceleration is enabled, you can modify SSL certificates. The system supports HTTP and HTTPS requests by default. You can also configure the force redirect feature to customize request methods. For more information, see [Configure the forcible redirect feature](/intl.en-US/Domain Management/HTTPS/Configure the forcible redirect feature.md).
    -   When HTTPS secure acceleration is disabled, the system no longer supports HTTPS requests or retains the SSL certificate or private key information. When you enable HTTPS secure acceleration again, you must upload an SSL certificate or private key again. For more information, see [Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md).
-   You can view SSL certificates. You cannot view private keys because they are sensitive information Keep certificate-related information confidential.
-   You can renew an SSL certificate. Proceed with caution. After an SSL certificate is renewed, it takes effect within one minute. |
|Billing|HTTPS secure acceleration is a value-added service. After you enable HTTPS, you are charged based on the number of HTTPS requests. For more information, see [Billing of value-added services](/intl.en-US/Pricing/Billing method/Billing of value-added services.md).

**Note:** HTTPS requests are separately billed and the fees cannot be offset by data transfer plans of Alibaba Cloud CDN. Before you enable HTTPS secure acceleration, make sure that you have a sufficient balance in your Alibaba Cloud account. If the balance is insufficient, Alibaba Cloud CDN may be suspended. |
|SSL certificate|-   You must upload SSL certificates and private keys in `PEM` format for domain names for which you want to enable HTTPS secure acceleration.

**Note:** The Tengine web server used by Alibaba Cloud CDN is designed based on the NGINX web server architecture. Therefore, the web server supports only certificate files in NGINX-compatible `PEM` format. For more information, see [Certificate formats](/intl.en-US/Domain Management/HTTPS/Certificate formats.md).

-   The uploaded SSL certificate must match the private key. Otherwise, requests sent from clients fail the authentication.
-   A private key cannot carry a password.
-   Only SSL and TLS handshakes that include Server Name Indication \(SNI\) values are supported. |

## Related features

You can enable the following features as needed to enhance data security.

|Feature|Description|
|-------|-----------|
|[Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md)|Enables HTTPS secure acceleration.|
|[Enable HTTP/2](/intl.en-US/Domain Management/HTTPS/Enable HTTP/2.md)|Enables the latest HTTP protocol, HTTP/2. HTTP/2 is supported by mainstream browsers such as Google Chrome, Internet Explorer 11, Safari, and Mozilla Firefox.|
|[Configure the forcible redirect feature](/intl.en-US/Domain Management/HTTPS/Configure the forcible redirect feature.md)|Redirects requests to corresponding HTTP or HTTPS URLs.|
|[Configure TLS](/intl.en-US/Domain Management/HTTPS/Configure TLS.md)|Ensures communication security and data integrity.|
|[Configure HSTS](/intl.en-US/Domain Management/HTTPS/Configure HSTS.md)|Forces clients such as browsers to communicate with servers over HTTPS. This reduces the risk of cookie hijacking.|

