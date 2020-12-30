---
keyword: [add a domain name to be accelerated, accelerated domain name, domain name configuration, add a domain name, new domain name, domain name]
---

# Add a domain name to Alibaba Cloud CDN

If you want to use Alibaba Cloud Content Delivery Network \(CDN\) to accelerate the delivery of content on a specific website, you must add the domain name that you want to accelerate to Alibaba Cloud CDN and specify the website as an origin server. Alibaba Cloud CDN caches content from origin servers to Alibaba Cloud CDN nodes to accelerate content delivery. This topic describes how to add a domain name to Alibaba Cloud CDN.

**Note:**

-   If you have not set a cache expiration time on your origin server or CDN nodes, the CDN nodes use the default time-to-live \(TTL\) value of 3,600 seconds to expire cached resources. After you add a domain name to Alibaba Cloud CDN, you can modify the TTL value. The amount of back-to-origin network traffic and fees vary based on the TTL value. We recommend that you set a TTL value based on your business requirements. A small TTL value may cause CDN nodes to frequently redirect requests to the origin server and increase the amount of network traffic that is consumed by the origin server. For more information, see [Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md).
-   Beginning from February 13, 2020, Alibaba Cloud CDN no longer supports the Live Streaming option when you set the Business Type parameter. If you want to accelerate live streaming content for a domain name, log on to the [ApsaraVideo Live console](https://live.console.aliyun.com/?spm=5176.2020520107.1001.38.719a8383swVAvA#/live/domains) to add and configure the domain name.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, click **Add Domain Name**.

4.  Set the following parameters: **Domain Name to Accelerate**, **Business Type**, **Origin Info**, **Port**, and **Region**.

    ![intl](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8457192061/p94747.png)

    The following table lists the parameters that you must set on the **Add Domain Name** page.

    |Parameter|Option|Description|
    |---------|------|-----------|
    |**Domain Name to Accelerate**|-|Enter the domain name that you want to accelerate, for example, `example.com`. Take note of the following rules:

    -   You can use a specific domain name or a wildcard domain name as the domain name to be accelerated, for example, `cdntest.example.com`.
    -   Wildcard domain names are supported but Chinese domain names are not supported. Enter wildcard domain names in the specified format, for example, `*.example.com`.
    -   You cannot add a duplicate domain name to Alibaba Cloud CDN. If a **DomainAlreadyExist** error occurs, check whether the domain name is already added to other Alibaba Cloud services such as ApsaraVideo VOD, ApsaraVideo Live, Dynamic Route for CDN \(DCDN\), Secure CDN \(SCDN\), and Video Surveillance. You can also [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to fix this issue.
    -   You can add a maximum of 50 domain names to Alibaba Cloud CDN by using your Alibaba Cloud account. If the average daily peak bandwidth value exceeds 50 Mbit/s and your workloads are under protection, you can [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex) to add more domain names to Alibaba Cloud CDN.
    -   Content that is delivered from the domain name must comply with the limits of Alibaba Cloud CDN. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md).
**Note:** The specified wildcard domain names and the domain names that match the wildcard domain names must belong to the same Alibaba Cloud account. When you add a domain name to Alibaba Cloud CDN, Alibaba Cloud CDN verifies the ownership of the domain name. If the specified wildcard domain name and the domain names that match the wildcard domain name belong to different Alibaba Cloud accounts, an error message is returned. To request technical support from Alibaba Cloud, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex). |
    |**Business Type**|[Image and Small File](/intl.en-US/Product Introduction/Scenarios/Image and small file distribution.md)|If you want to accelerate the delivery of small-sized static content on your website, we recommend that you select **Image and Small File** from the Business Type drop-down list. Examples of small-sized static content include small-sized files, images, and style sheets.|
    |[Delivery of large files](/intl.en-US/Product Introduction/Scenarios/Delivery of large files.md)|If you want to accelerate the delivery of static files larger than 20 MB, we recommend that you select **Large File Download** from the Business Type drop-down list. Examples of large-sized static files include game installation packages, app update packages, mobile read-only memory \(ROM\) upgrade packages, and app packages.|
    |[VOD](/intl.en-US/Product Introduction/Scenarios/ApsaraVideo for VOD.md)|If you want to accelerate the delivery of on-demand video or audio content, we recommend that you select **VOD** from the Business Type drop-down list.|
    |[DCDN](/intl.en-US/Product Introduction/Scenarios/DCDN.md)|If your website or application contains large amounts of dynamic content, you can select DCDN from the Business Type drop-down list. After simple configurations, DCDN can separately accelerate the delivery of dynamic and static content. Static content is cached on CDN nodes. Dynamic content is retrieved from the origin server based on the optimal link algorithm and protocol layer optimization of Alibaba Cloud. After you select **DCDN**, you are prompted to go to the DCDN console. You can then add and configure the domain name. For more information, see [Add a domain name](). |
    |**Origin Info**|**IP**|You can enter the public IP addresses of one or more servers. IP addresses of Alibaba Cloud Elastic Compute Service \(ECS\) instances do not need to be reviewed.|
    |**Site Domain**|You can enter the domain names of one or more origin servers. **Note:** The specified domain name of the origin server cannot be the same as the domain name to be accelerated. Otherwise, a DNS resolution loop occurs and requests cannot be redirected to the origin server. For example, if the domain name of your origin server is img.yourdomain.com, you can set the domain name to be accelerated to cdn.yourdomain.com. |
    |**OSS Domain**|You can enter the public endpoint of an Alibaba Cloud Object Storage Service \(OSS\) bucket, for example, xxx.oss-cn-hangzhou.aliyuncs.com. To view the public endpoint of an OSS bucket, go to the OSS console. You can also select the endpoint of an OSS bucket that belongs to the current Alibaba Cloud account from the Domain Name drop-down list. Internal endpoints of OSS buckets are not supported.|
    |**Function Compute Domain**|You must set the Region and Domain Name parameters for the Function Compute domain name. For more information, see [Set a Function Compute domain name](https://www.alibabacloud.com/help/doc-detail/90759.htm).|
    |**Port**|-|Select a port based on your business requirements.

    -   Port 80

Requests are redirected to the origin server through port 80.

    -   Port 443

Requests are redirected to the origin server through port 443. |
    |**Region**|**Global \(Excluding Mainland China\)**|If you select **Global \(Excluding Mainland China\)**, you do not need to apply for an Internet Content Provider \(ICP\) number for the domain name.|
    |**Global**|If you select **Global**, you must apply for an ICP number for the domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|
    |**Mainland China Only**|If you select **Mainland China Only**, you must apply for an ICP number for the domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|

5.  Click **Next**.

    ![The domain name is added](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8457192061/p62084.png)

    After your domain name passes the review, you can view the domain name on the **Domain Names** page in the Alibaba Cloud CDN console. If the status of the domain name is **Enabled**, it indicates that the domain name has been added to Alibaba Cloud CDN.

    **Note:**

    -   You can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to expedite the review.
    -   If the origin server is an ECS instance or an OSS bucket, it takes less time to verify the ownership of the domain name.
    -   After a domain name is added to Alibaba Cloud CDN, Alibaba Cloud CDN assigns a canonical name \(CNAME\) to the domain name. The Alibaba Cloud CDN service takes effect only after you add the CNAME record for the domain name.

## API operations

You can call API operations listed in the following table to manage domain names.

|API operation|Description|
|-------------|-----------|
|[AddCdnDomain](/intl.en-US/New API Reference/Domain name management/AddCdnDomain.md)|Adds a domain name to Alibaba Cloud CDN.|
|[DeleteCdnDomain](/intl.en-US/New API Reference/Domain name management/DeleteCdnDomain.md)|Removes a domain name from Alibaba Cloud CDN.|
|[StopCdnDomain](/intl.en-US/New API Reference/Domain name management/StopCdnDomain.md)|Disables a domain name that is accelerated by Alibaba Cloud CDN. After the domain name is disabled, the value of the DomainStatus parameter is changed to Offline.|
|[StartCdnDomain](/intl.en-US/New API Reference/Domain name management/StartCdnDomain.md)|Enables a disabled domain name. After the domain name is enabled, the value of the DomainStatus parameter is changed to Online.|
|[BatchStartCdnDomain](/intl.en-US/New API Reference/Domain name management/BatchStartCdnDomain.md)|Enables one or more domain names at a time. After a domain name is enabled, the value of the DomainStatus parameter is changed to Online.|
|[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)|Configures multiple accelerated domain names at a time.|
|[ModifyCdnDomain](/intl.en-US/New API Reference/Domain name management/ModifyCdnDomain.md)|Modifies the information about an accelerated domain name.|
|[DescribeUserDomains](/intl.en-US/New API Reference/Domain name management/DescribeUserDomains.md)|Queries all domain names accelerated by Alibaba Cloud CDN under your account and the status of the accelerated domain names. You can filter domain names by name or status. Fuzzy match is supported.|
|[DescribeCdnDomainDetail](/intl.en-US/New API Reference/Domain name management/DescribeCdnDomainDetail.md)|Queries the basic information about an accelerated domain name.|
|[DescribeDomainsBySource](/intl.en-US/New API Reference/Domain name management/DescribeDomainsBySource.md)|Queries the domain names corresponding to origin servers under your account.|
|[BatchStopCdnDomain](/intl.en-US/New API Reference/Domain name management/BatchStopCdnDomain.md)|Disables one or more accelerated domain names at a time. After an accelerated domain name is disabled, the value of the DomainStatus parameter is changed to Offline.|
|[DescribeCdnDomainConfigs](/intl.en-US/New API Reference/Domain name management/DescribeCdnDomainConfigs.md)|Queries the configurations of an accelerated domain name. You can query the configuration of one or more features at a time.|
|[DeleteSpecificConfig](/intl.en-US/New API Reference/Domain name management/DeleteSpecificConfig.md)|Deletes specific configurations of an accelerated domain name.|
|[DescribeUserVipsByDomain](/intl.en-US/New API Reference/Domain name management/DescribeUserVipsByDomain.md)|Queries virtual IP addresses of CDN nodes by domain name.|
|[BatchAddCdnDomain](/intl.en-US/New API Reference/Domain name management/BatchAddCdnDomain.md)|Adds multiple domain names to Alibaba Cloud CDN at a time. You can add a maximum of 20 domain names to Alibaba Cloud CDN with each account.|
|[ModifyCdnDomainSchdmByProperty](/intl.en-US/New API Reference/Domain name management/ModifyCdnDomainSchdmByProperty.md)|Modifies the accelerated region for an accelerated domain name.|
|[BatchUpdateCdnDomain](/intl.en-US/New API Reference/Domain name management/BatchUpdateCdnDomain.md)|Updates the configurations of multiple accelerated domain names at a time.|
|[SetWaitingRoomConfig](/intl.en-US/New API Reference/Domain name management/SetWaitingRoomConfig.md)|Configures the virtual waiting room feature for an accelerated domain name. This operation is available only for accelerated domain names of the DCDN workload type.|

**Note:** You can query the virtual IP addresses of CDN nodes by domain name only by calling API operations. For more information, see [DescribeUserVipsByDomain](/intl.en-US/New API Reference/Domain name management/DescribeUserVipsByDomain.md).

