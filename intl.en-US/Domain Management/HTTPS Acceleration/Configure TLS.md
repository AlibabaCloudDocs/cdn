# Configure TLS {#task_261642 .task}

This topic describes how to configure Transport Layer Security \(TLS\) for a domain. You can use the TLS Version Control function of Alibaba Cloud CDN to ensure the security and data security of all Internet services and communications.

HTTPS certificates are configured. For more information, see [Configure HTTPS certificates](intl.en-US/Domain Management/HTTPS Acceleration/Configure HTTPS certificates.md#).

TLS is used at the transport layer to ensure the security and integrity of data transmitted between two entities.

TLS has four versions:

-   TLS 1.0

    TLS 1.0 was defined in RFC 2246 in 1999 as an upgrade of SSL 3.0. This version is vulnerable to various attacks such as BEAST attacks and POODLE attacks. It is not strong enough to protect today's network connections and does not comply with Payment Card Industry Data Security Standard \(PCI DSS\). TLS 1.0 supports major browsers including Internet Explorer 6.0 or later, Google Chrome 1.0 or later, and Mozilla Firefox 2.0 or later.

-   TLS 1.1

    TLS 1.1 was defined in RFC 4346 in 2006 as an update from TLS 1.0. This version fixed some vulnerabilities of TLS 1.0. TLS 1.1 supports major browsers including Internet Explorer 11.0 or later, Google Chrome 22.0 later, Mozilla Firefox 24.0 or later, and Safari 7.0 or later.

-   TLS 1.2

    TLS 1.2 was defined in RFC 5246 in 2008 and has become the most widely used TLS version. TLS 1.2 supports major browsers including Internet Explorer 11.0 or later, Google Chrome 30.0 or later, Mozilla Firefox 27.0 or later, and Safari 7.0 or later.

-   TLS 1.3

    TLS 1.3 was defined in RFC 8446 in 2018. As the latest TLS version, TLS 1.3 is faster because it supports the 0-RTT mode. Also, this version is more secure because it only supports perfect forward secrecy key exchange algorithms. TLS 1.3 supports major browsers including Google Chrome 70.0 or later and Mozilla Firefox 63.0 or later.


1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the domain name you want to set, and in the **Actions** column click **Manage**.
4.  In the left-side navigation pane, click **HTTPS**.
5.  In the **TLS Version Control** section, enable or disable the TLS versions you want. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41679/156505457947114_en-US.png)

    **Note:** TLSv1.0, TLSv1.1, and TLSv1.2 are enabled by default.


