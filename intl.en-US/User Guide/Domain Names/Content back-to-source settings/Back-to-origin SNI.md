# Back-to-origin SNI {#concept_wb3_ndh_chb .concept}

This topic describes the working concepts and application scenarios related to back-to-origin Server Name Indication \(SNI\). The purpose of this topic is to help you decide whether you want to enable back-to-origin SNI.

## Description {#section_lls_bbd_dhb .section}

What is Server Name Indication \(SNI\)?

SNI is an extension to the Transport Layer Security \(TLS\) protocol by which a client determines which hostname it is attempting to connect to at the start of the handshaking process. This allows a server to present multiple certificates on the same IP address and TCP port number, and hence allows multiple secure \(HTTPS\) websites \(or any other service over TLS\) to be served by the same IP address without requiring all those sites to use the same certificate.

When a server uses a single IP address to provide HTTPS services for multiple domains, the requests for accessing the server must carry SNIs. The server can correctly return the certificates associated with the domains only when the SNIs specify the requested domains.

When do I need to enable back-to-origin SNI?

If your origin server uses one IP address to provide HTTPS services for multiple domains and port 443 is specified for receiving back-to-origin traffic on your CDN \(CDN nodes communicate with your origin server according to HTTPS\), you need to enable back-to-origin SNI and specify the requested domains. When a CDN node communicates with your origin server according to HTTPS, your origin server can correctly return the certificates associated with the requested domains.

**Note:** If your origin is Alibaba Cloud OSS, you do not need to enable back-to-origin SNI.

## Working concepts {#section_nsf_kbd_dhb .section}

The following figure shows the working concepts of back-to-origin SNI.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/155901335540953_en-US.png)

1.  The CDN node requests to access the origin server according to HTTPS, where the requested domain name is specified in the SNI.
2.  After receiving the request, the origin server sends the certificate associated with the requested domain to the CND node.
3.  After receiving the certificate, the CDN node establishes a secure connection with the origin server.

## Procedure {#section_hpn_pbd_dhb .section}

1.  Log on to the [CDN console](https://cdn.console.aliyun.com), and in the left-side navigation pane choose **Domain Names**.
2.  On the Domain Names page, select the target domain for which you want to set SNI, and then in the **Actions** column click **Manage**.
3.  On the page that is displayed, in the left-side navigation pane choose **Back-to-Origin**, and in the workspace click the **Back-to-origin configuration** tab. On the Back-to-origin configuration tab page, click **Modify** in the **Back-to-origin SNI** area.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/155901335540954_en-US.png)

4.  In the Back-to-origin SNI dialog box, set **Back-to-origin** to on, enter the name of the domain served by your origin server, and click **Confirm**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/155901335541376_en-US.png)


