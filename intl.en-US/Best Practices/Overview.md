---
keyword: CDN cache hit ratio
---

# Overview

A low Content Delivery Network \(CDN\) cache hit ratio increases the workloads on origin servers and causes low access efficiency of static resources. You can select an optimization strategy to improve the cache hit ratio based on the specific cause.

Alibaba Cloud CDN accelerates the delivery of static resources by caching the static resources to CDN nodes that are nearest to the clients. When a client requests a resource, the CDN node retrieves the requested resource cached on the nearest CDN node instead of the origin server. Therefore, CDN cache hit ratios affect user experience. The increase of cache hit ratios has become a core element of the CDN performance.

CDN cache hit ratios include the byte cache hit ratio and request cache hit ratio.

-   Byte cache hit ratio = Number of bytes returned for cache hits/Number of bytes returned for all requests

    **Note:** A lower byte cache hit ratio indicates a higher amount of back-to-origin traffic. A higher amount of outbound traffic from the origin server indicates a larger bandwidth value and heavier workloads of the origin server. Therefore, back-to-origin traffic represents the amount of workloads on the origin server, and the byte cache hit ratio is the major concern in actual business scenarios.

-   Request cache hit ratio = Number of cache hits/Number of all requests

## View CDN cache hit ratios

You can view cache hit ratios through one of the following methods:

-   Console

    The Alibaba Cloud CDN console displays byte hit ratios on the Quality Monitoring tab, as shown in the following figure.

    ![Quality Monitoring](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3795542261/p63526.png)

-   Log data

    Alibaba Cloud CDN records the cache hit status of all requests. For more information about the log format, see [Download log data](/intl.en-US/Service Management/Log Management/Download log data.md). The cache hit status field is displayed as HIT or MISS. Sample log entry:

    ```
    26/Jun/2019:10:38:19 +0800] 192.168.53.146 - 1542 "-" "GET http://www.aliyun.com/index.html" 200 191 2830 MISS "Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)" "text/html"
    ```

    **Note:** The hit status only indicates the hit status of CDN L1 nodes. For example, if the requested resource is not found in the cache of CDN L1 nodes but is found in the cache of CDN L2 nodes, the hit status is still displayed as MISS.

-   API

    To query the byte cache hit ratio, call the [DescribeDomainHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainHitRateData.md) operation. To query the request cache hit ratio, call the [DescribeDomainReqHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainReqHitRateData.md) operation.


## Increase CDN cache hit ratios

The following table describes the causes of a low cache hit ratio and the corresponding optimization strategies.

|Optimization strategy|Cause|
|---------------------|-----|
|[Prefetch resources](/intl.en-US/Service Management/Refresh and prefetch resources.md)|-   During peak hours, a large number of requests are redirected to the origin server.
-   If the accelerated domain name is not frequently visited, resources of the domain name that are cached on CDN nodes may be removed before the resources expire. |
|[Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md)|When the ETag or Last-Modified response header is not returned, the requested static resource fails to be cached on CDN nodes.|
|[Retain URL parameters](/intl.en-US/Domain Management/Performance optimization/Retain URL parameters.md)|When the URL of a request includes a query string or other variable parameters, the requested resource needs to be retrieved from the origin server.|

