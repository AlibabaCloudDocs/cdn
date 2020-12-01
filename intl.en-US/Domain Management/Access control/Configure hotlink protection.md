---
keyword: [Hotlink protection, CDN]
---

# Configure hotlink protection

Alibaba Cloud Content Delivery Network \(CDN\) provides the hotlink protection feature. This feature allows you to configure a referer whitelist or blacklist to identify and filter requests. This way, you can restrict access to CDN nodes and improve service security. This topic describes how to configure hotlink protection.

-   Hotlink protection uses the referer header field to trace request sources and filter requests.
-   Hotlink protection provides a referer whitelist and a referer blacklist. After a user sends a request to a CDN node, the node authenticates the user identity based on the referer whitelist or blacklist. If the request passes the authentication, it is allowed to access the requested resources. If the request fails the authentication, the CDN node returns a 403 HTTP status code to the request.

**Note:**

-   Hotlink protection is optional. It is disabled by default.
-   The blacklist and whitelist are mutually exclusive, and whichever configured last takes effect.
-   When a domain name is added to the whitelist or blacklist, a wildcard \(\*\) is automatically prepended to the domain name. For example, if you enter `a.com`, the domain name that takes effect is `*.a.com`. Hotlink protection takes effect on all domain names that match \*.a.com.
-   You can specify whether to allow requests with an empty referer header to access CDN resources. If you select Allow resource URL access from browsers, users can directly access CDN resources by entering the URL into the address bar of a browser.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Access Control**.

5.  In the **Hotlink Protection** section, click **Modify**.

6.  Select **Blacklist** or **Whitelist** based on your business requirements.

    |Parameter|Description|
    |---------|-----------|
    |**Type**|The following types are supported:

    -   Blacklist

Requests sent from domain names in the blacklist are blocked.

    -   Whitelist

Only requests sent from domain names in the whitelist are allowed to access resources.

The blacklist and whitelist are mutually exclusive, and whichever configured last takes effect. |
    |**Rules**|Separate multiple domain names with carriage return characters. You can use asterisks \(\*\) to specify wildcard referer header fields. For example, if you specify `a.*b.com`, `a.aliyun.b.com` and `a.img.b.com` match the wildcard domain name.|

7.  Click **OK**.


