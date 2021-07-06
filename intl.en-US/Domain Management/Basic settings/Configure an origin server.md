---
keyword: [origin domain name, CDN]
---

# Configure an origin server

This topic describes how to modify the information about an origin server in the Alibaba Cloud Content Delivery Network \(CDN\) console.

-   Alibaba Cloud CDN supports the following types of origin server: Object Storage Service \(OSS\) endpoints, IP addresses of origin servers, domain names of origin servers, and Function Compute domain names. You can specify one or more IP addresses or domain names for each origin server type and configure at most 20 origin servers. If you have configured more than one origin server, you can specify primary and secondary origin servers for failover and set the weight of each origin server for load balancing.
-   When you configure or modify an origin server, you can specify a custom port to receive requests redirected by Alibaba Cloud CDN. Alibaba Cloud CDN redirects only HTTP requests to the custom port of an origin server.
-   Alibaba Cloud CDN performs Layer 4 health checks on origin servers. Port 80, port 443, and the custom port that you have specified are all probed. Probes are sent every 2.5 seconds. If an origin server fails three consecutive health checks, the system marks the origin server as unavailable.
-   Alibaba Cloud CDN supports failover between primary and secondary origin servers. If multiple origin servers are configured, Alibaba Cloud CDN preferably redirects requests to the origin server whose **Priority** is **Primary**. If the primary origin server fails three consecutive health checks, Alibaba Cloud CDN redirects requests to the origin server whose **Priority** is **Secondary**. If the primary origin server passes the health check, the system marks the origin server as available and restores the priority of the origin server to primary. If you set all origin servers to the same priority, Alibaba Cloud CDN automatically redirects requests to the origin servers based on round-robin scheduling.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the **Origin Information** section, click **Add Origin Server**.

    ![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2206555261/p276724.png)

5.  In the **Add Origin Server** dialog box, specify the origin server information, priority, weight, and port.

    ![Origin server settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4452462061/p64107.png)

    The following table describes the parameters that you must set.

    |Parameter|Description|
    |---------|-----------|
    |Origin Info|    -   **IP**: You can specify the public IP addresses of one or more origin servers. If the origin server is an Alibaba Cloud Elastic Compute Service \(ECS\) instance, verification of the IP address is not required. For more information, see [What is ECS?](/intl.en-US/Product Introduction/What is ECS?.md)
    -   **Site Domain**: You can specify the domain names of one or more origin servers.

**Note:** The specified domain name of the origin server cannot be the same as the domain name to be accelerated. Otherwise, a DNS resolution loop occurs and requests cannot be redirected to the origin server. For example, if the domain name of the origin server is img.yourdomain.com, you can set the domain name to be accelerated to cdn.yourdomain.com.

    -   **OSS Domain**: You can enter the public endpoint of an OSS bucket, for example, xxx.oss-cn-hangzhou.aliyuncs.com. To view the public endpoint of an OSS bucket, log on to the OSS console. You can also select the endpoint of an OSS bucket that belongs to the current Alibaba Cloud account from the Domain Name drop-down list.
    -   **Function Compute Domain**: If you specify a Function Compute domain name, you must set the Region and Domain Name parameters. You can specify only Function Compute domain names that belong to the current Alibaba Cloud account. For more information, see [Set a Function Compute domain name](https://www.alibabacloud.com/help/doc-detail/90759.htm). |
    |Priority|You can set the priority of an origin server to **Primary** or **Secondary**. **A primary origin server has a higher priority than a secondary origin server**. Alibaba Cloud CDN preferably redirects requests to a primary origin server. For example, you have configured Origin Server A and Origin Server B. Origin Server A is specified as a primary origin server and Origin Server B is specified as a secondary origin server. Alibaba Cloud CDN preferably redirects user requests to Origin Server A. When Origin Server A fails, Alibaba Cloud CDN redirects user requests to Origin Server B. After Origin Server A recovers, Alibaba Cloud CDN fails back to Origin Server A.|
    |Weight|If you have specified the same priority for multiple origin servers, Alibaba Cloud CDN redirects user requests to the origin servers based on the weights of the origin servers for load balancing. For example, both Origin Server A and Origin Server B are specified as primary origin servers. The weight of Origin Server A is 80 and the weight of Origin Server B is 20. Alibaba Cloud CDN redirects user requests to both origin servers at a ratio of 8:2. The valid values of origin server weights are **1 to 100**. An origin server with a higher weight received more user requests.|
    |Port|Alibaba Cloud CDN redirects only HTTP requests to origin servers over custom ports. If you want Alibaba Cloud CDN to redirect HTTPS requests to origin servers over custom ports, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).     -   If you specify a custom port, you must disable the origin protocol policy. Otherwise, the specified custom port does not take effect. For more information, see [Configure the origin protocol policy](/intl.en-US/Domain Management/Back-to-origin settings/Configure the origin protocol policy.md).
    -   If the origin server is an OSS bucket, OSS determines whether you can specify a custom port.
    -   The valid values of custom ports are **1 to 65535**. |

    **Note:**

    -   If you set the origin server type to **IP** or **Site Domain**, Alibaba Cloud charges an outbound data transfer \(to the Internet\) fee when Alibaba Cloud CDN retrieves resources from an OSS bucket. For more information, see [OSS pricing](https://www.alibabacloud.com/zh/product/oss/pricing).
    -   If you set the origin server type to **OSS Domain**, Alibaba Cloud charges an outbound data transfer fee \(to Alibaba Cloud CDN\) when Alibaba Cloud CDN retrieves resources from an OSS bucket. Discounts are offered on outbound data transfer to Alibaba Cloud CDN. For more information, see [OSS pricing](https://www.alibabacloud.com/zh/product/oss/pricing).
    -   If you set the origin server type to **Site Domain** and specify an OSS domain name, Alibaba Cloud charges an outbound data transfer \(to the Internet\) fee when Alibaba Cloud CDN retrieves resources from the specified OSS bucket. For more information, see [OSS pricing](https://www.alibabacloud.com/zh/product/oss/pricing).
6.  Click **OK**.


