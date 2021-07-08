# Benefits

This topic describes the benefits of Alibaba Cloud Content Delivery Network \(CDN\) in terms of service performance, technical advantages, pricing strategies, user-friendliness, and service bundling.

## Excellent performance with user-friendly features

**Optimal performance**

-   Sufficient edge nodes: Among CDN service providers in mainland China, Alibaba Cloud has the largest number of nodes. Alibaba Cloud CDN has more than 2,800 CDN nodes deployed across the world. The total bandwidth capacity of Alibaba Cloud CDN reaches up to 150 Tbit/s, which supports 100 million concurrent queries per second. This ensures stable performance and high delivery efficiency.
-   Widely distributed nodes: Alibaba Cloud CDN nodes are deployed across 31 provincial regions in mainland China. These nodes are divided into multiple levels to form a cache hierarchy that supports low-latency and high-availability content delivery.
-   High stability and performance: The cache hit ratio of static resources is higher than 95%. Content delivery in mainland China can be accelerated by 100%. Content delivery in Hong Kong \(China\), Macao \(China\), Taiwan \(China\), and other regions outside mainland China can be accelerated by 200%.

**Ease of use**

-   Accurate caching: Alibaba Cloud CDN uses intelligent object algorithms to cache content based on object popularity in a multi-level cache hierarchy. This increases the accuracy when Alibaba Cloud CDN caches content.
-   High-speed caching: Alibaba Cloud CDN provides a high-performance caching system. This system balances the use of multi-core processing capabilities, implements efficient memory utilization and control, and maximizes input/output operations per second \(IOPS\) and throughput of solid state drives \(SSDs\).
-   High read and write rates: All nodes are configured with SSDs to support high-rate data reads and writes. Based on the acceleration capabilities, these SSDs can reduce the response time and improve the availability of CDN nodes.
-   Efficient back-to-origin process: Alibaba Cloud CDN provides failover and retransmission mechanisms to ensure an efficient back-to-origin process and information synchronization.
-   Intelligent scheduling: Alibaba Cloud CDN implements data-based real-time scheduling and supports node-level traffic prediction. This improves the scheduling quality and accuracy.
    -   Multi-level scheduling: Nodes are divided into multiple levels. This ensures service availability even if some nodes fail.
    -   Multi-system coordination: Alibaba Cloud CDN coordinates with the security defense system, refresh system, and content management system to maximize the performance of each module.
    -   Ordered processing of back-to-origin requests: Dynamic Route for CDN \(DCDN\) automatically responds to and adjusts for traffic spikes. Alibaba Cloud CDN can throttle the number of queries \(QPS\) per second to protect the availability of the origin server. The waiting room solution allows you to customize the waiting page, waiting duration, and release rules to maximize user experience.
-   You can use EdgeScript to customize Alibaba Cloud CDN to meet your business requirements. EdgeScript reduces the time that is required to release custom features.

## Technical advantages

The [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/) provides a graphical overview of the features provided by Alibaba Cloud CDN and simplifies the management of Alibaba Cloud CDN.

**Domain Name management**

-   You can add domain names to and remove domain names from Alibaba Cloud CDN, enable and disable accelerated domain names, add tags to domain names, copy configurations of multiple domain names at a time, and configure alerts for domain names.
-   You can change the accelerated region of an accelerated domain name and modify the information about origin servers.
-   You can specify a protocol for redirecting requests to origin servers, configure Server Name Indication \(SNI\) settings, set a response timeout period, configure HTTP request headers for back-to-origin requests, configure HTTP response headers for back-to-origin requests, rewrite the URI of back-to-origin requests, and rewrite URL parameters of back-to-origin requests.
-   You can refresh content on CDN nodes and prefetch content from origin servers.
-   Alibaba Cloud CDN supports HTTPS acceleration, HTTP/2 acceleration, and forcible redirects.
-   Alibaba Cloud CDN supports referer-based hotlink protection and URL signing. These features protect your content from unauthorized downloads. Alibaba Cloud CDN supports remote authentication, IP blacklists and whitelists, and user agent blacklists and whitelists. This improves service security.
-   Alibaba Cloud CDN can be integrated with various security services and protection features, including Web Application Firewall \(WAF\), Anti-DDoS services, region blacklists. These services and features protect your services from attacks.
-   Alibaba Cloud CDN supports IPv6.

**Service management**

-   Alibaba Cloud CDN can monitor the amount of data transfer and bandwidth values that are collected every 5 minutes, the number of requests that are redirected to origin servers, the number of requests, cache hit ratios, HTTP status codes, and HTTP status codes triggered by requests that are redirected to origin servers.
-   Alibaba Cloud CDN can monitor bandwidth values that are collected every minute for domain names, the number of requests per second, the amount of data transfer, the bandwidth usage of requests that are redirected to origin servers, the number of requests collected in real time, cache hit ratios, byte hit ratio, and HTTP status codes collected in real time.
-   You can query resource usage, query bills, export bills, export billing details, and query resource plans.
-   You can query and download logs within a specified time range for a specified domain name. Alibaba Cloud CDN can deliver logs to Object Storage Service \(OSS\) where logs can be retained for an extended period of time. You can enable real-time log delivery, which helps you quickly detect and locate errors.

**EdgeScript**

Alibaba Cloud CDN supports the EdgeScript \(ES\) feature. This feature allows you to customize your CDN service by running scripts if the standard configurations in the Alibaba Cloud CDN console cannot meet your business requirements.

**EdgeRoutine**

EdgeRoutine \(ER\) is a serverless computing environment provided by Alibaba Cloud Content Delivery Network \(CDN\). It can run custom JavaScript code on CDN nodes. After you use the EdgeRoutine command-line interface \(CLI\) to deploy code to the production environment, the system automatically runs the code on all CDN nodes. The CDN nodes process requests in different regions worldwide by following the logical rules of the code.

**Secure acceleration for enterprises and public service sectors**

Alibaba Cloud CDN can accelerate and secure content delivery for enterprises and public service sectors based on its globally distributed nodes. Alibaba Cloud CDN is an all-in-one content delivery service for a variety of sectors, such as public service, finance, media, retail, and transportation.

**Various API operations**

Alibaba Cloud CDN allows you to call API operations to use the preceding features and manage Alibaba Cloud CDN. For more information, see [List of operations by function](/intl.en-US/New API Reference/List of operations by function.md).

## Cost-effective pricing strategies

Alibaba Cloud CDN provides cost-effective pricing strategies.

-   Flexible metering methods. For more information, see [Billing overview](/intl.en-US/Pricing/Overview.md).
-   Discounts for subscription resource plans. For more information, see [CDN Resource Plans](https://common-buy-intl.alibabacloud.com/?spm=a2796.11741934.1343434330.1.873772f0KN5Jz5&commodityCode=%20cdn_bag_intl#/buy).
-   If you want to use Alibaba Cloud CDN to process large amounts of workloads, contact Alibaba Cloud customer service.

## Flexible service bundling

Alibaba Cloud provides an ecosystem of diversified services and products. The following tables describe the services and products that can be used together with Alibaba Cloud CDN in different scenarios.

-   You can integrate Alibaba Cloud CDN with other Alibaba Cloud services to optimize service performance and improve management efficiency.

    |Existing service|Recommended service|Benefit|
    |----------------|-------------------|-------|
    |[Elastic Compute Service \(ECS\)](/intl.en-US/Product Introduction/What is ECS?.md)|Alibaba Cloud CDN|If you use an ECS instance as an origin server, you can use Alibaba Cloud CDN to accelerate content delivery for the website that is deployed on the ECS instance.|
    |[OSS](/intl.en-US/Product Introduction/What is OSS?.md)|If you use an OSS bucket as an origin server, you can use Alibaba Cloud CDN to accelerate content delivery and reduce Internet data transfer fees.|

-   The following table describes the product branches of Alibaba Cloud CDN.

    |Scenario|Recommended service|Benefit|
    |--------|-------------------|-------|
    |Accelerate the delivery of dynamic and static content|[DCDN]()|DCDN is a branch of Alibaba Cloud CDN that can accelerate the delivery of both dynamic and static content. DCDN automatically separates dynamic content from static content and accelerates the delivery of both types of content in parallel.|

-   If you have already activated Alibaba Cloud CDN, you can integrate Alibaba Cloud CDN with other services to meet your business requirements. The following table describes services that can be used together with Alibaba Cloud CDN in different scenarios.

    |Scenario|Recommended integration|Description|
    |--------|-----------------------|-----------|
    |Accelerate on-demand audio and video streaming|[ApsaraVideo VOD \(VOD\)](https://www.alibabacloud.com/help/zh/doc-detail/51236.htm)|VOD is an all-in-one solution for on-demand audio and video streaming. VOD supports audio and video uploading, automatic transcoding, media resource management, and delivery acceleration.|
    |Accelerate live streaming|[ApsaraVideo Live](/intl.en-US/Product Introduction/What is ApsaraVideo Live?.md)|ApsaraVideo Live is an audio and video streaming platform that is based on the next-generation content access and delivery network and supports large-scale and distributed real-time transcoding. ApsaraVideo Live is a live video broadcast service that supports low latency, processes concurrent requests, and delivers smooth and high-resolution videos.|
    |Register a domain name to be accelerated by Alibaba Cloud CDN|[Domains](/intl.en-US/Product Introduction/What is Domains?.md)|Domains is a domain name management platform that provides domain name registration, transaction, monitoring, and protection services. This platform is also integrated with the Alibaba Cloud ICP Filing and Alibaba Cloud DNS services.|
    |Apply for an ICP number for the domain name to be accelerated by Alibaba Cloud CDN|[Alibaba Cloud ICP Filing]()|China mandates an ICP filing system for non-commercial Internet information services and an ICP licensing system for commercial Internet information services. You must apply for an ICP number for your domain name to comply with Measures for the Administration of Internet Information Services and Registration Administration Measures for Non-Commercial Internet Information Services. Websites that do not have an ICP number or license are prohibited from providing Internet information services. Therefore, all websites must obtain an ICP number before they are permitted to operate in mainland China. You can use the Alibaba Cloud ICP Filing system to apply for ICP numbers, modify ICP filing information, cancel ICP filing applications, and claim ICP numbers.|
    |Enable and configure HTTPS for a website|[SSL Certificates Service](/intl.en-US/Product Introduction/What is SSL Certificates Service?.md)|SSL Certificates Service is a digital server certificate service provided by Alibaba Cloud. This service provides digital server certificates issued by certification authorities \(CAs\) both inside and outside China. You can obtain free digital certificates or purchase other types of certificate from Alibaba Cloud. You can deploy these certificates in Alibaba Cloud services to enable HTTPS for HTTP-based services at minimum costs. This enables your websites to implement identity verification and data transmission encryption.|


## Service competitiveness

Alibaba Cloud CDN provides comprehensive service support, including:

-   End-to-end and 24/7 monitoring and support systems.
-   Well-maintained documentation. For more information, see [What is Alibaba Cloud CDN?](/intl.en-US/Product Introduction/What is Alibaba Cloud CDN?.md)
-   Quick-response troubleshooting systems:
    -   Online support: To consult about sales and after-sales issues or give feedback on Alibaba Cloud CDN, you can click the **Phone** icon on the right side of the Alibaba Cloud International site.
    -   Ticket system: To request technical support, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

## Recommended metering methods and resource plans

Alibaba Cloud CDN supports multiple metering methods and resource plans that are applicable to different scenarios. Select a metering method based on your business requirements.

|Scenario|Recommended metering method or resource plan|
|--------|--------------------------------------------|
|A small amount of the bandwidth capacity is consumed but a large amount of network traffic is generated by requests that are redirected to origin servers.|Pay-by-bandwidth. **Note:** |
|A small amount of network traffic is incurred by requests redirected to origin servers, but peak bandwidth values occur during certain periods of time.|Pay-by-data-transfer **Note:** We recommend that you purchase [resource plans](https://common-buy.aliyun.com/?spm=5176.8064714.323101.1.720cSlWXSlWXoT&commodityCode=dcdnpaybag#/buy) to reduce costs. Alibaba Cloud CDN provides multiple types of resource plan for different accelerated regions. The capacity of these resource plans ranges from 100 GB to 50 PB. Choose resource plans based on your business requirements. |
|The monthly fee is higher than CNY 100,000.00.|Alibaba Cloud CDN provides a monthly 95th percentile bandwidth metering method. For more information, contact Alibaba Cloud customer service.|

For more information about the metering methods of Alibaba Cloud CDN, see [CDN Pricing](https://www.alibabacloud.com/zh/product/cdn/pricing). You can also use the price calculator to estimate your expenses. You can click [here](https://www.alibabacloud.com/zh/product/cdn/pricing) to purchase Alibaba Cloud CDN.

