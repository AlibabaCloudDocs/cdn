---
keyword: [add a domain name to be accelerated, accelerated domain name, domain name configuration, add a domain name, new domain name, domain name]
---

# Add a domain name to Alibaba Cloud CDN

If you want to use Alibaba Cloud Content Delivery Network \(CDN\) to accelerate the delivery of content on a specified website, specify the website as the origin server. Then, add the domain name that you want to accelerate to Alibaba Cloud CDN. Alibaba Cloud CDN retrieves resources from the origin server and caches them on CDN nodes. This allows users to retrieve the resources from the nearest CDN nodes. After you add the domain name to Alibaba Cloud CDN, the system pushes the configuration of the domain name to all CDN nodes without affecting the services of the domain name.

-   Alibaba Cloud CDN is activated. For more information about how to activate Alibaba Cloud CDN, see [Activate Alibaba Cloud CDN](/intl.en-US/Quick Start/Activate Alibaba Cloud CDN.md).
-   An origin server with stable performance is deployed.
-   A domain name to be accelerated is prepared. If the accelerated region is **Mainland China Only** or **Global**, you must apply for an Internet Content Provider \(ICP\) number for the domain name. If the domain name does not have an ICP number, you can apply for one through [Alibaba Cloud ICP Filing System](https://beian.aliyun.com/pcContainer/myorder).

## Procedure

**Note:** Beginning February 13, 2020, Alibaba Cloud CDN no longer supports the Live Streaming option when you set the Business Type parameter. If you want to accelerate live streaming content for a domain name, log on to the [ApsaraVideo Live console](https://live.console.aliyun.com/?spm=5176.2020520107.1001.38.719a8383swVAvA#/live/domains) to add and configure the domain name. For more information, see [Add a domain name](/intl.en-US/Console Guide/Domain Names/Add a domain name/Add a domain name.md).

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, click **Add Domain Name**.

4.  On the **Add Domain Name** page, set the following parameters.

    **Step 1: Set the basic information about the origin server**

    ![intl](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0595542261/p94747.png)

    |Parameter|Description|
    |---------|-----------|
    |**Domain Name to Accelerate**|Take note of the following rules:

    -   The domain name to be accelerated can be a subdomain name or a wildcard domain name. The domain name must be in lowercase letters. Chinese characters are not supported.

If the domain name is `example.com`, the domain name to be accelerated can be a subdomain name of `example.com`, for example, `cdntest.example.com`.

    -   You can specify a wildcard domain name, such as `*.example.com`. For more information about the rules for adding wildcard domain names, see [Rules for adding wildcard domain names]().

**Note:**

        -   The specified wildcard domain name and the domain names that match the wildcard domain name must belong to the same Alibaba Cloud account. When you add a domain name to Alibaba Cloud CDN, Alibaba Cloud CDN verifies the ownership of the domain name. If the specified wildcard domain name and the domain names that match the wildcard domain name belong to different Alibaba Cloud accounts, an error message appears. To request technical support from Alibaba Cloud, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
        -   If a wildcard domain name is not added to Alibaba Cloud CDN, you can add domain names that match the wildcard domain name to Alibaba Cloud CDN by using different Alibaba Cloud accounts.
    -   You cannot add a duplicate domain name to Alibaba Cloud CDN.

If a **DomainAlreadyExist** error occurs, check whether the domain name is already added to other Alibaba Cloud services such as ApsaraVideo VOD, ApsaraVideo Live, Dynamic Route for CDN \(DCDN\), Secure CDN \(SCDN\), and Video Surveillance. You can also [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to report this issue.

    -   You can add at most 50 domain names to Alibaba Cloud CDN with each Alibaba Cloud account.

However, if the sum of the average daily peak bandwidth values of your domain names exceeds 50 Mbit/s, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to add more domain names to Alibaba Cloud CDN. Make sure that the increase of domain names does not cause business risks.

    -   The content delivered from the domain name must be legal and comply with the Terms of Service for Alibaba Cloud CDN. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md). |
    |**Business Type**|    -   [Image and small file distribution](/intl.en-US/Product Introduction/Scenarios.md): accelerates the delivery of small-sized static content on websites, such as e-commerce content and game images.
    -   [Large file distribution](/intl.en-US/Product Introduction/Scenarios.md): accelerates the delivery of static files that are larger than 20 MB.
    -   [On-demand audio and video streaming](/intl.en-US/Product Introduction/Scenarios.md): accelerates the delivery of audio or video content.
    -   [What is Dynamic Route for CDN?](): accelerates the delivery of both static and dynamic content. DCDN can accelerate the delivery of large amounts of dynamic content.

If you set Business Type to **DCDN**, you must follow the instructions to go to the DCDN console to add and configure the domain name. For more information, see [Add a domain name](). |
    |**Region**|Select an accelerated region. If you select **Mainland China Only** or **Global**, you must apply for an ICP number for the domain name. We recommend that you use [Alibaba Cloud ICP Filing System](https://beian.aliyun.com/pcContainer/myorder) to apply for ICP numbers. It may take some time for Ministry of Industry and Information Technology \(MIIT\) to update data in the database. After you submit domain name information to MIIT, we recommend that you wait 8 hours before you configure the domain name in Alibaba Cloud CDN.

**Note:** The pricing strategies vary based on the accelerated region. Choose an accelerated region based on your business requirements. For more information about the pricing of Alibaba Cloud CDN, see [CDN Pricing](https://www.alibabacloud.com/product/cdn/pricing).

    -   **Mainland China Only**: All requests are redirected to CDN nodes that are deployed in mainland China.
    -   **Global**: All requests are redirected to the nearest CDN nodes.
    -   **Global \(Excluding Mainland China\)**: All requests are redirected to CDN nodes that are deployed outside mainland China. |

    **Step 2: Configure an origin server**

    1.  On the **Add Domain Name** page, click **Add Origin Server**.

    2.  In the **Add Origin Server** dialog box, set the following parameters.

        ![Configure an origin server](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8331223261/p278368.png)

        |Parameter|Description|
        |---------|-----------|
        |**Origin Info**|Enter the information about the origin server. If the requested resources are not cached on CDN nodes, requests are redirected to the origin server to retrieve the resources. You can add at most 20 origin servers.         -   **OSS Domain**

If your resources are stored in an Object Storage Bucket \(OSS\) bucket, you can enter the public endpoint of the OSS bucket, for example, xxx.oss-cn-hangzhou.aliyuncs.com. Internal endpoints of OSS buckets are not supported. You can view the public endpoint of an OSS bucket in the [OSS console](https://oss.console.aliyun.com/). You can also select an OSS bucket that belongs to the current Alibaba Cloud account from the Domain Name drop-down list.

        -   **IP**

Enter the public IP addresses of one or more servers. Public IP addresses of Alibaba Cloud Elastic Compute Service \(ECS\) instances do not need to be reviewed.

        -   **Site Domain**

Enter the domain names of one or more origin servers.

**Note:** The domain name of the origin server cannot be the same as the domain name to be accelerated. Otherwise, a DNS resolution loop occurs and requests cannot be redirected to the origin server.

        -   **Function Compute Domain**

Enter a Function Compute domain name that belongs to the current Alibaba Cloud account. You must set the **Region** and **Domain Name** parameters for the Function Compute domain name. For more information, see [Overview](). |
        |**Priority**|You can set priorities to specify primary and secondary origin servers. The primary origin server has a higher priority than the secondary origin server. Alibaba Cloud CDN redirects requests to the primary origin server.

For example, you have specified two origin servers: Server A and Server B. Server A is the primary origin server and Server B is the secondary origin server. In this case, Alibaba Cloud CDN redirects requests to Server A. If an error occurs on Server A, Alibaba Cloud CDN redirects requests to Server B until Server A works as expected again. |
        |**Weight**|If origin servers have the same priority, Alibaba Cloud CDN redirects requests to the origin servers based on their weights. This balances loads among the origin servers. Valid values are 1 to 100. A greater value indicates a heavier weight. An origin server with a heavier weight receives a larger number of requests.

For example, you have specified two origin servers: Server A and Server B, and both of them are primary origin servers. The weight of Server A is 80, and the weight of Server B is 20. In this case, Alibaba Cloud CDN redirects 80% requests to Server A and 20% requests to Server B. |
        |**Port**|Specify a port based on the settings of your origin servers. Valid values are 1 to 65535. Custom ports support only HTTP. If you want requests to be redirected to a custom port over HTTPS, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

        -   If you specify a custom port, disable the origin protocol policy. Otherwise, the specified port cannot take effect. For more information, see [Configure the origin protocol policy](/intl.en-US/Domain Management/Back-to-origin settings/Configure the origin protocol policy.md).
        -   If the origin server is an OSS bucket, OSS determines whether you can specify a custom port. |

    3.  Click **OK**.

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

