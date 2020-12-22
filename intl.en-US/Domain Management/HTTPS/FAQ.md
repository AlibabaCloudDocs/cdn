# FAQ

HTTPS is used for secure communication over networks. It provides reinforced protection for content delivery that is accelerated by Alibaba Cloud Content Delivery Network \(CDN\). Secure Sockets Layer \(SSL\) secures the data that is transmitted between clients and servers when Alibaba Cloud CDN is used to accelerate content delivery. This topic provides answers to some commonly asked questions about HTTPS secure acceleration.

-   [What is HTTPS?](#section_zwj_78b_5v6)
-   [Will additional fees be charged after I enable HTTPS secure acceleration?](#section_fnh_ptz_zgb)
-   [How can I configure an SSL certificate?](#section_8zr_wp5_tzq)
-   [Do I need to configure HTTPS secure acceleration for CDN nodes if HTTPS is configured on an origin server?](#section_lq1_dyp_bea)
-   [Do I need to update the SSL certificate in Alibaba Cloud CDN after an origin server updates its SSL certificate?](#section_zjb_jyq_cc4)
-   [Why do clients access CDN nodes over HTTP after I enable HTTPS secure acceleration?](#section_cst_8gc_503)
-   [What can I do if I failed to apply for a free SSL certificate?](#section_l5z_efq_tf3)
-   [What can I do when the system indicates a duplicate SSL certificate after I upload the certificate?](#section_37t_zop_u9j)
-   [How can I convert the SSL certificate format when the system indicates that the certificate format is invalid?](#section_nn1_mcd_0e7)
-   [Will the content retrieval speed drop and resource usage increase after I enable HTTPS secure acceleration?](#section_hlw_5tz_zgb)
-   [Do I need to enable HTTPS secure acceleration only when I log on to a website?](#section_epq_ztz_zgb)
-   [What are common types of HTTP attacks?](#section_hfq_h5z_zgb)

## What is HTTPS?

HTTPS is a security protocol that is used to encrypt data that is transmitted over HTTP. This ensures the security of data transmission. HTTP transmits data in plaintext and does not encrypt data. HTTPS is an extension of HTTP. It provides an HTTP channel that is designed to ensure data security. In HTTPS, the communication protocol is encrypted based on Transport Layer Security \(TLS\) or Secure Sockets Layer \(SSL\). HTTPS supports authenticated and encrypted connections. Therefore, it is a popular method to transmit sensitive data, such as transactions, over the Internet. When you configure HTTPS secure acceleration in the Alibaba Cloud CDN console, you must provide the certificate of your accelerated domain name. The certificate must be deployed to all CDN nodes. This can be used for encrypted data transmission over HTTPS when content delivery is accelerated through the accelerated domain name in Alibaba Cloud CDN.

## Will additional fees be charged after I enable HTTPS secure acceleration?

Yes, additional fees will be charged for HTTPS secure acceleration. After HTTPS secure acceleration is enabled, data is transmitted over HTTPS between a client and a CDN node that responds to the client. Both SSL handshakes and content encryption and decryption require computations. The CDN node consumes more CPU resources to run the computations. However, the number of resources consumed by the origin server that provides the required content remains unchanged. In this case, data is transmitted over HTTP between the CDN node and the origin server.

If you purchase an SSL certificate, additional fees are charged. To apply for free certificates, you can log on to the [SSL Certificates Service console](https://yundunnext.console.aliyun.com/?p=cas). Free certificates that are provided by Alibaba Cloud CDN are Domain Validation \(DV\) certificates. You can apply for one free certificate for each accelerated domain name. The validity period of a free certificate is one year. When a free certificate is about to expire, the system automatically renews the certificate. After you configure an SSL certificate for an accelerated domain name, you are charged USD 0.008 for every 10,000 static HTTPS requests that are submitted to CDN nodes in this domain name.

## How can I configure an SSL certificate?

You can configure an SSL certificate in the Alibaba Cloud CDN console. For more information, see [Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md).

## Do I need to configure HTTPS secure acceleration for CDN nodes if HTTPS is configured on an origin server?

Yes, you must configure HTTPS secure acceleration for CDN nodes if HTTPS is configured on an origin server. HTTPS applies to the communication between clients and an origin server. Before Alibaba Cloud CDN is activated, clients retrieve content from the origin server without the acceleration of Alibaba Cloud CDN. Therefore, HTTPS must be configured on the origin server to support content delivery. After Alibaba Cloud CDN is activated, clients interact with CDN nodes. To enable communication over HTTPS between clients and CDN nodes, an SSL certificate must be configured for your accelerated domain name and deployed to CDN nodes. For more information about how to configure the SSL certificate, see [Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md).

## Do I need to update the SSL certificate in Alibaba Cloud CDN after an origin server updates its SSL certificate?

No, you do not need to update the SSL certificate in Alibaba Cloud CDN after an origin server updates its SSL certificate. The updated SSL certificate on the origin server does not affect the SSL certificate in Alibaba Cloud CDN. You must update the SSL certificate in Alibaba Cloud CDN only when the SSL certificate has expired or is about to expire. For more information, see [Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md).

## Why do clients access CDN nodes over HTTP after I enable HTTPS secure acceleration?

Clients can access CDN nodes over HTTP or HTTPS based on client settings. To force access over HTTPS for clients, you can configure the force redirect feature in the Alibaba Cloud CDN console. For more information, see [Configure the forcible redirect feature](/intl.en-US/Domain Management/HTTPS/Configure the forcible redirect feature.md).

## What can I do if I failed to apply for a free SSL certificate?

Specific limits apply when you apply for a free SSL certificate in the Alibaba Cloud CDN console. These limits may cause the failure to apply for a free SSL certificate. In this case, we recommend that you log on to the [SSL Certificates Service console](https://yundunnext.console.aliyun.com/?p=cas) to apply for and deploy a free SSL certificate.

## What can I do when the system indicates a duplicate SSL certificate after I upload the certificate?

If the system specifies that the certificate exists, you can change the certificate name and try again. This applies after you set Certificate Source to **Upload Custom Certificate \(Certificate+Private Key\)** and upload a certificate,

## How can I convert the SSL certificate format when the system indicates that the certificate format is invalid?

Alibaba Cloud CDN supports only SSL certificates in the Privacy-Enhanced Mail \(PEM\) format. The requirements on the content of uploaded certificates vary based on different certificate authorities. For more information, see [Certificate formats](/intl.en-US/Domain Management/HTTPS/Certificate formats.md). If your certificate is not in the PEM format, convert the certificate format before it is uploaded. For more information, see [Certificate format conversion](/intl.en-US/Domain Management/HTTPS/Certificate formats.mdsection_cn2_rql_xdb).

## Will the content retrieval speed drop and resource usage increase after I enable HTTPS secure acceleration?

No, the content retrieval speed will remain unchanged, and the number of consumed resources will not increase after you enable HTTPS secure acceleration. If HTTPS is enabled for an origin server, more computing resources are consumed by the origin server when compared with communication with the origin server over HTTP. The extra resource consumption is caused by the asymmetric encryption and decryption during HTTPS handshakes. Significant resources are consumed in the case of high concurrency. Symmetric encryption and decryption require similar resources as HTTP-based communication. Therefore, more sessions may be reused. The system requires more time to enable HTTPS-based communication with the origin server than HTTP-based communication with the origin server.

To fix this issue, Dynamic Route for CDN \(DCDN\) can be used to provide end-to-end HTTPS-based communication. DCDN allows you to reduce the average amount of time that is consumed for SSL handshakes. In the case of high concurrency, the session reuse rate on the origin server is significantly increased. This way, fewer resources can be consumed to enable content delivery acceleration over HTTPS.

-   To accelerate the delivery of static content, CDN nodes serve cached content. The amount of time that is consumed for handshakes is increased, but the amount of time that is consumed for transmission is decreased. In this case, the total amount of time for content delivery acceleration is decreased. No back-to-origin process is required when the cached static content is delivered to clients. This reduces the interaction with the origin server and minimizes the resource consumption on the origin server.
-   To accelerate the delivery of dynamic content, DCDN provides more flexible and optimal routing solutions when compared with content delivery over the Internet. The requests for dynamic content must be redirected to the origin server. When DCDN is used to accelerate content retrieval from the origin server, the session reuse rate is increased and the overall transmission speed is improved. The back-to-origin process is required to accelerate dynamic content delivery. Therefore, asymmetric encryption and decryption is an important step. This increases the resource consumption on the origin server. DCDN can be used to provide end-to-end HTTPS-based communication and minimize the overall resource consumption.

## Do I need to enable HTTPS secure acceleration only when I log on to a website?

No, we recommend that you enable HTTPS secure acceleration for all web pages. HTTPS secure acceleration provides the following benefits:

-   In terms of website security, if HTTPS secure acceleration is enabled for only some of your web pages, resources such as JavaScript or CSS files may be loaded over HTTP or based on the Alibaba Cloud CDN service that does not integrate HTTPS secure acceleration. In this case, user information may be leaked. To ensure data security, enable HTTPS secure acceleration for all web pages.
-   In terms of network performance, if HTTPS secure acceleration is enabled for only some of your web pages, requests may be redirected from HTTP URLs to HTTPS URLs or from HTTPS URLs to HTTP URLs. This decreases the content retrieval speed and the network performance.
-   In terms of support for HTTPS requests, an increasing number of browsers support HTTPS requests. Search engines index more HTTPS pages than HTTP pages.

## What are common types of HTTP attacks?

HTTPS is one of the methods that can be used to ensure secure content delivery acceleration. To ensure network security, you can integrate Alibaba Cloud CDN with the Web Application Firewall \(WAF\) service or the Anti-DDoS services. The following list shows common HTTP attacks:

-   SQL injection: a code injection technique that is used to attack data-driven applications. During this attack, malicious SQL statements are inserted into entry fields and executed in an SQL database. These SQL statements are not being executed as expected.
-   Cross-site scripting \(XSS\): a type of computer security vulnerability that is commonly found in web applications. XSS allows attackers to inject client-side scripts into web pages. When other users visit these web pages, the identities and permissions of the users are exploited to execute the injected scripts. The aim of the attack is to modify or steal user information.
-   Cross-site request forgery \(CSRF\): allows attackers to forge a request after a user submits a form. Then, attackers tamper with the user data or execute a specific task. To spoof the identity of a user, CSRF is launched with XSS or based on other attack methods. For example, attackers provide a malicious link that is used to perform a CSRF attack.
-   HTTP header injection: When a browser is used to visit a website, HTTP is applied, regardless of the technology and framework based on which this website is designed. When data is transmitted over HTTP, a blank line lies between the header and the content of a response message. This blank line is equivalent to two carriage return \(CR\) and line feed \(LF\) character pairs \(0x0D 0A\). This blank line marks the end of the header and the start of the content. Attackers can exploit this vulnerability to inject characters into the header.
-   Open redirect: an attack that is commonly launched based on a phishing attack. Attackers masquerade as a trusted entity to send a user a link. After the user clicks this link, the user is redirected to a malicious website where user data may be stolen. We recommend that all redirection operations must be authenticated. This allows you to make sure that users are not redirected to other malicious websites. One solution to this vulnerability is to add trusted URLs to a whitelist. Any redirects to domain names that are not included in the whitelist will be denied. Another solution is to add redirect tokens to trusted URLs. Before users are redirected to URLs, these URLs will be verified based on the tokens.

