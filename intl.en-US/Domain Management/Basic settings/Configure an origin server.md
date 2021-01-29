---
keyword: [origin domain name, CDN]
---

# Configure an origin server

This topic describes how to modify the information about an origin server in the Alibaba Cloud Content Delivery Network \(CDN\) console.

**Note:** When you modify the information about an origin server, if you set **Origin Information** to **OSS Domain**, **IP**, or **Site Domain**, you can specify a custom port that redirects requests to the origin server. If you specify a custom port, Alibaba Cloud CDN redirects only HTTP requests to the origin server.

Alibaba Cloud CDN supports the following types of origin server: Object Storage Service \(OSS\) endpoints, IP addresses of origin servers, domain names of origin servers, and Function Compute domain names. If you set Origin Info to IP or Site Domain, you can specify one or more IP addresses or domain names and set a priority for each IP address or domain name.

**Note:** Layer 4 health checks are performed on origin servers. Port 80, port 443, or custom ports of origin servers are probed. Probes are sent every 2.5 seconds. If an origin server fails three consecutive probes, the system marks the origin server as unavailable.

Alibaba Cloud CDN supports failover between primary and secondary origin servers. If multiple origin servers are configured, Alibaba Cloud CDN redirects requests to the origin server whose **Priority** is **Primary**. If the primary origin server fails three consecutive probes, Alibaba Cloud CDN redirects requests to the origin server whose **Priority** is **Secondary**. If the primary origin server passes the health check, the system marks the origin server as available and restores the priority of this origin server to primary. If you set the same priority for all origin servers, Alibaba Cloud CDN automatically redirects requests to the origin servers based on the round robin scheme.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the **Origin Information** section, click **Modify**.

5.  In the **Modify Origin Information** dialog box, set the origin type, origin address, and port.

    ![Configure origin information](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4452462061/p64107.png)

    The following table lists the parameters that you must set.

    **Note:**

    -   If you set the origin type to **IP** or **Site Domain**, you are charged based on the price of Internet data transfer.
    -   If you set the origin type to **OSS Domain**, Alibaba Cloud CDN redirects requests to the specified OSS bucket and you are charged based on the price of internal data transfer. For more information, see [OSS pricing](https://www.alibabacloud.com/product/oss/pricing).
    -   If you set the origin type to **Site Domain** and specify the endpoint of an OSS bucket, you are charged based on the price of Internet data transfer.
    -   Origin type

        |Origin type|Description|
        |-----------|-----------|
        |**IP**|You can specify the public IP addresses of one or more servers. If the origin server is an Alibaba Cloud Elastic Compute Service \(ECS\) instance, review of the IP address is not required. For more information, see [What is ECS?](/intl.en-US/Product Introduction/What is ECS?.md).|
        |**Site Domain**|You can specify the domain names of one or more origin servers. **Note:** The domain name of the origin server cannot be the same as the domain name to be accelerated. Otherwise, a DNS resolution loop occurs and requests cannot be redirected to the origin server. For example, if the domain name of the origin server is img.yourdomain.com, you can set the domain name to be accelerated to cdn.yourdomain.com. |
        |**OSS Domain**|You can enter the public endpoint of an OSS bucket, for example, xxx.oss-cn-hangzhou.aliyuncs.com. To view the public endpoint of an OSS bucket, go to the OSS console. You can also select an OSS bucket that belongs to the current Alibaba Cloud account.|
        |**Function Compute Domain**|If you select this value, you must set the Region and Domain Name parameters. For more information, see [Set a Function Compute domain name](https://www.alibabacloud.com/help/doc-detail/90759.htm).|

    -   Port

        |Port|Description|
        |:---|:----------|
        |**Port 80**|Alibaba Cloud CDN retrieves resources from origin servers by using port 80 over HTTP or HTTPS.|
        |**Port 443**|Alibaba Cloud CDN retrieves resources from origin servers by using port 443 over HTTP or HTTPS. If the IP address of the origin server is associated with multiple domain names, you must configure the Server Name Indication \(SNI\) feature for the origin server. For more information, see [Configure SNI](/intl.en-US/Domain Management/Back-to-origin settings/Configure SNI.md).**Note:** If the origin server supports only HTTPS requests, specify port 443. |
        |**Custom Port**|Alibaba Cloud CDN redirects only HTTP requests to origin servers over custom ports. If you want Alibaba Cloud CDN to redirect HTTPS requests to origin servers over custom ports, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex). **Note:** If you specify a custom port, disable the origin protocol policy. Otherwise, the specified port cannot take effect. For more information, see [Configure the origin protocol policy](/intl.en-US/Domain Management/Back-to-origin settings/Configure the origin protocol policy.md).

If the origin server is an OSS bucket, OSS determines whether you can specify a custom port. |

6.  Click **OK**.


