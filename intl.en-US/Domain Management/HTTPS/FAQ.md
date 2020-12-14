# FAQ

This topic provides answers to some commonly asked questions about HTTPS settings in Alibaba Cloud Content Delivery Network \(CDN\).

-   [Will additional fees be charged after I enable HTTPS secure acceleration?](#section_fnh_ptz_zgb)
-   [Will the content retrieval speed drop and resource usage increase after I enable HTTPS secure acceleration?](#section_hlw_5tz_zgb)
-   [Do I need to enable HTTPS secure acceleration only when I log on to a website?](#section_epq_ztz_zgb)
-   [What are common types of HTTP attacks?](#section_hfq_h5z_zgb)

## Will additional fees be charged after I enable HTTPS secure acceleration?

Yes, additional fees will be charged for HTTPS secure acceleration. After HTTPS secure acceleration is enabled, data is transmitted over HTTPS between a client and a CDN node that responds to the client. Both SSL handshakes and content encryption and decryption require computations. The CDN node consumes more CPU resources to run the computations. However, the number of resources consumed by the origin server that provides the required content remains unchanged. This is because data is transmitted over HTTP between the CDN node and the origin server.

-   If you purchase an SSL certificate, additional fees are charged.

    **Note:** You can apply for free certificates in the Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com). Free certificates that are provided by Alibaba Cloud CDN are Domain Validation \(DV\) certificates. You can apply for one free certificate for each accelerated domain name. The validity period of a free certificate is one year. When a free certificate is about to expire, the system automatically renews the certificate.

-   After you configure an HTTPS certificate for an accelerated domain name, you are charged USD 0.008 for every 10,000 static HTTPS requests that are destined for CDN nodes in this domain name.

## Will the content retrieval speed drop and resource usage increase after I enable HTTPS secure acceleration?

No, the content retrieval speed will remain unchanged, and the number of consumed resources will not increase after you enable HTTPS secure acceleration.

However, the content retrieval speed may drop by about 10% the first time you access a website after you enable HTTPS secure acceleration. Compared with an HTTP connection, it takes more time for the system to establish an initial Secure Sockets Layer \(SSL\) connection. After an HTTPS connection is established, the content retrieval speed returns to normal.

## Do I need to enable HTTPS secure acceleration only when I log on to a website?

No, we recommend that you enable HTTPS secure acceleration for all web pages.

-   In terms of website security, if HTTPS secure acceleration is enabled for only some of your web pages, resources such as JavaScript or CSS files may be loaded over HTTP or based on the Alibaba Cloud CDN service that does not integrate HTTPS secure acceleration. In this case, user information may be leaked. To ensure data security, enable HTTPS secure acceleration for all web pages.
-   In terms of network performance, if HTTPS secure acceleration is enabled for only some of your web pages, requests may be redirected from HTTP URLs to HTTPS URLs or from HTTPS URLs to HTTP URLs. This decreases the content retrieval speed and downgrades the network performance.
-   In terms of support for HTTPS requests, an increasing number of browsers support HTTPS requests. Search engines index more HTTPS pages than HTTP pages.

## What are common types of HTTP attacks?

HTTPS is one of the methods that can be used to ensure secure content delivery acceleration. To ensure network security, you can integrate Alibaba Cloud CDN with the Web Application Firewall \(WAF\) service or the Anti-DDoS service. The following list shows common HTTP attacks:

-   SQL injection: a code injection technique that is used to attack data-driven applications. During this attack, malicious SQL statements are inserted into entry fields and executed in an SQL database. As a result, SQL statements are not executed as what developers have intended.
-   Cross-site scripting \(XSS\): a type of computer security vulnerability that is typically found in web applications. XSS allows attackers to inject client-side scripts into web pages. When other users visit these web pages, their identities and permissions are exploited to execute the injected scripts. This attack is intended to tamper with or even steal user information.
-   Cross-site request forgery \(CSRF\): allows attackers to forge a request after a user submits a form. Then, attackers tamper with the user data or execute a specific task. To spoof the identity of a user, CSRF is launched with XSS or based on other attack methods. For example, attackers trick the user into clicking a malicious link that is used to perform a CSRF attack.
-   HTTP header injection: When a browser is used to visit a website, HTTP is applied, regardless of the technology and framework based on which this website is designed. When data is transmitted over HTTP, a blank line lies between the header and the content of a response message. This blank line is equivalent to two carriage return \(CR\) and line feed \(LF\) character pairs \(0x0D 0A\). This blank line marks the end of the header and the start of the content. Attackers can exploit this vulnerability to inject characters into the header.
-   Open redirect: an attack that is typically launched based on a phishing attack. Attackers masquerade as a trusted entity to send a user a link. After the user clicks this link, the user is redirected to a malicious website where user data may be stolen. We recommend that all redirection operations must be authenticated. Therefore, users will not be redirected to malicious websites. One solution to this vulnerability is to add trusted URLs to a whitelist. Any redirects to domain names that are not included in the whitelist will be denied. Another solution is to add redirect tokens to trusted URLs. These URLs will be verified based on the tokens before users can be redirected to these URLs.

