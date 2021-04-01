---
keyword: [add a domain name to be accelerated, accelerated domain name, domain name configuration, add a domain name, new domain name, domain name]
---

# Add a domain name to Alibaba Cloud CDN

If you want to use Alibaba Cloud Content Delivery Network \(CDN\) to accelerate the delivery of content on a specific website, you must add the domain name that you want to accelerate to Alibaba Cloud CDN and specify the website as the origin server. Alibaba Cloud CDN retrieves resources from origin servers and caches the resources on CDN nodes. This allows users to retrieve the resources from the nearest CDN nodes. After you add a domain name to Alibaba Cloud CDN, the system pushes the configuration of the domain name to all CDN nodes without affecting services of the domain name. To enable content delivery acceleration for the domain name, you must configure a Canonical Name \(CNAME\) record for the domain name.

Alibaba Cloud CDN is activated. For more information, see [Activate Alibaba Cloud CDN](/intl.en-US/Quick Start/Activate Alibaba Cloud CDN.md).

## Procedure

**Note:** Beginning February 13, 2020, Alibaba Cloud CDN no longer supports the Live Streaming option when you set the Business Type parameter. If you want to accelerate live streaming content for a domain name, log on to the [ApsaraVideo Live console](https://live.console.aliyun.com/?spm=5176.2020520107.1001.38.719a8383swVAvA#/live/domains) to add and configure the domain name. For more information, see [Add a domain name](/intl.en-US/Console Guide/Domain Names/Add a domain name/Add a domain name.md).

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, click **Add Domain Name**.

4.  On the **Add Domain Name** page, set the parameters for the domain name that you want to add.

    ![intl](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7321435161/p94747.png)

    |Parameter|Description|
    |---------|-----------|
    |**Domain Name to Accelerate**|Enter the domain name that you want to add, such as `example.com`. Take note of the following limits:

    -   You can specify a domain name or a wildcard domain name. The domain name must be in lowercase letters, such as `cdntest.example.com`. Chinese characters are not supported.
    -   You can specify a wildcard domain name, such as `*.example.com`. For more information about the rules for adding wildcard domain names, see [Rules for adding wildcard domain names]().

**Note:**

        -   The specified wildcard domain names and the domain names that match the wildcard domain names must belong to the same Alibaba Cloud account. When you add a domain name to Alibaba Cloud CDN, Alibaba Cloud CDN verifies the ownership of the domain name. If the specified wildcard domain name and the domain names that match the wildcard domain name belong to different Alibaba Cloud accounts, an error message appears. To request technical support from Alibaba Cloud, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
        -   If a wildcard domain has never been added to Alibaba Cloud CDN, you can add domain names that match the wildcard domain name to Alibaba Cloud CDN by using different Alibaba Cloud accounts.
    -   You cannot add a duplicate domain name to Alibaba Cloud CDN.

If a **DomainAlreadyExist** error occurs, check whether the domain name is already added to other Alibaba Cloud services such as ApsaraVideo VOD, ApsaraVideo Live, Dynamic Route for CDN \(DCDN\), Secure CDN \(SCDN\), and Video Surveillance. You can also [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to report this issue.

    -   You can add at most 50 domain names to Alibaba Cloud CDN for each Alibaba Cloud account.

If the average daily peak bandwidth of your domain names exceeds 50 Mbit/s, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to increase the maximum number of domain names that can be added to Alibaba Cloud CDN. Make sure that the increase of domain names does not cause business risks.

    -   The content delivered from the domain name must be legal and comply with the Terms of Service for Alibaba Cloud CDN. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md). |
    |**Business Type**|    -   [Image and small file distribution](/intl.en-US/Product Introduction/Scenarios/Image and small file distribution.md): accelerates the delivery of small-sized static content on websites, such as e-commerce content and game images.
    -   [Delivery of large files](/intl.en-US/Product Introduction/Scenarios/Delivery of large files.md): accelerates the delivery of static files that are larger than 20 MB.
    -   [ApsaraVideo for VOD](/intl.en-US/Product Introduction/Scenarios/ApsaraVideo for VOD.md): accelerates the delivery of audio or video content.
    -   [DCDN](/intl.en-US/Product Introduction/Scenarios/DCDN.md): accelerates the delivery of both static and dynamic content. DCDN can accelerate the delivery of large amounts of dynamic content.

If you set Business Type to **DCDN**, you must follow the instructions to go to the DCDN console to add and configure the domain name. For more information, see [Add a domain name](). |
    |**Origin Info**|Specify the information about the origin server. If the requested resources are not cached on CDN nodes, the requests are redirected to the origin server to retrieve the resources.     -   **OSS Domain**

If your resources are stored in an Object Storage Bucket \(OSS\) bucket, you can enter the public endpoint of the OSS bucket, for example, xxx.oss-cn-hangzhou.aliyuncs.com. Internal endpoints of OSS buckets are not supported. You can view the public endpoint of an OSS bucket in the [OSS console](https://oss.console.aliyun.com/). You can also select an OSS bucket that belongs to the current Alibaba Cloud account.

    -   **IP**

Enter the public IP addresses of one or more servers. Public IP addresses of Alibaba Cloud Elastic Compute Service \(ECS\) instances do not need to be reviewed.

    -   **Site Domain**

Enter the domain names of one or more origin servers.

**Note:** The domain name of the origin server cannot be the same as the domain name to be accelerated. Otherwise, a DNS resolution loop occurs and requests cannot be redirected to the origin server.

    -   **Function Compute Domain**

Enter a Function Compute domain name. You must set the **Region** and **Domain Name** parameters for the Function Compute domain name. For more information, see [Overview](). |
    |**Port**|Select a port based on the specified origin server.     -   **Port 80**: Requests are redirected to the origin server through port 80.
    -   **Port 443**: Requests are redirected to the origin server through port 443. Make sure that the origin server supports HTTPS. |
    |**Region**|Select the accelerated region. If you select **Mainland China Only** or **Global**, you must apply for an Internet Content Provider \(ICP\) number for the domain name. We recommend that you use [Alibaba Cloud ICP Filing System](https://beian.aliyun.com/pcContainer/myorder) to apply for ICP numbers. It may take some time to update data in the database of Ministry of Industry and Information Technology \(MIIT\). After you submit domain name information to MIIT, we recommend that you wait 8 hours before you configure the domain name in Alibaba Cloud CDN. **Note:** The pricing strategies vary based on the accelerated region. Choose an accelerated region based on your business requirements. For more information about the pricing of Alibaba Cloud CDN, see [CDN Pricing](https://www.alibabacloud.com/product/cdn/pricing).

    -   **Mainland China Only**: All requests are redirected to CDN nodes that are deployed in mainland China.
    -   **Global**: All requests are redirected to the nearest CDN nodes.
    -   **Global \(Excluding Mainland China\)**: All requests are redirected to CDN nodes that are deployed outside mainland China. |

5.  Click **Next**.

    If this is the first time the domain name is added to Alibaba Cloud CDN, Alibaba Cloud CDN must verify the ownership of the domain name. If the domain name has already passed the verification, skip this step. For more information, see [Verify the ownership of a domain name]().

6.  Wait for manual verification.

    It takes one to two business days to verify the ownership of a domain name. If the origin server is an ECS instance or an OSS bucket, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex). It takes less time to verify the ownership of an ECS instance or an OSS bucket.

    After the domain name passes the verification, you can check the status of the domain name on the **Domain Names** page. If the domain name is in the **Enabled** state, it indicates that the domain name is added to Alibaba Cloud CDN.


## What to do next

[Configure a cache expiration rule](/intl.en-US/Quick Start/Configure a cache expiration rule.md)

## Related API operations

-   [AddCdnDomain](/intl.en-US/New API Reference/Domain name management/AddCdnDomain.md): Adds one domain name to Alibaba Cloud CDN at a time.
-   [BatchAddCdnDomain](/intl.en-US/New API Reference/Domain name management/BatchAddCdnDomain.md): Adds multiple domain names to Alibaba Cloud CDN at a time.

