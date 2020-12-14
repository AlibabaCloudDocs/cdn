---
keyword: [HSTS, CDN, HTTPS connection]
---

# Configure HSTS

This topic describes how to configure HTTP Strict Transport Security \(HSTS\). After HSTS is configured, a client can establish only HTTPS connections to Alibaba Cloud Content Delivery Network \(CDN\). HSTS allows you to protect against cookie hijacking.

Make sure an HTTPS certificate is configured. For more information, see [Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md).

After HTTPS is enabled for your website, the requests that are destined for HTTP URLs are redirected to the specified URLs that use HTTPS based on the HTTP status codes 301 and 302. This applies when you enter an HTTP URL in the address bar of the browser or click an HTTP URL. During the redirect process, the request may be hijacked. As a result, the redirected requests cannot be sent to the origin server of the website. HSTS is introduced to resolve this issue.

After a browser receives an HTTP request, if the HSTS header for the domain name does not expire, the browser redirects the request to HTTPS. The browser also returns the HTTP status code 307. This way, the 301 or 302 redirect requests between the browser and the origin server cannot be intercepted.

The HSTS response header is provided in the format of `Strict-Transport-Security:max-age=expireTime [;includeSubDomains] [;preload]`. The following table describes the parameters in the header.

|Parameter|Description|
|---------|-----------|
|max-age|The maximum time period during which the requested resource is cached. Unit: seconds.|
|includeSubDomains|Optional. If this parameter is set, the preceding parameters apply to all subdomains of the domain name.|
|preload|Optional. This parameter allows you to add the domain name to the HSTS preloaded list of the browser.|

**Note:**

-   Before HSTS takes effect, the first HTTP request is redirected to HTTPS based on the HTTP status codes 301 or 302.
-   The HSTS response header applies to the responses to HTTPS requests, but does not apply to the responses to HTTP requests.
-   HSTS applies to port 443 rather than other ports.
-   HSTS applies to domain names rather than IP addresses.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **HTTPS**.

5.  In the **HSTS** section, click **Modify**.

6.  In the **Configure HSTS** dialog box, turn on **HSTS**.

7.  Set **Expire In** and **Include Subdomains**.

    **Note:**

    -   **Expire In** specifies the period in which the HSTS response header is cached on the browser. You can specify a value between 0 and 730. We recommend that you set the value to 60.
    -   Before you turn on **Include Subdomains**, make sure that HTTPS has been enabled for all subdomains. Otherwise, you may fail to access the HTTPS pages to which the subdomains are automatically redirected.
    ![HSTS settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9946219951/p47911.png)

8.  Click **OK**.


