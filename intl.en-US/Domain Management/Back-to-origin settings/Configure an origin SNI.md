---
keyword: [origin SNI, CDN, origin server]
---

# Configure an origin SNI

If an origin IP address is associated with multiple domain names, you must set a Server Name Indication \(SNI\) value. This allows CDN nodes to access the origin server over HTTPS.

SNI is an extension of Transport Layer Security \(TLS\) by which a client determines which hostname it is attempting to connect to at the beginning of each handshake process. This allows a server to present multiple certificates on the same IP address and TCP port number. This way, multiple HTTPS websites \(or other services over TLS\) that have different certificates can be served by the same IP address.

If an origin server uses one IP address to provide HTTPS services through multiple domain names and you have specified port 443 for Alibaba Cloud CDN to communicate with the origin server, you must set an SNI value to specify the requested domain name. This way, when a CDN node wants to access the origin server over HTTPS, the origin server can return the valid certificate of the requested domain name.

**Note:** If Alibaba Cloud Object Storage Service \(OSS\) serves your origin content, you do not need to set an SNI value.

The following figure shows how an SNI value works.

![How SNI works](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4846219951/p40953.png)

You can manage an SNI header in the following procedure:

1.  A CDN node wants to access the origin server over HTTPS. The requested domain name is included in the SNI header.
2.  After the origin server receives the request, it sends the certificate of the requested domain name to the CDN node.
3.  After the CDN node receives the certificate, it establishes a secure connection to the origin server.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  In the **Origin SNI** section, click **Modify**.

6.  Turn on **Origin SNI** and enter the requested domain name in the SNI field.

    ![Origin SNI](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3993247061/p40954.png)

    **Note:** In Alibaba Cloud CDN, SNI specifies a domain name of your origin server. If your origin server uses one IP address to provide HTTPS services through multiple domain names, you must set an SNI value to specify the requested domain name. For example, cdn.console.aliyun.com can be specified.

7.  Click **OK**.


