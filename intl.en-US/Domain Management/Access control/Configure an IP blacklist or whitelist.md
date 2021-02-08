---
keyword: [, CDN whitelist, IP blacklist, IP whitelist]
---

# Configure an IP blacklist or whitelist

Alibaba Cloud Content Delivery Network \(CDN\) allows you to configure an IP address blacklist or whitelist to identify and filter users. This helps you control access to CDN resources and improve resource security. This topic describes how to configure an IP address blacklist or whitelist.

-   IP address blacklist: IP addresses in the blacklist are not allowed to access resources.

    If an IP address is added to the blacklist, requests from the IP address can be sent to CDN nodes. However, CDN nodes reject the requests and return a 403 error. These requests are recorded in the CDN logs.

-   IP address whitelist: Only requests from IP addresses in the whitelist can access resources. Other IP addresses are blocked.

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

    -   whitelist

Only IP addresses in the whitelist are allowed to access the current accelerated domain name. Other IP addresses are blocked.

**Note:** The blacklist and whitelist are mutually exclusive. The most recent configuration takes effect. |
    |**Rules**|You can specify at most 5,000 IP addresses or CIDR blocks and separate them with carriage return characters. Each CIDR block must be unique. For example, if the IP address 127.0.0.0/24 is already in the whitelist, it cannot be added again.|

8.  Click **OK**.


