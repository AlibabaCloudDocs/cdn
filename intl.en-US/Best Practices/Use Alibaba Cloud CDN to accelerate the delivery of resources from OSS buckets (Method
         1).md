---
keyword: [CDN accelerates OSS resources, CDN console]
---

# Use Alibaba Cloud CDN to accelerate the delivery of resources from OSS buckets \(Method 1\)

You can use Alibaba Cloud Content Delivery Network \(CDN\) to accelerate the delivery of static resources from an Object Storage Service \(OSS\) bucket. This topic describes how to enable Alibaba Cloud CDN to accelerate the delivery of resources from an OSS bucket in the OSS console and the scenarios where Alibaba Cloud CDN can be applied.

## Prerequisites

-   Before you perform the tasks described in this document, make sure that you have completed [account registration](https://account.alibabacloud.com/register/intl_register.htm) and [real-name authentication](https://account-intl.console.aliyun.com/#/intlAuth) with Alibaba Cloud.

-   An OSS bucket is created and associated with a custom domain name. For more information, see [Create buckets](/intl.en-US/Quick Start/Create buckets.md) and [Bind custom domain names](/intl.en-US/Console User Guide/Manage buckets/Manage a domain/Bind custom domain names.md).

## Background information

Alibaba Cloud CDN works with a precise scheduling system. This system redirects requests for static resources to CDN nodes that are nearest to the clients. This mechanism enables efficient retrieval of requested resources and minimizes network congestion.

Static resources stored in an OSS bucket include static scripts, images, attachments, audio files, and video files. CDN nodes cache static resources from the OSS bucket. When a client requests the cached static resources, the scheduling system redirects the request to the CDN node that is nearest to the client. Then, the CDN node returns the cached resources to the client. The following figure shows how Alibaba Cloud CDN accelerates the delivery of resources from an OSS bucket.

![Diagram](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/669798/156860449150521_en-US.png)

In this case, the OSS bucket is the origin server. The delivery of content stored in the OSS bucket is accelerated by Alibaba Cloud CDN. Users retrieve files from the nearest CDN nodes. This architecture provides the following benefits:

-   All requests destined for the origin server are redirected to CDN nodes. This reduces the workloads on the origin server.
-   Compared with data transfer between clients and OSS buckets over the Internet, data transfer between clients and CDN nodes is billed at a lower price rate.
-   Clients retrieve static resources from the nearest CDN nodes. This minimizes the network transmission distance and ensures the quality of the retrieved resources.

The following section describes how to add a Canonical Name \(CNAME\) record in the Alibaba Cloud Domain Name System \(DNS\) console.

## Procedure

1.  In the Alibaba Cloud CDN console, add the domain name associated with the OSS bucket to Alibaba Cloud CDN.

    1.  Log on to the[Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, click **Add Domain Name**.

    4.  Set the following parameters and set Origin Info to **OSS Domain**.

        |Parameter|Value|Description|
        |---------|-----|-----------|
        |**Domain Name to Accelerate**|-|Enter the domain name that you want to add to Alibaba Cloud CDN, for example, ch.aliyun.com. Take note of the following limits:

        -   You can use a subdomain name or a wildcard domain name as the accelerated domain name, for example, `cdntest.example.com`.
        -   Wildcard domain names are supported and Chinese domain names are not supported. Follow the instructions to enter a wildcard domain name, for example, `*.test.com`.
        -   You cannot add a duplicate domain name to Alibaba Cloud CDN. If a **DomainAlreadyExist** error occurs, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
        -   You can add at most 50 domain names to Alibaba Cloud CDN under each Alibaba Cloud account. To add more domain names, submit a ticket.
        -   Content that is delivered from your domain name must comply with the limits of Alibaba Cloud CDN and the relevant regulations. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md). |
        |**Business Type**|[Image and Small File](/intl.en-US/Product Introduction/Scenarios/Image and small file distribution.md)|If you want to accelerate the delivery of small-sized static content on your website, we recommend that you select **Image and Small File** from the Business Type drop-down list. Examples of small-sized static content include small-sized files, images, and style sheets.|
        |[Delivery of large files](/intl.en-US/Product Introduction/Scenarios/Downloads of large files.md)|If you want to accelerate the delivery of static files larger than 20 MB, we recommend that you select **Large File Download** from the Business Type drop-down list. Examples of large-sized static files include game installation packages, app update packages, mobile read-only memory \(ROM\) upgrade packages, and app packages.|
        |[VOD](/intl.en-US/Product Introduction/Scenarios/ApsaraVideo for VOD.md)|If you want to accelerate the delivery of on-demand video or audio content, we recommend that you select **VOD** from the Business Type drop-down list.|
        |[DCDN](/intl.en-US/Product Introduction/Scenarios/DCDN.md)|If your website or application contains large amounts of dynamic content, you can select DCDN from the Business Type drop-down list. After simple configurations, Dynamic Route for CDN \(DCDN\) can accelerate the delivery of dynamic and static content separately. Static content is cached and dynamic content is retrieved from the origin server based on the optimal link algorithm and protocol layer optimization of Alibaba Cloud. After you select **DCDN**, you are prompted to go to the DCDN console. You can then add and configure the domain name. For more information, see [Add a domain](). |
        |**Origin Info**|OSS Domain|For more information about how to associate an OSS bucket with a custom domain name, see [Bind custom domain names](/intl.en-US/Console User Guide/Manage buckets/Manage a domain/Bind custom domain names.md).|
        |**Port**|-|Select a port based on your business requirements.

        -   Port 80

Data is transmitted over HTTP.

        -   Port 443

Data is transmitted over HTTPS. |
        |**Region**|Global \(Excluding Mainland China\)|If you select Global \(Excluding Mainland China\), you do not need to obtain an Internet Content Provider \(ICP\) number for the domain name.|
        |Global|If you select Global, you must obtain an ICP number for the domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|
        |Mainland China Only|If you select Mainland China Only, you must obtain an ICP number for the domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|

        ![intl](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8457192061/p94747.png)

    5.  Click **Next**.

        After your domain name passes the review, you can view the domain name on the **Domain Names** page in the Alibaba Cloud CDN console. If the domain name is in the **Enabled** state, it indicates that the domain name is added to Alibaba Cloud CDN.

        ![The domain name is added](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8457192061/p62084.png)

2.  Log on to the Alibaba Cloud CDN console and obtain the CNAME assigned to the domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the accelerated domain name.

        ![Click Domain Names](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3630062061/p66555.png)

3.  In the Alibaba Cloud DNS console, add a CNAME record for the domain name.

    1.  Log on to the [Alibaba Cloud DNS console](https://dc.console.aliyun.com/dns).

    2.  On the Manage DNS page, click the Domains tab, select the domain name that you want to manage, and then click **Configure** in the Actions column.

    3.  Click **Add Record** and add a CNAME record.

        ![Add a CNAME record](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3630062061/p64412.png)

        -   Type: Select `CNAME` from the drop-down list.
        -   Host: Enter the prefix of the accelerated domain name.

            |Accelerated domain name|Host|
            |:----------------------|:---|
            |`testcdn.aliyun.com`|`testcdn`|
            |`www.aliyun.com`|`www`|
            |`aliyun.com`|`@`|
            |`*.aliyun.com`|`*`|

        -   ISP Line: Use the default value.
        -   Value: Enter the CNAME assigned to the accelerated domain name.
        -   TTL: Use the default value.
    4.  Click **OK**.

        The CNAME record is added. After the CNAME record takes effect, CDN acceleration is automatically enabled for the domain name.

        **Note:**

        -   After you add a CNAME record, it immediately takes effect. After you modify a CNAME record, the modifications take effect within 72 hours.
        -   After you add a CNAME record, it takes approximately 10 minutes for the system to update the status in the console. The system may prompt that you must add a CNAME record. Ignore the message.
4.  On an on-premises machine, check whether the CNAME record works as expected.

    1.  Open the Command Prompt in Windows.

    2.  Use the Command Prompt to ping the accelerated domain name. If the CNAME in the output matches the CNAME assigned to the accelerated domain name in the Alibaba Cloud CDN console, it indicates that the CDN service is enabled for the domain name.

        ![Check whether the CNAME record has taken effect](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)

5.  In the OSS console, turn on the Auto CDN Cache Update switch for the domain name.

    **Note:**

    After Auto CDN Cache Update is enabled, OSS automatically refreshes objects updated in the OSS bucket on CDN nodes immediately after the update is completed. This way, the objects cached on CDN nodes are up to date.

    After you disassociate the domain name from the OSS bucket, OSS does not automatically refresh objects cached on CDN nodes. However, you can configure the refresh and prefetch features in the CDN console. For more information, see [Configure the refresh and prefetch features](/intl.en-US/Service Management/Refresh and preload/Configure the refresh and prefetch features.md).

    1.  Log on to the [OSS console](https://oss.console.aliyun.com/overview).

    2.  In the left-side navigation pane, click **Buckets**.

    3.  On the **Buckets** page, click the name of the bucket that you want to manage.

    4.  In the left-side domain management pane, choose **Transmission** \> **Domain Names**.

    5.  On the Domain Names tab, turn on the **Auto CDN Cache Update** switch.

        ![Domain Names](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6875464061/p87718.png)


After the CNAME record takes effect, if a client requests resources stored in an OSS bucket by including only the accelerated domain name in the request, an AccessDenied error occurs. In this case, the client can use one of the following methods to retrieve the resources:

-   To request OSS resources on a web page, include the accelerated domain name followed by the file path that you want to access in the request. For example, if the accelerated domain name is `mydomain.cn` and the file that you want to access is 123.jpg, which is under the root directory, the URL in the request is `http://mydomain.cn/123.jpg`.
-   To request OSS resources from a client, specify the accelerated domain name as the OSS bucket domain name, and access the OS bucket through the accelerated domain name.

