# Use Alibaba Cloud CDN to accelerate the delivery of resources from ECS instances

Alibaba Cloud Content Delivery Network \(CDN\) can cache static resources stored on Elastic Compute Service \(ECS\) instances to accelerate the delivery of the resources. ECS instances can store both static and dynamic resources. When a client requests dynamic resources from an ECS instance, the ECS instance returns the requested resources to the client. When a client requests static resources from an ECS instance, if the CDN node nearest to the client has cached the requested resources, the CDN node returns the cached resources to the client. This way, the delivery of the static resources is accelerated. This topic describes how to enable Alibaba Cloud CDN to accelerate the delivery of resources on ECS instances in the Alibaba Cloud CDN console and the scenarios where Alibaba Cloud CDN can be applied.

Before you perform the tasks described in this document, make sure that you have completed [account registration](https://account.alibabacloud.com/register/intl_register.htm) and [real-name authentication](https://account-intl.console.aliyun.com/#/intlAuth) with Alibaba Cloud.

Alibaba Cloud CDN works with a precise scheduling system. This system redirects requests for static resources to CDN nodes that are nearest to the clients. This mechanism enables efficient retrieval of required resources and minimizes network congestion.

An ECS instance stores dynamic resources such as web applications and databases, and static resources such as static scripts, images, attachments, audio files, and video files. CDN nodes cache static resources rather than dynamic resources from the ECS instance. When a client requests to access or download dynamic resources, the ECS instance returns the requested resources to the client. When a client requests static resources that are cached on CDN nodes, the scheduling system redirects the request to the CDN node nearest to the client. Then, the CDN node returns the cached resources to the client. The following figure shows how Alibaba Cloud CDN accelerates the delivery of resources from an ECS instance.

![Diagram](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/855874/156896477251266_en-US.png)

In this case, the ECS instance is the origin server. The delivery of content stored on the ECS instance is accelerate by Alibaba Cloud CDN. Users retrieve files from the nearest CDN node. This architecture provides the following benefits:

-   All requests destined for the origin server are redirected to CDN nodes. This reduces the workloads on the origin server.
-   Compared with data transfer between clients and ECS instances over the Internet, data transfer between clients and CDN nodes is billed at a lower price rate.
-   Clients retrieve static resources from the nearest CDN nodes. This minimizes the network transmission distance and ensures the quality of the retrieved resources.

In the following example, Alibaba Cloud DNS is used to demonstrate how to configure a Canonical Name \(CNAME\) record.

1.  In the OSS console, set parameters to enable Alibaba Cloud CDN to accelerate the delivery of content from your ECS instance.

    1.  On the Add Domain Name page, set the following parameters and set Origin Info to **IP** or **Site Domain**.

        |Parameter|Value|Description|
        |---------|-----|-----------|
        |**Domain Name to Accelerate**|-|Enter the domain name that you want to add to Alibaba Cloud CDN, for example, ch.aliyun.com. Note that:

        -   You can use a subdomain name or a wildcard domain name as the accelerated domain name, for example, `cdntest.example.com`.
        -   Wildcard domain names are supported and Chinese domain names are not supported. Follow the instructions to enter a wildcard domain name, for example, `*.test.com`.
        -   You cannot add a duplicate domain name to Alibaba Cloud CDN. If a **DomainAlreadyExist** error occurs, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
        -   You can add at most 50 domain names to Alibaba Cloud CDN under each Alibaba Cloud account. To add more domain names, submit a ticket.
        -   Content that is delivered from your domain name must comply with the limits of Alibaba Cloud CDN and the relevant regulations. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md). |
        |**Business Type**|[Image and Small File](/intl.en-US/Product Introduction/Scenarios/Image and small file distribution.md)|If you want to accelerate the delivery of small-sized static content on your website, we recommend that you select **Image and Small File** from the Business Type drop-down list. Examples of small-sized static content include small-sized files, images, and style sheets.|
        |[Delivery of large files](/intl.en-US/Product Introduction/Scenarios/Downloads of large files.md)|If you want to accelerate the delivery of static files larger than 20 MB, we recommend that you select **Large File Download** from the Business Type drop-down list. Examples of large-sized static files include game installation packages, app update packages, mobile read-only memory \(ROM\) upgrade packages, and app packages.|
        |[VOD](/intl.en-US/Product Introduction/Scenarios/ApsaraVideo for VOD.md)|If you want to accelerate the delivery of on-demand video or audio content, we recommend that you select **VOD** from the Business Type drop-down list.|
        |[DCDN](/intl.en-US/Product Introduction/Scenarios/DCDN.md)|If your website or application contains large amounts of dynamic content, you can select DCDN from the Business Type drop-down list. After simple configurations, Dynamic Route for CDN \(DCDN\) can accelerate the delivery of dynamic and static content separately. Static content is cached and dynamic content is retrieved from the origin server based on the optimal link algorithm and protocol layer optimization of Alibaba Cloud. After you select **DCDN**, you are prompted to go to the DCDN console. You can then create and configure the domain name. For more information, see [Add a domain](). |
        |**Origin Info**|**IP** or **Site Domain**|        -   **IP**: Enter the public IP address of your server. You can enter multiple IP addresses.
        -   **Site Domain**: Enter the domain name of your origin server. You can enter multiple domain names.

**Note:** The domain name of the origin server that you specified cannot be the same as the accelerated domain name. Otherwise, a DNS resolution loop occurs and requests cannot be redirected to the origin server correctly. For example, if the domain name of your origin server is `img.yourdomain.com`, you can set the accelerated domain name to `cdn.yourdomain.com`. |
        |**Port**|-|Select a port based on your business requirements.

        -   Port 80

Data is transmitted over HTTP.

        -   Port 443

Data is transmitted over HTTPS. |
        |**Region**|Global \(Excluding Mainland China\)|If you select Global \(Excluding Mainland China\), you do not need to obtain an Internet Content Provider \(ICP\) number for the domain name.|
        |Global|If you select Global, you must obtain an ICP number for the domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|
        |Mainland China Only|If you select Mainland China Only, you must obtain an ICP number for the domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|

        ![Add the domain name to Alibaba Cloud CDN](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9942464061/p94766.png)


