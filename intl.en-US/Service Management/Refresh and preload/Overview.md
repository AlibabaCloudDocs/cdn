# Overview {#concept_490971 .concept}

CDN supports the resource refresh and preload features. The refresh feature allows you to force CDN nodes to communicate with origins and obtain the latest files. The preload feature allows you to preload popular resources during peak hours from origins to CDN nodes to improve resource access efficiency. This topic describes how the refresh and preload features work, the time required by a refresh or preload task to take effect, and the related API operations.

The concepts of refresh and preload in CDN are as follows:

-   Refresh: After a URL refresh or directory refresh request is submitted, the content cached on the CDN node will forcibly expire. When you request resources from the CDN node, the CDN node directly forwards the request to the origin to query the corresponding resources. The CDN node then returns the resources to you and caches them. The refresh feature reduces the cache hit rate.
-   Preload: After a URL preload request is submitted, the origin site automatically caches the corresponding resources to the CDN node. When you request the resources for the first time, you can obtain the latest resources directly from the CDN node cache without having the request rerouted to the origin site. The preload feature increases the cache hit rate.

The following table describes the refresh and preload features.

|Category|How it works|Time to take effect|API operation|
|--------|------------|-------------------|-------------|
|URL refresh|Specify files to force a CDN node to retrieve the latest files from the origin.|Within 5 minutes|[RefreshObjectCaches](https://www.alibabacloud.com/help/doc-detail/91164.htm)|
|Directory refresh|Specify directories to force a CDN node to retrieve the latest files in the directories from the origin.|[RefreshObjectCaches](https://www.alibabacloud.com/help/doc-detail/91164.htm)|
|URL preload|Specify files to actively preload corresponding resources from the origin to a CDN L2 node. As a result, users can directly hit the cache upon their first visits to these resources.|[PushObjectCache](https://www.alibabacloud.com/help/doc-detail/91161.htm)|

