---
keyword: [TLS, SSL certificate]
---

# Configure TLS

You can use the Transport Layer Security \(TLS\) Version Control feature of Alibaba Cloud Content Delivery Network \(CDN\) to ensure the data security and integrity of all Internet services and communications. You can configure TLS versions based on domain names. This topic describes how to configure TLS for a domain name.

Make sure an HTTPS certificate is configured. For more information, see [Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md).

TLS is designed to ensure the security and integrity of data transmitted between two applications. HTTPS is a typical application of TLS. HTTPS, also known as HTTP over TLS, is a secure version of HTTP. HTTPS runs below the top application layer \(HTTP\) and above the transport layer \(TCP\), and provides data encryption and decryption services.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **HTTPS**.

5.  In the **TLS Version Control** section, you can enable or disable specific TLS versions based on your business requirements.

    The following table describes TLS versions.

    |TLS version|Feature|Supported browser|
    |-----------|-------|-----------------|
    |TLSv1.0|TLS 1.0 was defined in RFC 2246 in 1999 as an update to SSL 3.0. TLS 1.0 is vulnerable to various attacks, such as BEAST and POODLE attacks. TLS 1.0 can no longer protect network connections due to the low encryption performance. TLS 1.0 does not comply with Payment Card Industry Data Security Standard \(PCI DSS\).|    -   IE6+
    -   Chrome 1+
    -   Firefox 2+ |
    |TLSv1.1|TLS 1.1 was defined in RFC 4346 in 2006 as an update to TLS 1.0. TLS 1.1 fixed some vulnerabilities of TLS 1.0.|    -   IE 11+
    -   Chrome 22+
    -   Firefox 24+
    -   Safri 7+ |
    |TLSv1.2|TLS 1.2 was defined in RFC 5246 in 2008 and is the widely used TLS version.|    -   IE 11+
    -   Chrome 30+
    -   Firefox 27+
    -   Safri 7+ |
    |TLSv1.3|TLS 1.3 was defined in RFC 8446 in 2018. TLS 1.3 is the latest TLS version. TLS 1.3 supports the zero round trip time resumption \(0-RTT\) mode and allows you to establish faster connections. TLS 1.3 supports only key exchange algorithms of perfect forward secrecy to improve security.|    -   Chrome 70+
    -   Firefox 63+ |

    ![TLS version control](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9946219951/p47114.png)

    **Note:** By default, TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.


