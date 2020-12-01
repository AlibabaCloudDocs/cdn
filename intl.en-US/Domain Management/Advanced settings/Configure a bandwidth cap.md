---
keyword: [Alibaba Cloud CDN bandwidth, bandwidth cap]
---

# Configure a bandwidth cap

A bandwidth cap specifies the maximum bandwidth value for a domain name. When the average bandwidth value measured during each statistical cycle \(five minutes\) exceeds the maximum bandwidth value set for a domain name, the domain name is automatically disabled due to security reasons. All requests are redirected to the origin server, and Alibaba Cloud Content Delivery Network \(CDN\) suspends acceleration services in case unexpected fees are incurred. If your domain name is disabled, you can enable it in the Alibaba Cloud CDN console. This topic describes how to set a bandwidth cap and the usage notes.

When you set a bandwidth cap, take note of the following items:

-   If you want to set a bandwidth cap as a Resource Access Management \(RAM\) user, you must log on to the [RAM console](https://ram.console.aliyun.com/permissions) to create the AliyunCDNFullAccess policy. This policy grants the RAM user permissions to manage Alibaba Cloud CDN.
-   You cannot set a bandwidth cap for a wildcard domain name. If you set a bandwidth cap for a wildcard domain name, the bandwidth cap does not take effect.
-   After you set a bandwidth cap for a domain name, the domain name is disabled if the average bandwidth value measured during a statistical cycle exceeds the bandwidth cap. We recommend that you set an appropriate bandwidth cap for your domain name to ensure service availability. Proceed with caution.
-   If a domain name is disabled because the specified bandwidth cap is reached, you can log on to the Alibaba Cloud CDN console, navigate to the Domain Names page, click the domain name that you want to manage, and then click **Enable** in the Actions column to enable the domain name.
-   After a domain name is disabled, it will not be disabled again within the following hour.
-   The monitoring data of bandwidth values may not be up-to-date. After the bandwidth cap set for a domain name is reached, the domain name is disabled within the following 15 minutes.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Advanced**.

5.  In the **Bandwidth Cap** section, click **Modify**.

6.  Turn on the **Bandwidth Cap** switch and specify a bandwidth cap.

    **Note:**

    -   The convention between each two neighboring data units is 1,000. For example, 1 Tbit/s is equal to 1,000 Gbit/s, and 1 Gbit/s is equal to 1,000 Mbit/s.
    -   You can choose to enable or disable this feature based on your business requirements.
7.  Click the **OK**.


