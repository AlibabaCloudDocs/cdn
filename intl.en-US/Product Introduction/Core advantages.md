# Core advantages

This topic describes the core advantages of Alibaba Cloud Content Delivery Network \(CDN\). Alibaba Cloud CDN provides a wide variety of integrated features, advanced technologies, cost-effective pricing, diversified ecosystem, and comprehensive support. This allows you to make informed decisions and ensure increased business at low cost.

## Product competitiveness

**Optimal performance**

-   Alibaba Cloud CDN has the largest number of CDN nodes for content delivery acceleration in mainland China. Alibaba Cloud has deployed more than 2,300 CDN nodes in mainland China and more than 500 CDN nodes across regions outside of mainland China. For more information, see [Node distribution](/intl.en-US/Product Introduction/Node distribution.md).
-   Alibaba Cloud CDN provides more bandwidth capacity than other similar CDN products inside mainland China. The bandwidth capacity of a single CDN node exceeds 40 Gbit/s, and the total bandwidth capacity of all CDN nodes in mainland China is 130 Tbit/s.
-   Excellent key performance metrics ensure optimal user experience. Alibaba Cloud CDN provides a cache hit ratio of higher than 95% with response times measured in milliseconds. It also provides a smoothness rate of higher than 95%. This applies to accelerated video delivery. For more information, see [Common performance indicators](/intl.en-US/Product Introduction/Performance indicators of Alibaba Cloud CDN.md).

**Ease of use**

Alibaba Cloud CDN can accelerate content delivery in many different scenarios. These include the download of small and large files, on-demand video and audio streaming, live streaming media, Dynamic Route for CDN \(DCDN\), and Secure Content Delivery Network \(SCDN\). In these cases, we recommend that you use EdgeScript to customize Alibaba Cloud CDN to meet your business requirements. Alibaba Cloud CDN is a popular solution due to the features and benefits for customers. For more information, see [Case studies](/intl.en-US/Product Introduction/Case studies.md).

-   The [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview) provides a simple graphical overview of the provided features to simplify management. For more information, see [Domain Management](/intl.en-US/Domain Management/Features.md) and [Service Management](/intl.en-US/Service Management/Overview of Alibaba Cloud CDN features.md).
-   You can use EdgeScript to customize Alibaba Cloud CDN to meet your business requirements. This reduces the time that is required to release custom features. For more information, see Overview of [EdgeScript](/intl.en-US/EdgeScript/Introduction/Overview.md).

## Technological competitiveness

-   Advanced infrastructure: Linux Virtual Server \(LVS\) is used for Layer 4 load balancing and Tengine for Layer 7 load balancing. The HTTP cache protocol is written in the Swift programming language.
-   Rich API operations: In addition to using the console, you can manage the Alibaba Cloud CDN service by calling specific API operations. We recommend that you use the latest API operations. For more information, see [New API Reference](/intl.en-US/New API Reference/Introduction to the API.md).
-   SDKs for multiple languages: SDK guides provide steps about how to download, install, and use Alibaba Cloud SDKs. For more information, see [SDK for Java](https://develop.aliyun.com/tools/sdk?java#/java), [SDK for Python](https://develop.aliyun.com/tools/sdk?java#/python), [SDK for PHP](https://develop.aliyun.com/tools/sdk?java#/php), [SDK for .NET](https://develop.aliyun.com/tools/sdk?java#/dotnet), [SDK for C or C++](https://develop.aliyun.com/tools/sdk?java#/c), and [SDK for Go](https://develop.aliyun.com/tools/sdk?java#/go).

## Pricing competitiveness

The following list shows the competitive pricing of Alibaba Cloud CDN:

-   Flexible billing methods. For more information, see [Recommended billing methods and resource plans](#section_2k3_p0x_sci).
-   Resource plans are offered with discounts. For more information, see [Resource plans](https://common-buy.aliyun.com/?spm=5176.7933777.1398157.2.2fef56f5Tev9PO&commodityCode=dcdnpaybag&aly_as=L0rjD3H0#/buy).
-   If you want to use Alibaba Cloud CDN to process a large number of workloads, you can submit a ticket to contact Alibaba Cloud sales services.

## Ecological competitiveness

Alibaba Cloud provides an ecosystem of diversified services and products. The following tables describe the services and products that you can combine with Alibaba Cloud CDN in different scenarios:

-   You can integrate existing Alibaba Cloud services with Alibaba Cloud CDN. This allows you to optimize service performance and improve management efficiency.

    |Existing service|Recommended integration|Benefit|
    |----------------|-----------------------|-------|
    |[Elastic Compute Service \(ECS\)](/intl.en-US/Product Introduction/What is ECS?.md)|Alibaba Cloud CDN|If you specify ECS instances as origin servers, you can use Alibaba Cloud CDN to accelerate your websites that are deployed on the ECS instances.|
    |[Object Storage Service \(OSS\)](/intl.en-US/Product Introduction/What is OSS?.md)|You can integrate Alibaba Cloud CDN with OSS. This allows you to accelerate your websites and reduce the Internet traffic fees that are charged for data retrieval from OSS.|

-   Multiple branches of Alibaba Cloud CDN are available to support your specific scenarios.

    |Scenario|Recommended service|Benefit|
    |--------|-------------------|-------|
    |Accelerate dynamic and static content delivery|[DCDN]()|DCDN is a branch of Alibaba Cloud CDN that integrates acceleration technology for static and dynamic content. DCDN automatically separates static content from dynamic content. Then, it can be used to accelerate the delivery of both content types in parallel.|

-   If you have activated Alibaba Cloud CDN, you can integrate Alibaba Cloud CDN with other related services. This allows you to support specific scenarios.

    |Scenario|Recommended integration|Benefit|
    |--------|-----------------------|-------|
    |Accelerate on-demand audio and video streaming|[ApsaraVideo VOD](https://www.alibabacloud.com/help/doc-detail/51236.htm)|ApsaraVideo VOD \(VOD\) is an all-in-one solution for on-demand audio and video streaming. VOD supports audio and video uploads, automatic transcoding, media resource management, and delivery acceleration.|
    |Accelerate live streaming media|[ApsaraVideo Live](/intl.en-US/Product Introduction/What is ApsaraVideo Live.md)|ApsaraVideo Live is an audio and video streaming platform based on the next-generation content access and delivery network and large-scale distributed real-time transcoding technology. ApsaraVideo Live provides a low latency live video broadcast service to process concurrent requests and deliver smooth, high-resolution videos.|
    |Require a domain name to accelerate in Alibaba Cloud CDN|[Domains](/intl.en-US/Product Introduction/What is Alibaba Cloud Domains?.md)|Alibaba Cloud Domains is a domain name management platform that provides domain name registration, transaction, monitoring, and protection services. This platform also integrates the Alibaba Cloud ICP Filing and Alibaba Cloud DNS services.|
    |Require an Internet Content Provider \(ICP\) number that is granted to the domain name to accelerate in Alibaba Cloud CDN|[Alibaba Cloud ICP Filing]()|ICP filing ensures compliance with Measures for the Administration of Internet Information Services and Registration Administration Measures for Non-Commercial Internet Information Services. China mandates an ICP filing system for non-commercial Internet information services and an ICP licensing system for commercial Internet information services. Websites that do not have an ICP number or license cannot provide Internet information services. Therefore, all websites inside mainland China must have an ICP number or license. The Alibaba Cloud ICP Filing system provides guides about how to apply for ICP filing, modify ICP filing information, cancel ICP filing, and claim ICP filing.|
    |Configure HTTPS connections to all CDN nodes|[SSL Certificates Service](/intl.en-US/Product Introduction/What is SSL Certificates Service?.md)|SSL Certificates Service is a digital server certificate service provided by Alibaba Cloud. This service provides digital server certificates issued by certificate authorities \(CAs\) both inside and outside China on the Alibaba Cloud platform. You can obtain free digital certificates or purchase other types of certificates on the Alibaba Cloud platform. You can deploy these certificates in Alibaba Cloud services to convert HTTP-based services into HTTPS-based services at minimum costs. This enables your websites to implement identity verification and data transmission encryption.|


## Service competitiveness

Alibaba Cloud CDN provides comprehensive service support, including:

-   End-to-end 24/7 monitoring and support systems.
-   Enriched documentation and training systems and open technical exchanges: For more information about Alibaba Cloud CDN documents, see [What is Alibaba Cloud CDN?](/intl.en-US/Product Introduction/What is Alibaba Cloud CDN?.md).
-   Responsive troubleshooting systems:
    -   Online support: To consult about sales and after-sales issues or give feedback on Alibaba Cloud CDN, you can click **Contact Us** on the right of the Alibaba Cloud International site.
    -   Ticket system: To contact us, you can also [submit ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

## Easy activation

To activate Alibaba Cloud CDN, perform the following steps:

1.  Create an Alibaba Cloud account and pass real-name verification.
2.  Log on to the [Alibaba Cloud CDN console](https://www.alibabacloud.com/en/product/cdn) to select the required billing method. For more information, see [Recommended billing methods and resource plans](#section_2k3_p0x_sci).
3.  Click **Activate Now**. For more information, see [Activate Alibaba Cloud CDN](/intl.en-US/Quick Start/Activate Alibaba Cloud CDN.md).

After you activate the service, you can log on to the Alibaba Cloud CDN console and create an accelerated domain name. Then, Alibaba Cloud CDN team assigns a canonical name \(CNAME\) address to the accelerated domain name. You must configure a CNAME record to map the accelerated domain name to the CNAME address. After the CNAME record takes effect, Alibaba Cloud CDN can accelerate access to the accelerated domain name. For more information, see [Add a domain name to Alibaba Cloud CDN](/intl.en-US/Quick Start/Add a domain name to Alibaba Cloud CDN.md) and [Configure a CNAME record in Alibaba Cloud DNS](/intl.en-US/Quick Start/Configure a CNAME record/Configure a CNAME record in Alibaba Cloud DNS.md).

## Recommended billing methods and resource plans

Alibaba Cloud CDN supports multiple billing methods and resource plans that are applicable to different scenarios. The following recommendations allow you to select the optimal billing methods and resource plans.

|Scenario|Recommended billing method or resource plan|
|--------|-------------------------------------------|
|A small part of the bandwidth capacity is consumed by requests for the content from origin servers, but a large amount of network traffic is processed during acceleration.|Pay-by-bandwidth.|
|A small amount of network traffic is processed during the acceleration of content delivery for origin servers, but spikes in bandwidth usage occur during specific periods of time.|Pay-by-data-transfer. **Note:** We recommend that you purchase [resource plans](https://common-buy.aliyun.com/?spm=5176.8064714.323101.1.720cSlWXSlWXoT&commodityCode=dcdnpaybag#/buy) to minimize the costs. These resource plans apply to multiple accelerated regions and data transfer plans. In this scenario, the total amount of data that ranges from 100 GB to 50 PB is supported to meet your business requirements. |
|You have enabled HTTPS and the delivery of content from origin servers is accelerated over HTTPS.|[Resource plans of static and dynamic HTTPS requests](https://common-buy.aliyun.com/?spm=5176.8064714.323101.1.720cSlWXSlWXoT&commodityCode=dcdnpaybag#/buy). The fees that are charged for dynamic and static HTTPS requests are offset based on the priority of the resource plans. If the quotas provided by the resource plans are exceeded, extra fees for dynamic and static HTTPS requests are charged based on the pay-as-you-go billing method.|
|If a large number of images are delivered through Alibaba Cloud CDN every day, you can enable adult content recognition to monitor and filter adult content.|[Adult content recognition resource plans](https://common-buy.aliyun.com/?commodityCode=cdnpornbag#/buy). Multiple adult content recognition resource plans are available. The resource plans support the total number of processed images that range from 500,000 to 500,000,000.|
|If your monthly fee is higher than CNY 100,000.00,|Alibaba Cloud CDN provides a monthly 95th percentile bandwidth billing method. For more information, contact Alibaba Cloud customer services.|

For more information about the billing methods of Alibaba Cloud CDN, see [Pricing of Alibaba Cloud CDN](https://www.alibabacloud.com/product/cdn/pricing). You can also use the price calculator to estimate your expenses.

You can click [here](https://www.alibabacloud.com/product/cdn/pricing) to purchase the Alibaba Cloud CDN service.

