# Benefits

This topic describes the benefits of Alibaba Cloud CDN in terms of service performance, technical advantages, pricing strategies, service bundling, and service competitiveness. You can familiarize yourself with such information and choose the most suitable Alibaba Cloud services.

## Excellent performance with user-friendly features

**Widely distributed nodes**

Alibaba Cloud CDN provides more than 2,800 globally distributed edge nodes. Among these nodes, more than 2,300 are distributed in 31 provincial regions in mainland China and more than 500 are distributed in over 70 countries. The total bandwidth capacity of Alibaba Cloud CDN reaches up to 150 Tbit/s. The widely distributed nodes and high-capacity bandwidth provide secure, stable, and reliable content delivery services.

**Industry-certified capabilities**

-   Alibaba Cloud CDN is graded Level 3 by the Ministry of Public Security based on the multi-level protection scheme.
-   Alibaba Cloud CDN is certified by the Payment Card Industry Data Security Standard \(PCI DSS\).
-   Alibaba Cloud is recognized as a global-scale CDN service provider by Gartner.
-   Alibaba Cloud CDN is the first IPv6 Enabled CDN Logo certified CDN service in the world.

**Extensive features**

Alibaba Cloud CDN is an all-in-one content delivery service. It allows you to use and manage its features in the console or by calling API operations. The following table describes the major features provided by Alibaba Cloud CDN.

|Category|Feature|
|--------|-------|
|Domain name management|Supports the following features: configuration of domain names to be accelerated, basic settings, back-to-origin settings, caching settings, HTTPS settings, access control settings, performance optimization, video-related settings, security settings, advanced settings, EdgeScript \(ES\) settings, and IPv6 settings.|
|Monitoring and usage analytics|Supports the following features: resource monitoring, real-time monitoring, statistical analytics, resource usage query, ES monitoring, and security monitoring.|
|Log management|Supports the following features: log export, log storage, and real-time log delivery.|
|Refresh and prefetch|Supports the following features: URL refresh, directory refresh, and URL prefetch.|

**Custom configurations**

Alibaba Cloud CDN is an all-in-one and also programmable CDN service. You can use ES to customize Alibaba Cloud CDN. If the standard configurations in the Alibaba Cloud CDN cannot meet your business requirements, ES allows you to use scripts to customize features. ES supports quick and agile service customization.

**Custom routines on edge nodes**

EdgeRoutine \(ER\) is a serverless computing environment provided by Alibaba Cloud CDN. It can run custom JavaScript code on CDN nodes. After you use the EdgeRoutine command-line interface \(CLI\) to deploy code to the production environment, the system automatically runs the code on all CDN nodes. The CDN nodes process requests in different regions worldwide by following the logical rules of the code.

**Various API operations**

Alibaba Cloud CDN provides an API that you can call to use and manage features of Alibaba Cloud CDN. For more information, see [List of operations by function](/intl.en-US/New API Reference/List of operations by function.md).

## Technical advantages

**High-accuracy scheduling system**

-   To improve the accuracy of the scheduling system, Alibaba Cloud CDN is optimized based on the following techniques:
    -   A dynamically updated IP library: Alibaba Cloud CDN maintains a dynamically updated IP library that provides information such as regions and Internet service providers \(ISPs\) to the scheduling system when the scheduling system receives DNS resolution requests from clients. Based on the information, the scheduling system schedules user requests to their nearest CDN nodes that belong to the same ISP. The IP library is dynamically updated to ensure that the data is up to date.
    -   HTTPDNS \(requires compatibility with clients\): HTTPDNS allows clients to bypass the local DNS servers of ISPs and directly access the scheduling system over HTTP. The scheduling system then redirects the requests to optimal nodes for the destination domain names. This prevents security issues such as DNS hijacking.
    -   Node analytics: The scheduling system of Alibaba Cloud CDN analyzes the health status of all nodes and links in the caching system in real time based on the statistics provided by the link quality system. This improves user experience by increasing the link quality of CDN nodes.
    -   Content-oriented scheduling: Content-oriented scheduling increases the cache hit ratio of Alibaba Cloud CDN. 302 redirection, one of the content-oriented scheduling schemes, is used in scenarios such as large file distribution and on-demand video streaming. After a client sends a request, the request is resolved by the DNS server, redirected to the scheduling system, and then parsed by the scheduling system to locate the content that the request wants to access. Then, a 302 redirect is performed to redirect the request to an optimal node selected by the scheduling system.
-   Benefits: The scheduling system can schedule requests based on the trend of history traffic, or schedule requests in real time to handle traffic spikes.
-   Expected results: Based on the scheduling system, Alibaba Cloud CDN can monitor the health status of each node in real time and select an optimal node for each request.

**Intelligent caching system**

-   Accurate caching: Alibaba Cloud CDN uses intelligent algorithms to cache content based on object popularity in a multi-level cache hierarchy. This increases the accuracy when Alibaba Cloud CDN caches content.
-   High-speed caching: Alibaba Cloud CDN provides a high-performance caching system. This system balances the use of multi-core processing capabilities, implements efficient memory utilization and control, and maximizes input/output operations per second \(IOPS\) and throughput of solid state drives \(SSDs\).
-   High read and write rates: All nodes are configured with SSDs to support high-rate data reads and writes. Based on the acceleration capabilities, these SSDs can reduce the response time and improve the availability of CDN nodes.
-   Efficient back-to-origin process: Alibaba Cloud CDN provides failover and retransmission mechanisms to ensure an efficient back-to-origin process and information synchronization.

**Efficient transport layer protocol**

-   Quick UDP Internet Connection \(QUIC\): QUIC is a new transport layer network protocol that has inherited qualities from TCP, TLS, and HTTP/2. QUIC supports encrypted, low-latency, and multiplexed connections. These qualities can meet the requirements for the transport and application layers.
-   Independently developed algorithms for the TCP protocol suite: Alibaba Cloud has developed algorithms such as congestion detection and packet loss probing algorithms to improve the performance of TCP. The transmission performance has been significantly improved.

**Reliable protection capabilities**

Alibaba Cloud CDN integrates with various security features and services to minimize security risks for your services.

-   Hotlink protection: Alibaba Cloud CDN supports multiple types of whitelist and blacklist such as referer, user-agent, URL, and IP to implement access control. You can also use ES to customize security features to protect your origin servers from unauthorized access. Alibaba Cloud CDN also supports remote authentication, which is a two-factor authentication method used to reinforce the security of your origin servers.
-   DNS hijacking protection: HTTPDNS allows clients to bypass the local DNS servers of ISPs and access Alibaba Cloud servers over HTTP to acquire DNS resolution results. This prevents DNS hijacking.
-   HTTPS-encrypted transmission: The security of data may be compromised if it is transmitted as plaintext over the Internet. Alibaba Cloud CDN uses TLS to encrypt HTTP messages. You can also configure advanced settings such as TLS1.3, HSTS, and keyless.
-   Protection for origin servers: Alibaba Cloud CDN provides basic security features. If your origin servers require reinforced protection, you can use Secure CDN \(SCDN\).
-   High availability origin servers: Alibaba Cloud CDN supports primary and secondary origin servers, and monitors the health status of the origin servers. If the primary origin server fails, requests are redirected to a secondary origin server.

## Cost-effective pricing strategies

Alibaba Cloud CDN provides cost-effective pricing strategies.

-   Flexible metering methods. For more information, see [Billing overview](/intl.en-US/Pricing/Billing overview.md).
-   Discounts for subscription resource plans. For more information, see [CDN Resource Plans](https://common-buy-intl.alibabacloud.com/?spm=a2796.11741934.1343434330.1.873772f0KN5Jz5&commodityCode=%20cdn_bag_intl#/buy).

**Recommended metering methods and resource plans**

Alibaba Cloud CDN supports multiple metering methods and resource plans that are applicable to different scenarios. Select a metering method based on your business requirements.

|Scenario|Recommended metering method or resource plan|
|--------|--------------------------------------------|
|A small amount of network traffic is generated by requests that are redirected to origin servers, but peak bandwidth values occur during specific periods of time.|Pay-by-data-transfer **Note:** We recommend that you purchase [resource plans](https://common-buy.aliyun.com/?spm=5176.8064714.323101.1.720cSlWXSlWXoT&commodityCode=dcdnpaybag#/buy) to reduce costs. Alibaba Cloud CDN provides multiple types of resource plan for different accelerated regions. The capacity of these resource plans ranges from 100 GB to 50 PB. Choose resource plans based on your business requirements. |
|The monthly fee is higher than CNY 100,000.00.|Alibaba Cloud CDN provides a monthly 95th percentile bandwidth metering method. For more information, contact Alibaba Cloud customer service.|

For more information about the metering methods of Alibaba Cloud CDN, see [CDN Pricing](https://www.alibabacloud.com/product/cdn/pricing).

## Flexible service bundling

Alibaba Cloud provides an ecosystem of diversified services and products. The following tables describe the services and products that can be used together with Alibaba Cloud CDN in different scenarios.

-   You can integrate Alibaba Cloud CDN with other Alibaba Cloud services to optimize service performance and improve management efficiency.

    |Existing service|Recommended service|Benefit|
    |----------------|-------------------|-------|
    |[Elastic Compute Service \(ECS\)](/intl.en-US/Product Introduction/What is ECS?.md)|Alibaba Cloud CDN|If you use an ECS instance as an origin server, you can use Alibaba Cloud CDN to accelerate content delivery for the website that is hosted on the ECS instance.|
    |[Object Storage Service \(OSS\)](/intl.en-US/Product Introduction/What is OSS?.md)|If you use an OSS bucket as an origin server, you can use Alibaba Cloud CDN to accelerate content delivery and reduce Internet data transfer fees.|
    |[Function Compute]()|Function Compute is a fully-managed and event-driven computing service. Function Compute allows you to focus on writing and uploading code without the need to procure and manage infrastructure resources such as servers. Function Compute allocates computing resources, runs tasks in an elastic and reliable way, and provides features such as log query, performance monitoring, and alerting.|

-   Alibaba Cloud CDN is best suitable for accelerating the delivery of static content. If you want to accelerate the delivery of both static and dynamic content, or require reinforced protection, you can use the following services.

    |Scenario|Recommended service|Benefit|
    |--------|-------------------|-------|
    |Accelerate the delivery of both dynamic and static content|[Dynamic Route for CDN \(DCDN\)]()|DCDN is a branch of Alibaba Cloud CDN that can accelerate the delivery of both dynamic and static content. DCDN automatically separates dynamic content from static content and accelerates the delivery of both types of content in parallel.|

-   If you have already activated Alibaba Cloud CDN, you can integrate Alibaba Cloud CDN with other services to meet your business requirements. The following table describes the services that can be used together with Alibaba Cloud CDN in different scenarios.

    |Scenario|Recommended service|Benefit|
    |--------|-------------------|-------|
    |Accelerate on-demand audio and video streaming|[ApsaraVideo VOD \(VOD\)](https://www.alibabacloud.com/help/doc-detail/51236.htm)|VOD is an all-in-one solution for on-demand audio and video streaming. VOD supports audio and video uploading, automatic transcoding, media resource management, and delivery acceleration.|
    |Accelerate live streaming|[ApsaraVideo Live](/intl.en-US/Product Introduction/What is ApsaraVideo Live?.md)|ApsaraVideo Live is an audio and video streaming platform that is based on the next-generation content access and delivery network and supports large-scale and distributed real-time transcoding. ApsaraVideo Live is a live video broadcast service that supports low latency, processes concurrent requests, and delivers smooth and high-resolution videos.|
    |Register a domain name to be accelerated by Alibaba Cloud CDN|[Domains](/intl.en-US/Product Introduction/What is Domains?.md)|Domains is a domain name management platform that provides domain name registration, transaction, monitoring, and protection services. This platform is also integrated with the Alibaba Cloud ICP Filing and Alibaba Cloud DNS services.|
    |Apply for an Internet Content Provider \(ICP\) number for the domain name to be accelerated by Alibaba Cloud CDN|[Alibaba Cloud ICP Filing]()|China mandates an ICP filing system for non-commercial Internet information services and an ICP licensing system for commercial Internet information services. You must apply for an ICP number for your domain name to comply with Measures for the Administration of Internet Information Services and Registration Administration Measures for Non-Commercial Internet Information Services. Websites that do not have an ICP number or license are prohibited from providing Internet information services. Therefore, all websites must obtain an ICP number before they are permitted to operate in mainland China. You can use the Alibaba Cloud ICP Filing system to apply for ICP numbers, modify ICP filing information, cancel ICP filing applications, and claim ICP numbers.|
    |Enable and configure HTTPS for a website|[SSL Certificates Service](/intl.en-US/Product Introduction/What is SSL Certificates Service?.md)|SSL Certificates Service is a digital server certificate service provided by Alibaba Cloud. This service provides digital server certificates issued by certification authorities \(CAs\) inside or outside China. You can obtain free digital certificates or purchase other types of certificate from Alibaba Cloud. You can deploy these certificates in Alibaba Cloud services to enable HTTPS for HTTP-based services at minimum costs. This enables your websites to implement identity verification and data transmission encryption.|
    |Improve the operation and maintenance \(O&M\) efficiency, and process large volumes of log data|[Log Service](/intl.en-US/Product Introduction/What is Log Service?.md)|Log Service is a one-stop logging service developed by Alibaba Cloud. It has shown superior performance in big data scenarios. Log Service helps you collect, consume, ship, query, and analyze log data without development work. It improves the O&M efficiency, and provides the capability to process large volumes of log data.|
    |Monitor Alibaba Cloud resources and Internet applications|[CloudMonitor](/intl.en-US/Product Introduction/What is CloudMonitor?.md)|CloudMonitor is a service that focuses on the monitoring of Alibaba Cloud resources and Internet applications. CloudMonitor collects monitoring metrics of Alibaba Cloud resources. You can use CloudMonitor to detect the availability of your network and set alerts for specific metrics.|


## Service competitiveness

Alibaba Cloud CDN provides comprehensive service support, including:

-   End-to-end and 24/7 monitoring and support systems.
-   Well-maintained documentation. For more information, see [What is Alibaba Cloud CDN?](/intl.en-US/Product Introduction/What is Alibaba Cloud CDN?.md)
-   Quick-response troubleshooting systems:
    -   Online support: To consult about pre-sales and after-sales issues or give feedback on Alibaba Cloud CDN, you can click the **Phone** icon on the right side of the Alibaba Cloud International site.
    -   Ticket system: To request technical support, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

