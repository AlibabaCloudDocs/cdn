# FAQ {#concept_llx_zsz_zgb .concept}

-   [Does HTTPS secure acceleration incur additional fees?](#section_fnh_ptz_zgb)
-   [Will my access speed drop and resource usage increase after I enable HTTPS secure acceleration?](#section_ed2_her_pvu)
-   [Should I enable HTTPS only for when I log on to a website?](#section_itr_lv0_x3j)
-   [What are common HTTP attacks?](#section_hhv_63w_rwz)

## Does HTTPS secure acceleration incur additional fees? {#section_fnh_ptz_zgb .section}

Yes. HTTPS secure acceleration takes effect on the link from the client to the serving edge node. The SSL handshakes and content encryption and decryption all require computation, which makes the CDN server consume more CPU resources. However, the number of resources consumed on the origin server remains unchanged because the link from the serving edge node to the client still uses HTTP.

-   If you purchase a certificate, you are charged for additional fees.

    **Note:** You can apply for [free certificates](intl.en-US/Domain Management/HTTPS Acceleration/Overview of certificate formats.md#) on the [CDN console](https://cdnnext.console.aliyun.com). Free certificates provided by Alibaba Cloud CDN are of the DV certification level. You can apply for one free certificate for each accelerating domain. The validity period of a free certificate is one year. When a free certificate is about to expire, the system automatically renews it.

-   After you configure an HTTPS certificate for an accelerating domain, you are charged 0.008 USD for every 10,000 static HTTPS requests destined for CDN nodes in this domain.

## Will my access speed drop and resource usage increase after I enable HTTPS secure acceleration? {#section_ed2_her_pvu .section}

No, overall your access speed will remain the same, and the number of resources used will not increase as a result of enabling HTTPS secure acceleration. However, note that your access speed may drop by 10% the first time you access a website after you enable HTTPS because an initial Secure Sockets Layer \(SSL\) connection takes more time. After an HTTPS connection has been established, the access speed will return to normal.

## Should I enable HTTPS only for when I log on to a website? {#section_itr_lv0_x3j .section}

We do not recommend that you enable HTTPS only for when you log on to a website because this will negatively affect overall your website security and network performance. Specially, in terms of website security, if HTTPS is enabled for only some web pages, then there is the possibility that resources may be leaked while you are using HTTPS or an unsecure CDN service. Next, in terms of network performance, enabling HTTPS for only some web pages will cause the server to need to continually switch from HTTPS and HTTP, which can result in access speed decreases.

## What are common HTTP attacks? {#section_hhv_63w_rwz .section}

HTTPS is only one of the many ways to guarantee secure access. To ensure the overall network security, you need to deploy web application firewalls \(WAFs\) and defend against threats such as distributed denial-of-service \(DDoS\) attacks. Common HTTPS attacks are as follows:

-   SQL injection

    SQL injection is a code injection technique, used to attack data-driven applications, in which malicious SQL statements are inserted into entry fields for execution in an SQL database. As a result, SQL statements are not executed as what developers have expected.

-   Cross-site scripting \(XSS\)

    Cross-site scripting \(XSS\) is a type of computer security vulnerability typically found in web applications. XSS enables attackers to inject client-side scripts into web pages. When other users surf on these web pages, their identities and permissions are exploited to execute the injected scripts, which are intended to tamper with or even steal the user information.

-   Cross-site request forgery \(CSRF\)

    Cross-site request forgery \(CSRF\) enables attackers to forge a request, in which a user submits a form, thereby tampering with the user data or executing a specific task. To spoof a user's identity, CSRF is often launched with XSS or by using means such as tricking the user into clicking a link into which CSRF is embedded.

-   HTTP header injection

    When you use a browser to visit a website, HTTP is used no matter what technology and framework were used to design this website. According to HTTP, a blank line lies between the header and content of a response message. This blank line, which is equivalent to two sets of CRLF \(0x0D 0A\), marks the end of the header and the start of the content. Attackers can exploit this vulnerability to inject any characters into the header.

-   Open redirect

    Open redirect is typically launched by using a phishing attack. Attackers masquerade as a trusted entity to send a user a link. When the user clicks this link, they are redirected to a malicious website, where the user data is stolen. We recommend that all redirection operations must be authenticated, so that users will not be redirected to malicious websites. One solution to this vulnerability is to add trusted URLs to a whitelist. Any redirections to domains that are not included in the whitelist will be denied. The other solution is to add redirection tokens to trusted URLs, which will be verified based on the tokens when users are to be redirected to these URLs.


