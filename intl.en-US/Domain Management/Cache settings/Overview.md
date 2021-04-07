# Overview

When Alibaba Cloud Content Delivery Network \(CDN\) accelerates the delivery of static resources to a user, it retrieves the resources from the origin server and caches them on the CDN node that is nearest to the user. When the resources are requested again, the CDN node directly returns the resources to the user. This accelerates content delivery.

## Default TTL value

If you have not created a cache expiration rule on your origin server or in the Alibaba Cloud CDN console, the default cache expiration rule applies. The default time-to-live \(TTL\) value for cached resources is 10 seconds and the maximum is 3,600 seconds. You can modify the TTL value in the Alibaba Cloud CDN console. For more information, see [Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md).

**Note:** The amount of back-to-origin network traffic and fees vary based on the TTL value. We recommend that you set a TTL value based on your business requirements. A small TTL value may cause CDN nodes to frequently redirect requests to the origin server and increase the amount of network traffic on the origin server.

-   The default TTL value is calculated based on the following formula: t = \(curtime - last\_modified\) × 0.1.
-   Valid TTL values are from 10 to 3600.

Parameters and descriptions:

-   t: the default TTL value, in seconds.
-   curtime: the current time.
-   last\_modified: the last time when the resources on the origin server were updated.

Examples:

-   If the `last_modified` value of an object is `20140801 00:00:00` and the current time is `20140801 00:01:00`, t = \(curtime-last\_modified\) × 0.1 = 6 seconds. Based on the rules, the TTL value is 10 seconds because the minimum value is 10 seconds.
-   If the `last_modified` value of an object is `20140801 00:00:00` and the current time is `20140802 00:00:00`, t = \(curtime-last\_modified\) × 0.1 = 8,640 seconds. Based on the rules, the TTL value is 3,600 seconds because the maximum value is 3,600 seconds.
-   If the `last_modified` value of an object is `20140801 00:00:00` and the current time is `20140801 00:10:00`, t = \(curtime-last\_modified\) × 0.1 = 60 seconds. Based on the rules, the TTL value is 60 seconds.

## Default cache expiration rule

-   If the response from the origin server does not contain the `last_modified` header but contains the `ETag` header, the retrieved object is considered a static resource. The default TTL value for this object is set to the minimum value. You can use the `dft_expires` directive to configure the minimum value.
-   If the response from the origin server does not contain the `last_modified` or `ETag` header, the retrieved object is considered a dynamic resource. The default TTL value for this object is set to 0 seconds. The object must be retrieved from the origin server each time it is requested.

Parameters and descriptions:

-   ETag: the identifier of a resource.
-   dft\_expires: the expiration time of a resource stored in the cache directory of the client. The expiration time is specified by the server.

## Related features

The following table describes the operations that you can perform on a domain name by using the caching feature.

|Feature|Description|
|-------|-----------|
|[Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md)|Allows you to configure cache expiration rules for static resources in a specified directory or with specified file extensions. In each cache expiration rule, you can set a TTL value for the cached static resources and a priority for the rule. CDN nodes cache and expire static resources based on the cache expiration rules.|
|[Create a cache expiration rule for HTTP status codes](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule for HTTP status codes.md)|Allows you to set a TTL value for HTTP status codes that are returned to requests for resources in a specified directory or with specified file extensions.|
|[Create a custom HTTP response header](/intl.en-US/Domain Management/Cache settings/Create a custom HTTP response header.md)|Allows you to customize HTTP response headers for expired resources.|
|[Create a custom error page](/intl.en-US/Domain Management/Cache settings/Create a custom error page.md)|Allows you to customize an error page for a specific HTTP status code.|
|[Create a URI rewrite rule](/intl.en-US/Domain Management/Cache settings/Create a URI rewrite rule.md)|Allows you to rewrite URIs in requests and performs 302 redirects to redirect the requests to the destination URIs.|

