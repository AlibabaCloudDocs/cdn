---
keyword: cache hit ratio of Alibaba Cloud CDN
---

# Increase the cache hit ratios of Alibaba Cloud CDN

A low cache hit ratio of Alibaba Cloud Content Delivery Network \(CDN\) increases the loads on origin servers and slows the delivery of retrieving static resources. You can select a solution to low cache hit ratios of Alibaba Cloud CDN based on the causes.

Alibaba Cloud CDN accelerates the delivery of static resources by caching the static resources on CDN nodes that are nearest to the clients. When a client requests a resource that is cached on CDN nodes, the CDN nodes return the requested resource to the client. This simplifies the delivery process, accelerates content delivery, and reduces loads on the origin server. A low cache hit ratio increases loads on the origin server and degrades user experiences.

The cache hit ratios of Alibaba Cloud CDN are classified into byte cache hit ratios and request cache hit ratios. Differences between byte cache hit ratios and request cache hit ratios are:

-   Byte cache hit ratio = Number of bytes returned for cache hits/Number of bytes returned for all requests

    **Note:** A lower byte cache hit ratio indicates a higher amount of back-to-origin traffic. A higher amount of outbound traffic from the origin server indicates a larger bandwidth value and heavier loads on the origin server. Therefore, back-to-origin traffic represents the amount of loads on the origin server, and the byte cache hit ratio is the major concern in actual business scenarios.

-   Request cache hit ratio = Number of cache hits/Number of all requests

## View cache hit ratios

You can view cache hit ratios by using the following methods:

-   View cache hit ratios in the console

    The Alibaba Cloud CDN console displays byte hit ratios in the following ways:

    -   Resource monitoring

        Compared with real-time monitoring, resource monitoring allows you to query cache hit ratios within a longer period of time, for example, the last 30 days. Monitoring data is collected every 5 minutes, and is delayed by about 15 minutes. For more information, see [Resource monitoring](/intl.en-US/Service Management/Monitoring and usage analytics/Resource monitoring.md).

        ![Cache hit ratio](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6993655261/p278844.png)

    -   Real-time monitoring

        Compared within resource monitoring, real-time monitoring allows you to query cache hit ratios within a shorter period of time, for example, the last hour. Monitoring data is collected every minute, and is delayed by about 3 minutes. For more information, see [Real-time Monitoring](/intl.en-US/Service Management/Monitoring and usage analytics/Real-time Monitoring.md).

        ![Quality Monitoring](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3795542261/p63526.png)

-   View cache hit ratios by calling API operations
    -   API operations of resource monitoring

        |API operation|Description|
        |-------------|-----------|
        |[DescribeDomainHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainHitRateData.md)|Queries the byte hit ratios of one or more accelerated domain names. You can query data collected within the last 90 days.|
        |[DescribeDomainReqHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainReqHitRateData.md)|Queries the request hit ratios of one or more accelerated domain names. You can query data collected within the last 90 days.|

    -   API operations of real-time monitoring

        |API operation|Description|
        |-------------|-----------|
        |[DescribeDomainRealTimeByteHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeByteHitRateData.md)|Queries the byte hit ratios of one or more accelerated domain names. Data is collected every minute. You can query data collected within the last seven days.|
        |[DescribeDomainRealTimeReqHitRateData](/intl.en-US/New API Reference/Data monitoring operations/DescribeDomainRealTimeReqHitRateData.md)|Queries the request hit ratios of one or more accelerated domain names. Data is collected every minute. You can query data collected within the last seven days.|


## View log data of cache hit status

Alibaba Cloud CDN records the cache hit status of all requests. For more information about the log format, see [Download log data](/intl.en-US/Service Management/Log Management/Offline logs/Download log data.md). The cache hit status is displayed as HIT or MISS. A value of HIT indicates a cache hit, and a value of MISS indicates a cache miss, as shown in the following log entry:

```
26/Jun/2019:10:38:19 +0800] 192.168.53.146 - 1542 "-" "GET http://www.aliyun.com/index.html" 200 191 2830 MISS "Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)" "text/html"
```

**Note:** The cache hit status indicates the cache hit status only of CDN L1 nodes. For example, if the requested resource is not found in the cache of CDN L1 nodes but is found in the cache of CDN L2 nodes, the cache hit status is still displayed as MISS.

You can also call the [DescribeCdnDomainLogs](/intl.en-US/New API Reference/Log operations/DescribeCdnDomainLogs.md) operation to query the cache hit status of CDN L1 nodes.

## Causes of and solutions to low cache hit ratios

The following table describes the causes of low cache hit ratios and the solutions to the causes.

|Cause|Solution|
|-----|--------|
|Before a major event or the release of an installation package, required resources are not prefetched to CDN nodes. The required resources must be retrieved from the origin server. This reduces the cache hit ratio.

The prefetch feature allows an origin server to cache resources on CDN nodes. The first time a resource is requested, it is retrieved from CDN nodes instead of the origin server. This increases the cache hit ratio.

|[Prefetch resources](/intl.en-US/Service Management/Refresh and prefetch resources.md)|
|In the following situations, user requests are redirected to the origin server to retrieve the requested resources. The retrieved resources are then cached on CDN nodes. This reduces the cache hit ratio and increases loads on the origin server. -   No cache policies for files on the origin server are configured on CDN nodes. In this case, all user requests are redirected to the origin server.
-   A cache policy is configured on CDN nodes, but the time-to-live \(TTL\) is set to a small value. Resources cached on CDN nodes are automatically deleted after expiration.

|[Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md)|
|If request URLs contain queryString or other variables, the URLs are considered different even if they want to access the same resource. In this case, the requests are redirected to the origin server. This reduces the cache hit ratio.|-   [Retain URL parameters](/intl.en-US/Domain Management/Performance optimization/Retain URL parameters.md)
-   [Delete URL parameters](/intl.en-US/Domain Management/Performance optimization/Delete URL parameters.md) |
|If a client requests only a part of the content in the requested file but the object chunking feature is disabled, the CDN node retrieves all content in the requested file from the origin server. After the client receives the requested content that is specified by the Range field, the HTTP connection automatically closes. The retrieved file is not cached on CDN nodes. This reduces the cache hit ratio and increases loads on the origin server.|[Object chunking](/intl.en-US/Domain Management/Video-related settings/Object chunking.md)|

