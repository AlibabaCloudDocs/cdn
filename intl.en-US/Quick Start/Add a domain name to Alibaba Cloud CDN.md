---
keyword: [add a domain name, accelerated domain name, domain name]
---

# Add a domain name to Alibaba Cloud CDN

If you want to use Alibaba Cloud Content Delivery Network \(CDN\) to accelerate the delivery of content on a specific website, you must add the domain name that you want to accelerate to Alibaba Cloud CDN and specify the website as the origin server. Alibaba Cloud CDN caches content from the origin server to Alibaba Cloud CDN nodes to accelerate content delivery. This topic describes how to add a domain name to Alibaba Cloud CDN.

**Note:** If you need to accelerate live streaming content for a domain name, log on to the [ApsaraVideo Live](https://livenext.console.aliyun.com) console to add and configure the domain name.

Beginning February 13, 2020, Alibaba Cloud CDN no longer supports the **Live Streaming** option when you set the **Business Type** parameter.

1.  Log on to the[Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, click **Add Domain Name**.

4.  Set the **Domain Name to Accelerate**,**Business Type**, **Origin Info**, **Port**, and **Region** parameters.

    ![intl](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8457192061/p94747.png)

    The following table lists the parameters that you must set on the **Add Domain Name** page.

    |Parameter|Value|Description|
    |---------|-----|-----------|
    |**Domain Name to Accelerate**|-|Enter the domain name that you want to accelerate, for example, `example.com`. Note that:

    -   You can use a subdomain name or a wildcard domain name as the accelerated domain name, for example, `cdntest.example.com`.
    -   Wildcard domain names are supported and Chinese domain names are not supported. Enter wildcard domain names in the specified format, such as `*.example.com`.
    -   You cannot add duplicate domain names to Alibaba Cloud CDN. If the system prompts that **the domain name already exists**, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
    -   You can add a maximum of 50 domain names to Alibaba Cloud CDN with each Alibaba Cloud account. To increase the upper limit, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).
    -   Content that is delivered from the domain name must comply with the limits of Alibaba Cloud CDN. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md).
**Note:** The specified wildcard domain names and the subdomain names must be under the same Alibaba Cloud account. When you add a domain name to Alibaba Cloud CDN, Alibaba Cloud CDN verifies the ownership of the domain name. If the specified wildcard domain name and the subdomain name belong to different accounts, an error message appears. To request technical support from Alibaba Cloud, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex). |
    |**Business Type**|[Image and Small File](/intl.en-US/Product Introduction/Scenarios/Image and small file distribution.md)|If you want to accelerate the delivery of small-sized static content on your website, such as small files, images, and style sheets, we recommend that you select **Image and Small File** from the Business Type drop-down list.|
    |[Downloads of large files](/intl.en-US/Product Introduction/Scenarios/Downloads of large files.md)|If you want to accelerate the delivery of static files larger than 20 MB, such as game installation packages, application updates, mobile ROM upgrades, and application packages, we recommend that you select **Large File Download** from the Business Type drop-down list.|
    |[VOD](/intl.en-US/Product Introduction/Scenarios/ApsaraVideo for VOD.md)|If you want to accelerate the delivery of on-demand video or audio content, we recommend that you select **VOD** from the Business Type drop-down list.|
    |[DCDN](/intl.en-US/Product Introduction/Scenarios/DCDN.md)|If your website or application contains large amounts of dynamic content, you can select DCDN from the Workload Type drop-down list. After simple configurations, Dynamic Route for CDN \(DCDN\) can accelerate the delivery of dynamic and static content separately. Static content is cached on CDN nodes and dynamic content is retrieved from the origin server based on the optimal link algorithm and protocol layer optimization of Alibaba Cloud. After you select **DCDN**, you are prompted to go to the Dynamic Route for CDN console. You can then create and configure the domain name. For more information, see [Add a domain](). |
    |**Origin Info**|**IP**|You can specify the public IP addresses of one or more servers. IP addresses of Alibaba Cloud Elastic Compute Service \(ECS\) instances are exempt from manual review.|
    |**Site Domain**|You can specify the domain names of one or more origin servers. **Note:** The domain name of the origin server that you specified cannot be the same as the accelerated domain name. Otherwise, a DNS resolution loop occurs and the requests cannot be redirected to the origin server correctly. For example, if the domain name of your origin server is img.yourdomain.com, you can set the accelerated domain name to cdn.yourdomain.com. |
    |**OSS Domain**|You can enter the public endpoint of an Alibaba Cloud Object Storage Service \(OSS\) bucket, for example, xxx.oss-cn-hangzhou.aliyuncs.com. To view the public endpoint of an OSS bucket, go to the OSS console. You can also select an OSS bucket under the current account.|
    |**Function Compute Domain**|To use a Function Compute domain name, you must set the Region and Domain Name parameters. For more information, see [Set a Function Compute domain name](https://www.alibabacloud.com/help/doc-detail/90759.htm).|
    |**Port**|-|Select a port based on your business requirements.

    -   Port 80

Allows users to access resources over HTTP.

    -   Port 443

Allows users to access resources over HTTPS. |
    |**Region**|**Global \(Excluding Mainland China\)**|If you select **Global \(Excluding Mainland China\)**, you do not need to apply for an Internet Content Provider \(ICP\) number from Ministry of Industry and Information Technology \(MIIT\) for the accelerated domain name.|
    |**Global**|If you select **Global**, you must apply for an ICP number from MIIT for the accelerated domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|
    |**Mainland China Only**|If you select **Mainland China Only**, you must apply for an ICP number from MIIT for the accelerated domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|

5.  Click **Next**.

    ![Add the domain name to Alibaba Cloud CDN](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8457192061/p62084.png)

    After the domain name passes ownership verification, it is listed on the **Domain Names** page. If the status of the domain name is **Enabled**, it indicates that the domain name has been added to Alibaba Cloud CDN.

    **Note:**

    -   If you require urgent verification on your domain name, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).
    -   If the origin server is an ECS instance or an OSS bucket, it takes less time to verify the ownership of the domain name.
    -   After a domain name is added to Alibaba Cloud CDN, Alibaba Cloud CDN assigns a Canonical Name \(CNAME\) to the domain name. The Alibaba Cloud CDN service takes effect only after you add the CNAME record for the domain name.

## API operations

You can call API operations listed in the following table to manage domain names.

|API|Description|
|---|-----------|
|[AddCdnDomain](/intl.en-US/New API Reference/Domain management operations/AddCdnDomain.md)|Adds a domain name to Alibaba Cloud CDN.|
|[DeleteCdnDomain](/intl.en-US/New API Reference/Domain management operations/DeleteCdnDomain.md)|Removes a domain name from Alibaba Cloud CDN.|
|[StopCdnDomain](/intl.en-US/New API Reference/Domain management operations/StopCdnDomain.md)|Disables a domain name that is accelerated by Alibaba Cloud CDN. After the domain name is disabled, the value of the DomainStatus parameter is changed to Offline.|
|[StartCdnDomain](/intl.en-US/New API Reference/Domain management operations/StartCdnDomain.md)|Enables a disabled domain name. After the domain name is enabled, the value of the DomainStatus parameter is changed to Online.|
|[BatchStartCdnDomain](/intl.en-US/New API Reference/Domain management operations/BatchStartCdnDomain.md)|Enables one or more domain names at a time. After a domain name is enabled, the value of the DomainStatus parameter is changed to Online.|
|[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain management operations/BatchSetCdnDomainConfig.md)|Configures multiple accelerated domain names at a time.|
|[ModifyCdnDomain](/intl.en-US/New API Reference/Domain management operations/ModifyCdnDomain.md)|Modifies the information about an accelerated domain name.|
|[DescribeUserDomains](/intl.en-US/New API Reference/Domain management operations/DescribeUserDomains.md)|Queries all domain names accelerated by Alibaba Cloud CDN under your account and the status of the accelerated domain names. You can filter domain names by name or status. Fuzzy match is supported.|
|[DescribeCdnDomainDetail](/intl.en-US/New API Reference/Domain management operations/DescribeCdnDomainDetail.md)|Queries the basic information about an accelerated domain name.|
|[DescribeDomainsBySource](/intl.en-US/New API Reference/Domain management operations/DescribeDomainsBySource.md)|Queries the domain names corresponding to origin servers under your account.|
|[BatchStopCdnDomain](/intl.en-US/New API Reference/Domain management operations/BatchStopCdnDomain.md)|Disables one or more accelerated domain names at a time. After an accelerated domain name is disabled, the value of the DomainStatus parameter is changed to Offline.|
|[DescribeCdnDomainConfigs](/intl.en-US/New API Reference/Domain management operations/DescribeCdnDomainConfigs.md)|Queries the configurations of an accelerated domain name. You can query the configuration of one or more features at a time.|
|[DeleteSpecificConfig](/intl.en-US/New API Reference/Domain management operations/DeleteSpecificConfig.md)|Deletes specific configurations of an accelerated domain name.|
|[DescribeUserVipsByDomain](/intl.en-US/New API Reference/Domain management operations/DescribeUserVipsByDomain.md)|Queries virtual IP addresses of CDN nodes by domain name.|
|[BatchAddCdnDomain](/intl.en-US/New API Reference/Domain management operations/BatchAddCdnDomain.md)|Adds multiple domain names to Alibaba Cloud CDN at a time. You can add a maximum of 20 domain names to Alibaba Cloud CDN with each account.|
|[ModifyCdnDomainSchdmByProperty](/intl.en-US/New API Reference/Domain management operations/ModifyCdnDomainSchdmByProperty.md)|Modifies the accelerated region for an accelerated domain name.|
|[BatchUpdateCdnDomain](/intl.en-US/New API Reference/Domain management operations/BatchUpdateCdnDomain.md)|Updates the configurations of multiple accelerated domain names at a time.|
|[SetWaitingRoomConfig](/intl.en-US/New API Reference/Domain management operations/SetWaitingRoomConfig.md)|Configures the virtual waiting room feature for an accelerated domain name. This operation is available only for accelerated domain names of the DCDN workload type.|

**Note:** You can query the virtual IP addresses of CDN nodes by domain name only by calling API operations. For more information, see [DescribeUserVipsByDomain](/intl.en-US/New API Reference/Domain management operations/DescribeUserVipsByDomain.md).

