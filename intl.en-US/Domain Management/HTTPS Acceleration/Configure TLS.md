# Configure TLS {#task_261642 .task}

You can use the TLS Version Control function of Alibaba Cloud CDN to ensure the data security and integrity of all Internet services and communications. You can configure TLS versions based on domain names. This topic describes how to configure TLS for a domain.

Make sure an HTTPS certificate is configured. For more information, see [Configure HTTPS certificates](reseller.en-US/Domain Management/HTTPS Acceleration/Configure HTTPS certificates.md#).

Transport Layer Security \(TLS\) is designed to ensure the security and integrity of data transmitted between two applications. HTTPS is a typical application of TLS. HTTPS, also known as HTTP over TLS, is a secure version of HTTP. HTTPS runs below the top application layer \(HTTP\) and above the transport layer \(TCP\), providing data encryption and decryption services.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the **TLS Version Control** section, you can enable or disable specific TLS versions as needed. 

    The following table describes TLS versions.

    |TLS version|Description|Supported browser|
    |-----------|-----------|-----------------|
    |TLS 1.0|TLS 1.0 was defined in RFC 2246 in 1999 as an upgrade of SSL 3.0. This version is vulnerable to various attacks such as BEAST and POODLE attacks. It is not strong enough to protect today's network connections and does not comply with Payment Card Industry Data Security Standard \(PCI DSS\).|     -   Internet Explorer 6 and later
    -   Google Chrome 1 and later
    -   Mozilla Firefox 2 and later
 |
    |TLS 1.1|TLS 1.1 was defined in RFC 4346 in 2006 as an update for TLS 1.0. This version fixed some vulnerabilities of TLS 1.0.|     -   Internet Explorer 11 and later
    -   Google Chrome 22 and later
    -   Mozilla Firefox 24 and later
    -   Safari 7 and later
 |
    |TLS 1.2|TLS 1.2 was defined in RFC 5246 in 2008 and has become the most widely used TLS version.|     -   Internet Explorer 11 and later
    -   Google Chrome 30 and later
    -   Mozilla Firefox 27 and later
    -   Safari 7 and later
 |
    |TLS 1.3|TLS 1.3 was defined in RFC 8446 in 2018. TLS 1.3 is faster because it supports the 0-RTT mode. Also, this version is more secure as it only supports perfect forward secrecy key exchange algorithms.|     -   Google Chrome 70 and later
    -   Mozilla Firefox 63 and later
 |

    ![TSL Version Control](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41679/156653143547114_en-US.png)

    **Note:** TLS 1.0, TLS 1.1, and TLS 1.2 are enabled by default.


