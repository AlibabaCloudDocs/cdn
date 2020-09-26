---
keyword: Refresh and prefetch
---

# Overview

Alibaba Cloud Content Delivery Network \(CDN\) supports resource refresh and prefetch. The refresh feature allows you to force CDN nodes to retrieve the latest version of the resources from the origin. The prefetch feature allows you to cache frequently requested resources on CDN nodes before peak hours to accelerate content delivery. This topic describes how the refresh and prefetch features work, the amount of time that it takes to refresh or prefetch resources, and the related API operations.

The refresh and prefetch features of Alibaba Cloud CDN are described as follows:

-   Refresh: After you submit a URL or directory refresh request, the corresponding resource cached on the CDN node will forcibly expire. When a client requests the resource, the CDN node retrieves the latest version of the resource from the origin, returns the resource to the client, and then caches the resource. The refresh feature reduces the cache hit ratio.
-   Prefetch: After you submit a URL prefetch request, the origin automatically caches the corresponding resource on the CDN node. When a client requests the resource for the first time, the CDN node returns the cached resource to the client without the need to reroute the request to the origin. The prefetch feature increases the cache hit ratio.

The following table describes the refresh and prefetch features in details.

|Category|How it works|Time consumption|API operation|
|--------|------------|----------------|-------------|
|URL refresh|CDN nodes are forced to retrieve the latest version of the specified files from the origin.|It takes less than five minutes to refresh or prefetch resources.|[RefreshObjectCaches](/intl.en-US/New API Reference/Refresh and preload operations/RefreshObjectCaches.md)|
|Directory refresh|CDN nodes are forced to retrieve the latest version of the files in the specified directories from the origin.|[RefreshObjectCaches](/intl.en-US/New API Reference/Refresh and preload operations/RefreshObjectCaches.md)|
|URL refresh using regular expressions|You can use regular expressions to refresh all matching URLs.|N/A|
|URL prefetch|Alibaba Cloud CDN retrieves the specified resources from the origin and caches them on CDN L2 nodes. When a client requests these resources for the first time, the nearest CDN L2 node returns the cached resources to the client.|[t65109.md\#](/intl.en-US/New API Reference/Refresh and preload operations/PushObjectCache.md)|

