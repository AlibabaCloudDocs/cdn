---
keyword: [, CDN whitelist, IP blacklist, IP whitelist]
---

# Configure an IP blacklist or whitelist

Alibaba Cloud Content Delivery Network \(CDN\) allows you to configure an IP blacklist or whitelist to identify and filter users. This helps you control access to CDN resources and improve resource security. This topic describes how to configure an IP blacklist or whitelist.

-   IP blacklist: IP addresses in the blacklist are not allowed to access resources.

    If an IP address is added to the blacklist, requests from the IP address can be sent to CDN nodes. However, CDN nodes reject the requests and return an HTTP 403 status code. These requests are recorded in the CDN logs.

-   IP whitelist: Only requests from IP addresses in the whitelist can access CDN resources. Other IP addresses are blocked.

**Note:**

-   IP blacklists and whitelists support IPv6 addresses. IPv6 addresses must use uppercase letters, for example, 2001:DB8:0:23:8:800:200C:417A or 2001:0DB8:0000:0023:0008:0800:200C:417A. The notation of an IPv6 address must not be shortened. For example, 2001:0DB8::0008:0800:200C:417A is invalid.
-   IP blacklists and whitelists support CIDR blocks. For example, in the CIDR block 192.168.0.0/24, /24 indicates that the first 24 bits are the network bits. The remaining 8 bits are the host bits. The subnet can accommodate 254 hosts. Therefore, 192.168.0.0/24 represents IP addresses from 192.168.0.1 to 192.168.0.254.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Access Control**.

5.  Click the **IP Blacklist/Whitelist** tab.

6.  In the **IP Blacklist/Whitelist** section, click **Modify**.

7.  Select **Blacklist** or **Whitelist** based on your business requirements.

    |Parameter|Description|
    |---------|-----------|
    |**Type**|The following types of IP list are supported:

    -   Blacklist

IP addresses in the blacklist are not allowed to access the current accelerated domain name.

    -   Whitelist

Only IP addresses in the whitelist are allowed to access the current accelerated domain name. Other IP addresses are blocked.

**Note:** Blacklists and whitelists are mutually exclusive. The most recent configuration takes effect. |
    |**Rules**|You can specify at most 5,000 IP addresses or CIDR blocks and separate them with carriage return characters. Each CIDR block must be unique. For example, if the IP address 127.0.0.0/24 is already in the whitelist, it cannot be added again. **Note:** If you want to control access from specific client IP addresses, you must add the X-Forwarded-For \(XFF\) HTTP header to the IP whitelist or blacklist. By default, the IP blacklist blocks requests based on the XFF header. For more information about how to retrieve actual IP addresses of clients, see [Retrieve actual IP addresses of clients](/intl.en-US/Website Access/Retrieve actual IP addresses of clients.md). |

8.  Click **OK**.


## Related API operations

You can call the BatchSetCdnDomainConfig operation to configure an IP blacklist or whitelist for multiple domain names at a time. The ip\_black\_list\_set parameter specifies an IP blacklist and the ip\_allow\_list\_set parameter specifies an IP whitelist. For more information, see [BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md).

