# Force Redirect {#concept_tyh_4rl_xdb .concept}

## Introduction {#section_sms_prl_xdb .section}

When **HTTPS Secure Acceleration** is enabled for a CDN domain, it supports custom settings to perform force redirects on users' original request methods.

For example, when **force HTTPS** redirect is enabled and a user initiates an HTTP request, the server returns a 301 redirect response and the original HTTP request is forcibly redirected to an HTTPS request, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5136/15595712393707_en-US.png)

**Force Redirect** is disabled by default. When you enable the feature, both HTTP and HTTPS requests are enabled simultaneously by default.

Options: **Default**, **Force HTTPS redirect**, and **Force HTTP Redirect**.

-   **Force HTTPS redirect**: User requests are forcibly redirected to HTTPS requests.
-   **Force HTTP redirect**: User requests are forcibly redirected to HTTP requests.

## Procedure {#section_upx_5rl_xdb .section}

1.  Go to Domain Namespage, select the domain name, then click **Manage**.
2.  Enable the function in **HTTPS Configuration** \> **Forcible redirect**.

