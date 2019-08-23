# Configure an IP address blacklist or whitelist {#task_187634 .task}

You can configure an IP address blacklist or whitelist to identify and filter users, restricting access to CDN resources and improving CDN security. This topic describes how to configure an IP address blacklist or whitelist.

-   IP address blacklist: Blacklisted IP addresses are not allowed to access CDN resources.

    If your IP address is blacklisted, requests from your IP address can be sent to a CDN node. However, the CDN node will reject the requests and return a 403 error. The requests from blacklisted IP addresses are recorded in CDN logs.

-   IP address whitelist: Only whitelisted IP addresses are allowed to access CDN resources.

**Note:** 

-   Both IP address blacklists and whitelists support IPv6 addresses.
-   Both IP address blacklists and whitelists support CIDR block notations. For example, in the CIDR block 192.168.0.0/24, /24 indicates that the first 24 bits are network bits. The remaining 8 bits are host bits. The subnet can accommodate 254 hosts. 192.168.0.0/24 indicates that IP addresses range from 192.168.0.1 to 192.168.0.254.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Access Control**.
5.  Click IP Blacklist/Whitelist.
6.  On the IP Blacklist/Whitelist, click **Modify**. 

    ![Rules](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5153/15665335707283_en-US.png)

7.  Configure **Blacklist** or **Whitelist** as prompted. 

    |Parameter|Description|
    |---------|-----------|
    |Type| The following two types of IP address lists are supported:

    -   Blacklist

The blacklisted IP addresses are not allowed to access CDN resources.

    -   Whitelist

Only the whitelisted IP addresses are allowed to access CDN resources.

 The blacklist and whitelist are mutually exclusive. Only either of them can take effect at any time.

 |
    |Rules|You can configure a maximum of 100 IP addresses or CIDR blocks and separate them with carriage return characters. Each CIDR block must be unique. For example, if the IP address 192.168.0.1/24 is already configured, it cannot be configured again.|

8.  Click **OK**.

