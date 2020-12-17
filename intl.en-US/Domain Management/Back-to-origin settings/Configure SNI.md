---
keyword: [SNI, CDN, origin server]
---

# Configure SNI

If the IP address of your origin server is associated with multiple domain names, you must configure the Server Name Indication \(SNI\) feature for the origin server. When Content Delivery Network \(CDN\) nodes access the origin server over HTTPS, SNI specifies the domain name for which requests are destined.

SNI is an extension of Transport Layer Security \(TLS\) by which a client determines which hostname it is attempting to connect to at the beginning of the handshake process. This allows a server to present multiple certificates on the same IP address and TCP port number. This way, multiple HTTPS-capable websites or TLS-capable services that have different certificates can be served by the same IP address.

If your origin server uses only one IP address that is associated with multiple HTTPS-capable websites, and requests are redirected to the origin server over port 443, you must configure SNI for the origin server. SNI specifies the domain name for which requests are destined. When CDN nodes access the origin server over HTTPS, the origin server can respond with the correct certificate.

**Note:** If your origin server is an Object Storage Service \(OSS\) bucket, you do not need to configure SNI.

The following figure shows how SNI works.

![How SNI works](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4846219951/p40953.png)

SNI works based on the following process:

1.  A CDN node redirects a request to the origin server over HTTPS. The domain name for which the request is destined is specified by SNI.
2.  After the origin server receives the request, it responds with the certificate of the requested domain name based on SNI.
3.  After the CDN node receives the certificate, it establishes a secure connection to the origin server.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  On the **Configurations** tab, find the **Origin SNI** section and click **Modify**.

6.  In the **Origin SNI** dialog box, turn on the **Origin SNI** switch and enter the domain name served by the origin server.

    **Note:**

    -   The SNI feature of Alibaba Cloud CDN specifies domain names served by origin servers. If your origin server uses only one IP address that is associated with multiple HTTPS-capable websites, you must configure SNI to specify a domain name, for example, cdn.console.aliyun.com.
    -   SNI supports only specific domain names. Wildcard domain names are not supported. If the accelerated domain name is a wildcard domain name, you can [submit ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to enable SNI to automatically recognize the domain name for which requests are destined.
    ![Configure SNI](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3993247061/p40954.png)

7.  Click **OK**.


