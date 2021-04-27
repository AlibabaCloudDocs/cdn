---
keyword: [CDN accelerates OSS resources, CDN console]
---

# Use Alibaba Cloud CDN to accelerate the delivery of resources from OSS buckets \(Method 1\)

You can use Alibaba Cloud Content Delivery Network \(CDN\) to accelerate the delivery of static resources from an Object Storage Service \(OSS\) bucket. This topic describes how to enable Alibaba Cloud CDN to accelerate the delivery of resources from an OSS bucket in the OSS console and the scenarios where Alibaba Cloud CDN can be used.

## Prerequisites

-   [Alibaba Cloud account registration](https://account.alibabacloud.com/register/intl_register.htm) and [real-name verification](https://account-intl.console.aliyun.com/#/intlAuth) are completed.

-   An OSS bucket is created and associated with a custom domain name. For more information, see [Create buckets](/intl.en-US/Quick Start/OSS console/Create buckets.md) and [Map custom domain names](/intl.en-US/Console User Guide/Manage buckets/Manage a domain/Map custom domain names.md).

## Background information

Alibaba Cloud CDN works with a precise scheduling system. This system redirects requests for static resources to CDN nodes that are nearest to the clients. This mechanism enables efficient retrieval of requested resources and minimizes network congestion.

Static resources stored in an OSS bucket include static scripts, images, attachments, audio files, and video files. CDN nodes prefetch static resources from the OSS bucket. When a client requests the cached static resources, the scheduling system redirects the request to the CDN node that is nearest to the client. Then, the CDN node returns the requested resources to the client. The following figure shows how Alibaba Cloud CDN accelerates the delivery of resources from an OSS bucket.

![Diagram](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/669798/156860449150521_en-US.png)

In this case, the OSS bucket is the origin server. The delivery of content stored in the OSS bucket is accelerated by Alibaba Cloud CDN. Users retrieve files from the nearest CDN node. This architecture provides the following benefits:

-   All requests destined for the origin server are redirected to CDN nodes. This reduces loads on the origin server.
-   Compared with data transfer between clients and OSS buckets over the Internet, data transfer between clients and CDN nodes is billed at a lower price rate.
-   Clients retrieve static resources from the nearest CDN nodes. This minimizes the network transmission distance and ensures the quality of the retrieved resources.

In the following example, Alibaba Cloud DNS is used to demonstrate how to configure a Canonical Name \(CNAME\) record.

## Procedure

1.  In the Alibaba Cloud CDN console, add the domain name of the OSS bucket to Alibaba Cloud CDN.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, click **Add Domain Name**.

    4.  Set the following parameters and set Origin Info to **OSS Domain**.

        ![intl](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7321435161/p94747.png)

        |Parameter|Description|
        |---------|-----------|
        |**Domain Name to Accelerate**|Enter the domain name that you want to add, such as `example.com`. Take note of the following limits:

        -   You can specify a domain name or a wildcard domain name. The domain name must be in lowercase letters, such as `cdntest.example.com`. Chinese characters are not supported.
        -   You can specify a wildcard domain name, such as `*.example.com`. For more information about the rules for adding wildcard domain names, see [Rules for adding wildcard domain names]().

**Note:**

            -   The specified wildcard domain name and the domain names that match the wildcard domain name must belong to the same Alibaba Cloud account. When you add a domain name to Alibaba Cloud CDN, Alibaba Cloud CDN verifies the ownership of the domain name. If the specified wildcard domain name and the domain names that match the wildcard domain name belong to different Alibaba Cloud accounts, an error message appears. To request technical support from Alibaba Cloud, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
            -   If a wildcard domain has never been added to Alibaba Cloud CDN, you can add domain names that match the wildcard domain name to Alibaba Cloud CDN by using different Alibaba Cloud accounts.
        -   You cannot add a duplicate domain name to Alibaba Cloud CDN.

If a **DomainAlreadyExist** error occurs, check whether the domain name is already added to other Alibaba Cloud services such as ApsaraVideo VOD, ApsaraVideo Live, Dynamic Route for CDN \(DCDN\), Secure CDN \(SCDN\), and Video Surveillance. You can also [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to report this issue.

        -   You can add at most 50 domain names to Alibaba Cloud CDN for each Alibaba Cloud account.

However, if the sum of the average daily peak bandwidth values of your domain names exceeds 50 Mbit/s, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to add more domain names to Alibaba Cloud CDN. Make sure that the increase of domain names does not cause business risks.

        -   The content delivered from the domain name must be legal and comply with the Terms of Service for Alibaba Cloud CDN. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md). |
        |**Business Type**|        -   [Image and small file distribution](/intl.en-US/Product Introduction/Scenarios/Image and small file distribution.md): accelerates the delivery of small-sized static content on websites, such as e-commerce content and game images.
        -   [Delivery of large files](/intl.en-US/Product Introduction/Scenarios/Delivery of large files.md): accelerates the delivery of static files that are larger than 20 MB.
        -   [ApsaraVideo for VOD](/intl.en-US/Product Introduction/Scenarios/ApsaraVideo for VOD.md): accelerates the delivery of audio or video content.
        -   [DCDN](/intl.en-US/Product Introduction/Scenarios/DCDN.md): accelerates the delivery of both static and dynamic content. DCDN can accelerate the delivery of large amounts of dynamic content.

If you set Business Type to **DCDN**, you must follow the instructions to go to the DCDN console to add and configure the domain name. For more information, see [Add a domain name](). |
        |**Origin Info**|Select **OSS Domain** and select the domain name of the selected OSS bucket. For more information, see [Map custom domain names](/intl.en-US/Console User Guide/Manage buckets/Manage a domain/Map custom domain names.md).|
        |**Port**|Select a port based on the specified origin server.         -   **Port 80**: Requests are redirected to the origin server through port 80.
        -   **Port 443**: Requests are redirected to the origin server through port 443. Make sure that the origin server supports HTTPS. |
        |**Region**|Select an accelerated region. If you select **Mainland China Only** or **Global**, you must apply for an Internet Content Provider \(ICP\) number for the domain name. We recommend that you use [Alibaba Cloud ICP Filing System](https://beian.aliyun.com/pcContainer/myorder) to apply for ICP numbers. It may take some time to update data in the database of Ministry of Industry and Information Technology \(MIIT\). After you submit domain name information to MIIT, we recommend that you wait 8 hours before you configure the domain name in Alibaba Cloud CDN. **Note:** The pricing strategies vary based on the accelerated region. Choose an accelerated region based on your business requirements. For more information about the pricing of Alibaba Cloud CDN, see [CDN Pricing](https://www.alibabacloud.com/product/cdn/pricing).

        -   **Mainland China Only**: All requests are redirected to CDN nodes that are deployed in mainland China.
        -   **Global**: All requests are redirected to the nearest CDN nodes.
        -   **Global \(Excluding Mainland China\)**: All requests are redirected to CDN nodes that are deployed outside mainland China. |

    5.  Click **Next**.

        If this is the first time the domain name is added to Alibaba Cloud CDN, Alibaba Cloud CDN must verify the ownership of the domain name. If the domain name has already passed the verification, skip this step. For more information, see [Verify the ownership of a domain name]().

    6.  Wait for manual verification.

        It takes one to two business days to verify the ownership of a domain name. If the origin server is an ECS instance or an OSS bucket, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex). It takes less time to verify the ownership of an ECS instance or an OSS bucket.

        After the domain name passes the verification, you can check the status of the domain name on the **Domain Names** page. If the domain name is in the **Enabled** state, it indicates that the domain name is added to Alibaba Cloud CDN.

2.  Log on to the Alibaba Cloud CDN console and obtain the CNAME assigned to the domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the domain name.

        ![Domain Names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8550435161/p66555.png)

3.  In the Alibaba Cloud DNS console, add a CNAME record for the domain name.

    1.  Log on to the [Alibaba Cloud DNS console](https://dns.console.aliyun.com).

    2.  On the **Manage DNS** page, find the domain name that you want to manage and click **Configure** in the Actions column.

    3.  Click **Add Record** and add a CNAME record.

        **Note:**

        -   The CNAME record of a specific domain name takes precedence over that of a wildcard domain name. If the domain name to accelerate is a wildcard domain name, and the host record includes an asterisk \(\*\), you must delete all effective DNS records of the second-level domain names that match the wildcard domain name.
        -   If the CNAME record that you want to use conflicts with an existing DNS record, we recommend that you use another domain name or modify the DNS records.
        ![Add a CNAME record](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7526528061/p64412.png)

        |Parameter|Description|Example|
        |---------|-----------|-------|
        |**Type**|Select CNAME from the drop-down list.|CNAME|
        |**Host**|Enter the prefix of the domain name.|        -   If the domain name to accelerate is `testcdn.aliyun.com`, enter `testcdn`.
        -   If the domain name to accelerate is `www.aliyun.com`, enter `www`.
        -   If the domain name to accelerate is `aliyun.com`, enter `@`.
        -   If the domain name to accelerate is `*.aliyun.com`, enter `*`. |
        |**ISP Line**|Enter the default Internet service provider \(ISP\) line.|Keep the default setting.|
        |**Value**|Enter the CNAME of the domain name.

**Note:** Each accelerated domain name is assigned a unique CNAME. Second-level domain names cannot use the CNAME of the top-level domain name. If you need to accelerate a second-level domain name, add the second-level domain name to Alibaba Cloud CDN. Alibaba Cloud then assigns a CNAME to the second-level domain name. Alternatively, you can add a second-level wildcard domain name to Alibaba Cloud CDN. Domain names that match the wildcard domain name can be mapped to the CNAME of the wildcard domain name. For more information, see [Add a domain name to Alibaba Cloud CDN](/intl.en-US/Quick Start/Add a domain name to Alibaba Cloud CDN.md).

|all.example.com.w.kunlunsl.com|
        |**TTL**|Enter a TTL value for the CNAME record. A smaller value indicates a shorter time to apply record updates. The default TTL value is 10 minutes.|Keep the default setting.|

    4.  Click **OK**.

        After the CNAME record takes effect, acceleration is immediately enabled for the domain name. After you add a CNAME record, it immediately takes effect. After you modify a CNAME record, the modifications take effect within 72 hours. After you add a CNAME record, it takes about 10 minutes for the system to update the status in the console. The system may prompt that you must add a CNAME record. Ignore the message.

4.  Use an on-premises machine to check whether the CNAME record takes effect.

    1.  Open Command Prompt in Windows.

    2.  Run the ping command to ping the domain name. If the CNAME in the output is the same as the CNAME that is assigned to the domain name, it indicates that acceleration is enabled for the domain name.

        ![Check whether the CNAME record takes effect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)

5.  In the OSS console, turn on the Auto CDN Cache Update switch for the domain name.

    **Note:** After you turn on Auto CDN Cache Update, OSS automatically refreshes objects updated in the OSS bucket on CDN nodes immediately after the update is completed. This way, the objects cached on CDN nodes are up to date. After you disassociate the domain name from the OSS bucket, OSS does not automatically refresh objects cached on CDN nodes. However, you can configure the refresh and prefetch features in the CDN console. For more information, see [Configure the refresh and prefetch features](/intl.en-US/Service Management/Configure the refresh and prefetch features.md).

    1.  Log on to the [OSS console](https://oss.console.aliyun.com/overview).

    2.  In the left-side navigation pane, click **Buckets**.

    3.  On the **Buckets** page, click the name of the bucket that you want to manage.

    4.  In the left-side domain management pane, choose **Transmission** \> **Domain Names**.

    5.  On the Domain Names tab, turn on **Auto CDN Cache Update**.

        ![Domain Names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6875464061/p87718.png)


After the CNAME record takes effect, if a client requests resources stored in an OSS bucket by including only the accelerated domain name in the request, an AccessDenied error occurs. In this case, the client can use one of the following methods to retrieve the resources:

-   To request OSS resources from a web page, include the accelerated domain name and the file path that you want to access in the request. For example, the accelerated domain name is `mydomain.cn` and the file that you want to access is 123.jpg, which is under the root directory. In this case, set URL in the request to `http://mydomain.cn/123.jpg`.
-   To request OSS resources from a client, specify the accelerated domain name as the OSS bucket domain name, and access the OSS bucket through the accelerated domain name.

