# Overview

Alibaba Cloud Content Delivery Network \(CDN\) retrieves resources from origin servers and caches the resources on CDN nodes deployed across the world. When a client sends a request, the system does not need to send the request to the origin server. Instead, the system automatically retrieves the requested resource cached on the CDN node that is closest to the client and returns the resource to the client. This topic describes how content delivery is accelerated in accelerated regions outside mainland China.

## Benefits

Alibaba Cloud CDN provides more than 2,800 nodes deployed across the world. More than 500 nodes are deployed across 70 countries and regions outside mainland China, including China \(Hong Kong\), China \(Macao\), and China \(Taiwan\). Alibaba Cloud CDN supports a total bandwidth capacity of 130 Tbit/s and 10 GE network interface controllers \(NICs\). Each CDN node provides 40 TB to 1.5 PB of data storage, and a bandwidth capacity of 40 Gbit/s to 200 Gbit/s. Alibaba Cloud CDN offers the following benefits:

Stability and high speed

-   Stable performance and high efficiency: a cache hit ratio of higher than 95%, a smooth video streaming rate of higher than 95%, and a response time of milliseconds.
-   Network-wide monitoring and intelligent service systems: 24/7 network-wide and intelligent monitoring and scheduling based on service quality.

Cost-effectiveness

-   You can elastically scale resources and pay for the resources based on the actual usage. Content delivery can be accelerated across Internet service providers \(ISPs\) and regions.
-   Alibaba Cloud CDN supports the pay-by-data-transfer and pay-by-bandwidth metering methods. Both metering methods charge fees on a pay-as-you-go basis. You can select a metering method based on your business requirements.
-   Alibaba Cloud CDN automatically responds to traffic spikes of accelerated domain names and makes adjustments to reduce workloads on origin servers.

Ease of use

-   Alibaba Cloud CDN provides an easy-to-use console. In the CDN console, you can customize configurations of domain names. For example, you can add, delete, modify, and query domain names. In addition, Alibaba Cloud CDN also allows you to customize hotlink protection rules, cache policies, and HTTP response headers.
-   Alibaba Cloud CDN provides a wide array of API operations that enable you to use the features of Alibaba Cloud CDN. For example, you can call API operations to activate Alibaba Cloud CDN, refresh content, query monitoring data, and download and deliver log data.

High efficiency and intelligence

-   Alibaba Cloud CDN provides standard configurations that can be quickly and automatically applied.
-   The Alibaba Cloud CDN console can quickly respond to user requests to ensure a smooth user experience. Compared with other CDN services, Alibaba Cloud CDN does not require manual intervention, which minimizes the response time.

## Scenarios

Alibaba Cloud CDN can be applied in the following scenarios to accelerate content delivery in regions outside mainland China, including China \(Hong Kong\), China \(Macao\), and China \(Taiwan\):

-   Small image files: Your websites or applications offer downloads of images and small files in formats such as HTML, CSS, and JavaScript.
-   Downloads of large files: Your websites or applications offer downloads of files larger than 20 MB, such as game applications, client applications, or mobile apps.
-   On-demand audio and video streaming: Your websites or applications offer on-demand video streaming or short video streaming. Mainstream media formats such as MP4 and FLV are supported.
-   Dynamic Route for CDN \(DCDN\) is an independent Alibaba Cloud service and can accelerate the delivery of dynamic content. You can also use DCDN to accelerate the delivery of static and dynamic content separately.
-   Secure acceleration: If your website is vulnerable to attacks and requires delivery acceleration, you can use HTTPS to reinforce the security of your workloads.

## Metering methods

Alibaba Cloud CDN supports the following metering methods: pay-by-data-transfer and pay-by-bandwidth. Value-added services are billed based on the actual usage, such as the number of HTTPS requests to static resources. Related topics:

-   [Pay by traffic](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Billing rules/Pay by traffic.md)
-   [Pay-by-bandwidth](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Billing rules/Pay-by-bandwidth.md)
-   [Billing of value-added services](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Billing rules/Billing of value-added services.md)

Both the subscription and pay-as-you-go billing methods charge fees based on the actual resource usage. Alibaba Cloud CDN provides cost-effective subscription resource plans. For more information, see [CDN/DCDN resource plans](https://common-buy.aliyun.com/?commodityCode=dcdnpaybag#/buy).

Both the subscription and pay-as-you-go billing methods charge fees based on the actual resource usage. Alibaba Cloud CDN provides cost-effective subscription resource plans. For more information, see [CDN/DCDN resource plans](https://common-buy-intl.aliyun.com/?commodityCode=%20cdn_bag_intl#/buy).

For more information about the pricing of Alibaba Cloud CDN, see [Pricing of CDN](https://www.alibabacloud.com/zh/product/cdn/pricing).

## Acceleration methods

After you create an Alibaba Cloud account and pass real-name verification, you can use Alibaba Cloud CDN in the CDN console or through API operations to accelerate content delivery in regions outside mainland China, including China \(Hong Kong\), China \(Macao\), and China \(Taiwan\). For more information, see:

-   [Configure CDN acceleration in accelerated regions outside mainland China in the CDN console](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Configure CDN acceleration/Configure Alibaba Cloud CDN in accelerated regions outside mainland China in the CDN
         console.md)
-   [Make API calls to accelerate content delivery outside mainland China](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Configure CDN acceleration/Make API calls to accelerate content delivery outside mainland China.md)

**Note:** Whether you need to file for an ICP number for the domain name to be accelerated depends on the accelerated region. If you select Global or Mainland China Only, you must file for an ICP number for the domain name. We recommend that you apply for an ICP number through Alibaba Cloud ICP Filing System.

## Related services

This section describes the related services of Alibaba Cloud CDN to help you understand the position and use of Alibaba Cloud CDN among other Alibaba Cloud services.

|Related service|Benefit|
|---------------|-------|
|[Object Storage Service \(OSS\)](/intl.en-US/Product Introduction/What is OSS?.md)|You can integrate Alibaba Cloud CDN with OSS to accelerate access to websites. This way, you can retrieve content directly from CDN nodes to reduce the costs of Internet data transfer.|
|[ApsaraVideo Live](https://www.alibabacloud.com/help/product/29949.htm)|You can integrate Alibaba Cloud CDN with ApsaraVideo Live to achieve media feed storage, video segmentation and transcoding, access authentication, and content delivery acceleration.|
|[Alibaba Cloud DNS](https://www.alibabacloud.com/help/product/29697.htm)|You can use Alibaba Cloud DNS that is highly available and scalable to ensure smooth access to resources.|
|[Elastic Compute Service \(ECS\)](/intl.en-US/Product Introduction/What is ECS?.md)|You can use Alibaba Cloud CDN with ECS to improve website availability, protect origin information, and minimize bandwidth usage costs.|
|[Server Load Balancer \(SLB\)](/intl.en-US/Classic Load Balancer/Product Introduction/What is CLB?.md)|You can specify the IP address of an SLB instance as the origin address to balance the bandwidth required for retrieving resources from the origin server.|

