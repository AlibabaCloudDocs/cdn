# Benefits

Alibaba Cloud Content Delivery Network \(CDN\) offers a wide array of features and benefits. This topic describes the benefits of Alibaba Cloud CDN.

## Excellent performance with user-friendly features

**Optimal performance**

-   Alibaba Cloud CDN has the largest number of CDN nodes in mainland China. Alibaba Cloud has deployed more than 2,300 CDN nodes in mainland China and more than 500 CDN nodes in regions outside mainland China. For more information, see [Node distribution](/intl.en-US/Product Introduction/Node distribution.md).
-   The bandwidth capacity of Alibaba Cloud CDN far outweighs that of other CDN services in mainland China. The bandwidth capacity of an individual CDN node exceeds 40 Gbit/s, and the total bandwidth capacity of all CDN nodes in mainland China reaches 130 Tbit/s.
-   Excellent key performance metrics ensure optimal user experience. Alibaba Cloud CDN provides a cache hit ratio of higher than 95%, a response time of within milliseconds, and a smoothness rate of higher than 95% for video acceleration and delivery. For more information, see [Common performance indicators](/intl.en-US/Product Introduction/Performance indicators of Alibaba Cloud CDN.md).

**Ease of use**

Alibaba Cloud CDN can accelerate content delivery in a variety of scenarios, such as downloads of small and large files, on-demand video and audio streaming, live streaming media, Dynamic Route for CDN \(DCDN\), and Secure Content Delivery Network \(SCDN\). You can customize Alibaba Cloud CDN based on your business requirements through simple configurations and the EdgeScript feature. For more information about case studies, see [Case studies](/intl.en-US/Product Introduction/Case studies.md).

-   The [CDN console](https://cdn.console.aliyun.com/overview) provides a graphical overview of the features provided by Alibaba Cloud CDN and simplifies the management of Alibaba Cloud CDN. For more information, see [Domain management features](/intl.en-US/Domain Management/Features.md) and [Service management features](/intl.en-US/Service Management/Overview.md).
-   You can use the EdgeScript feature to customize your CDN service based on your business requirements. This features shortens the time required for customizing features. For more information, see [Overview](/intl.en-US/EdgeScript/Introduction/Overview.md).

## Technical advantages

-   Advanced infrastructure: Linux Virtual Server \(LVS\) is used for Layer-4 load balancing and Tengine for Layer-7 load balancing. The HTTP caching protocol is written in Swift.
-   Various API operations: In addition to using the console, you can manage your CDN service by calling API operations. We recommend that you use the latest version of the CDN API. For more information, see [Introduction to the API](/intl.en-US/New API Reference/Introduction to the API.md).
-   SDKs for multiple languages: SDK guides are available to instruct you to download, install, and use Alibaba Cloud SDKs. For more information, see [SDK for Java](https://develop.aliyun.com/tools/sdk?java#/java), [SDK for Python](https://develop.aliyun.com/tools/sdk?java#/python), [SDK for PHP](https://develop.aliyun.com/tools/sdk?java#/php), [SDK for .NET](https://develop.aliyun.com/tools/sdk?java#/dotnet), [SDK for C or C++](https://develop.aliyun.com/tools/sdk?java#/c), and [SDK for Go](https://develop.aliyun.com/tools/sdk?java#/go).

## Cost-effective pricing strategies

Alibaba Cloud CDN provides cost-effective pricing strategies.

-   Flexible billing methods. For more information, see [Recommended metering methods and resource plans](#section_2k3_p0x_sci).
-   Discounts for subscription resource plans. For more information, see [CDN/DCDN Resource Plans](https://common-buy.aliyun.com/?spm=5176.7933777.1398157.2.2fef56f5Tev9PO&commodityCode=dcdnpaybag&aly_as=L0rjD3H0#/buy).
-   If you need to use Alibaba Cloud CDN to process large amounts of workloads, contact Alibaba Cloud customer service.

## Flexible service bundling

Alibaba Cloud provides an ecosystem of diversified services and products. The following tables describe the services and products that can be used together with Alibaba Cloud CDN in different scenarios.

-   You can integrate Alibaba Cloud CDN with other Alibaba Cloud services to optimize service performance and improve management efficiency.

    |Existing service|Recommended service|Benefit|
    |----------------|-------------------|-------|
    |[Elastic Compute Service \(ECS\)](/intl.en-US/Product Introduction/What is ECS?.md)|Alibaba Cloud CDN|If you use an ECS instance as the origin server, you can use Alibaba Cloud CDN to accelerate the website deployed on the ECS instance.|
    |[Object Storage Service \(OSS\)](/intl.en-US/Product Introduction/What is OSS?.md)|If you use an OSS bucket as the origin server, you can use Alibaba Cloud CDN to accelerate content delivery and reduce data transfer fees.|

-   The following table describes the product branches of Alibaba Cloud CDN.

    |Scenario|Recommended service|Description|
    |--------|-------------------|-----------|
    |Accelerate dynamic and static content delivery.|[DCDN]()|DCDN is a branch of Alibaba Cloud CDN that can accelerate the delivery of both dynamic and static content. DCDN automatically separates dynamic content from static content and accelerates the delivery of both types of content in parallel.|

-   If you have already activated Alibaba Cloud CDN, you can integrate CDN with other services to meet your business requirements. The following table describes services that can be used together with Alibaba Cloud CDN in different scenarios.

    |Scenario|Recommended service|Description|
    |--------|-------------------|-----------|
    |Accelerate on-demand audio and video streaming|[ApsaraVideo VOD](https://www.alibabacloud.com/help/zh/doc-detail/51236.htm)|ApsaraVideo VOD \(VOD\) is an all-in-one solution for on-demand audio and video streaming. VOD supports audio and video uploading, automatic transcoding, media resource management, and delivery acceleration.|
    |Accelerate live streaming|[ApsaraVideo Live](/intl.en-US/Product Introduction/What is ApsaraVideo Live.md)|ApsaraVideo Live is an audio and video streaming platform that is based on the next-generation content access and delivery network and supports large-scale and distributed real-time transcoding. ApsaraVideo Live is a live video broadcast service that supports low latency, processes concurrent requests, and delivers smooth and high-resolution videos.|
    |Register a domain name to be accelerated by Alibaba Cloud CDN|[Domains](/intl.en-US/Product Introduction/What is Alibaba Cloud Domains?.md)|Alibaba Cloud Domains is a domain name management platform that provides domain name registration, transaction, monitoring, and protection services. This platform is also integrated with the Alibaba Cloud ICP Filing and Alibaba Cloud DNS services.|
    |Apply for an ICP number for the domain name to be accelerated by Alibaba Cloud CDN|[Alibaba Cloud ICP Filing]()|China mandates an ICP filing system for non-commercial Internet information services and an ICP licensing system for commercial Internet information services. You must apply for an ICP number for your domain name to comply with Measures for the Administration of Internet Information Services and Registration Administration Measures for Non-Commercial Internet Information Services. Websites that do not have an ICP number or license are prohibited from providing Internet information services. Therefore, all websites must obtain an ICP number before they are permitted to operate in mainland China. You can use the Alibaba Cloud ICP Filing system to apply for ICP numbers, modify ICP filing information, cancel ICP filing applications, and claim ICP numbers.|
    |Enable and configure HTTPS for a website|[SSL Certificates Service](/intl.en-US/Product Introduction/What is SSL Certificates Service?.md)|SSL Certificates Service is a digital server certificate service provided by Alibaba Cloud. This service provides digital server certificates issued by certification authorities \(CAs\) both inside and outside China. You can obtain free digital certificates or purchase other types of certificate from Alibaba Cloud. You can deploy these certificates in Alibaba Cloud services to enable HTTPS for HTTP-based services at minimum costs. This enables your websites to implement identity verification and data transmission encryption.|


## Service competitiveness

Alibaba Cloud CDN provides comprehensive service support, including:

-   End-to-end and 24/7 monitoring and support systems.
-   Well-maintained documentation. For more information, see [What is Alibaba Cloud CDN?](/intl.en-US/Product Introduction/What is Alibaba Cloud CDN?.md)
-   Quick-response troubleshooting systems:
    -   Online support: To consult about sales and after-sales issues or give feedback on Alibaba Cloud CDN, you can click **Contact Us** on the right side of the Alibaba Cloud International site.
    -   Ticket system: To request technical support, you can also [submit ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

## Easy activation

To activate Alibaba Cloud CDN, perform the following steps:

1.  Create an Alibaba Cloud account and pass real-name verification.
2.  Log on to the [Alibaba Cloud CDN console](https://www.alibabacloud.com/en/product/cdn) and select a metering method based on your business requirements. For more information, see [Recommended metering methods and resource plans](#section_2k3_p0x_sci).
3.  Click **Activate Now**. For more information, see [Activate Alibaba Cloud CDN](/intl.en-US/Quick Start/Activate Alibaba Cloud CDN.md).

After you activate Alibaba Cloud CDN, you can log on to the CDN console and add a domain name to Alibaba Cloud CDN. Alibaba Cloud CDN then assigns a canonical name \(CNAME\) to the domain name. You must configure a CNAME record to map the domain name to the CNAME. After the CNAME record takes effect, Alibaba Cloud CDN can accelerate content delivery for the domain name. For more information, see [Add a domain name to Alibaba Cloud CDN](/intl.en-US/Quick Start/Add a domain name to Alibaba Cloud CDN.md) and [Configure a CNAME record in Alibaba Cloud DNS](/intl.en-US/Quick Start/Configure a CNAME record/Configure a CNAME record in Alibaba Cloud DNS.md).

## Recommended metering methods and resource plans

Alibaba Cloud CDN supports multiple metering methods and resource plans that are applicable to different scenarios. Select a metering method based on your business requirements.

|Scenario|Recommended metering method or resource plan|
|--------|--------------------------------------------|
|A small amount of the bandwidth capacity but a large amount of network traffic is consumed by requests redirected to origin servers.|Pay-by-bandwidth|
|A small amount of network traffic is incurred by requests redirected to origin servers, but peak bandwidth values occur during certain periods of time.|Pay-by-data-transfer **Note:** We recommend that you purchase [resource plans](https://common-buy.aliyun.com/?spm=5176.8064714.323101.1.720cSlWXSlWXoT&commodityCode=dcdnpaybag#/buy) to minimize the cost. Alibaba Cloud CDN provides multiple types of resource plans for different accelerated regions. The capacity of these resource plans ranges from 100 GB to 50 PB. Choose resource plans based on your business requirements. |
|HTTPS is enabled for the origin server and users send HTTPS requests to the origin server.|[Resource plans of dynamic and static HTTPS requests](https://common-buy.aliyun.com/?spm=5176.8064714.323101.1.720cSlWXSlWXoT&commodityCode=dcdnpaybag#/buy) These resource plans can be used to offset dynamic and static HTTPS request fees. The requests that exceed the resource plans are billed based on the pay-as-you-go billing method.|
|Content moderation is required to review large numbers of images.|[Content moderation plans](https://common-buy.aliyun.com/?commodityCode=cdnpornbag#/buy) Alibaba Cloud CDN provides content moderation plans whose capacity ranges from 500,000 to 500,000,000 images. Choose plans based on your business requirements.|
|The monthly fee is higher than CNY 100,000.|Alibaba Cloud CDN provides you with a monthly 95th percentile bandwidth metering method. For more information, contact Alibaba Cloud customer service.|

For more information about the metering methods of Alibaba Cloud CDN, see [CDN Pricing](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail). You can also use the price calculator to estimate your expenses.

Alibaba Cloud CDN offers the preceding benefits. You can click [here](https://www.aliyun.com/price/product?spm=5176.7933777.1398156.1.2fef56f5Tev9PO&aly_as=TgCS3ZC5#/cdn/detail) to purchase Alibaba Cloud CDN.

