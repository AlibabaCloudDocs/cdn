---
keyword: [blacklist and whitelist, User-Agent]
---

# Configure a User-Agent blacklist or whitelist

Alibaba Cloud Content Delivery Network \(CDN\) allows you to configure a User-Agent blacklist or whitelist to identity and filter requests. This can restrict access to CDN resources and improve service security. This topic describes how to configure a User-Agent blacklist or whitelist.

If you need to implement access control based on the User-Agent field, you can configure a User-Agent blacklist or whitelist to filter requests.

-   User-Agent blacklist: Requests that contain User-Agent fields in the blacklist cannot access resources.

    If a User-Agent field is added to the blacklist, requests that contain the field can be sent to CDN nodes. However, CDN nodes reject these requests and return a 403 error. These requests are recorded in the CDN logs.

-   User-Agent whitelist: Only requests that contain User-Agent fields in the whitelist can access resources. Other requests cannot access resources.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Access Control**.

5.  In the left-side navigation pane, click **UserAgent Blacklist/Whitelist**.

6.  On the **UserAgent Blacklist/Whitelist** tab, click **Modify**.

7.  Select **Blacklist** or **Whitelist** based on your business requirements.

    ![Select Blacklist or Whitelist](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6626976061/p64289.png)

    |Parameter|Description|
    |---------|-----------|
    |**Type**|The following two types of list are supported:

    -   Blacklist

Requests that contain the User-Agent fields in the blacklist cannot access resources.

    -   Whitelist

Only requests that contain User-Agent fields in the whitelist can access resources. Other requests cannot access resources.

The blacklist and whitelist are mutually exclusive, and whichever configure last takes effect. |
    |**Rules**|When you specify User-Agent fields, separate multiple fields with vertical bars \(\|\). You can use asterisks \(\*\) to specify wildcard fields. Example: \*curl\*\|\*IE\*\|\*chrome\*\|\*firefox\*|

8.  Click **OK**.


