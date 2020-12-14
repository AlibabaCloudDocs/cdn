# Overview

When Alibaba Cloud Content Delivery Network \(CDN\) accelerates static resource delivery, it loads resources from an origin server to the available CDN node that is closest to the visitor. When the visitor accesses the static resources, Alibaba Cloud CDN retrieves the resources from the CDN node instead of the origin server. This reduces the resource delivery time. It may take more time for the system to retrieve resources from the origin server.

## Calculate the time-to-live \(TTL\) value for a cached object

-   t = \(Current time - Last-Modified\) × 0.1
-   t = max\(10, t\)
-   t = min\(t, 3,600\)

The TTL value is represented by t and measured in seconds.

## Default caching rules

-   If the `Last-Modified` value of an object is `20140801 00:00:00` and the current time is `20140801 00:01:00`, t = \(Current time - Last-Modified\) × 0.1 = 6 seconds. Based on the calculation rules, the TTL value is 10 seconds because the minimum value is 10 seconds.
-   If the `Last-Modified` value of an object is `20140801 00:00:00` and the current time is `20140802 00:00:00`, t = \(Current time - Last-Modified\) × 0.1 = 8,640 seconds. Based on the calculation rules, the TTL value is 3,600 seconds because the maximum value is 3,600 seconds.
-   If the `Last-Modified` value of an object is `20140801 00:00:00` and the current time is `20140801 00:10:00`, t = \(Current time - Last-Modified\) × 0.1 = 60 seconds. Based on the calculation rules, the TTL value is 60 seconds.
-   If the response from the origin server does not contain the `Last-Modified` header but contains the `ETag` header, the retrieved object is more likely a static resource. The default TTL value for this object is set to the minimum value. You can use the `dft_expires` directive to configure the minimum value.
-   If the response from the origin server does not contain the `Last-Modified` or the `ETag` header, the retrieved object is a dynamic resource. The default TTL value for this object is set to 0. The object is retrieved from the origin server each time it is requested.

**Note:**

Website developers and IT engineers are more familiar with the business logic of, and the static and dynamic content on their websites. We recommend that you set the TTL values in the Alibaba Cloud CDN console based on the file types and directories. For more information, see [Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md).

## References

Alibaba Cloud CDN supports the following caching features.

|Feature|Description|
|-------|-----------|
|[Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md)|Allows you to configure cache expiration rules for static resources in a specified directory or with specified file extensions. In each cache expiration rule, you can set the TTL value of the cached static resources and the priority. Based on these cache expiration rules, Alibaba Cloud CDN caches the specified static resources on CDN nodes.|
|[Create a TTL rule for HTTP status codes](/intl.en-US/Domain Management/Cache settings/Create a TTL rule for HTTP status codes.md)|Allows you to configure expiration rules for HTTP status codes that are returned for resources in a specified directory or with specified file extensions.|
|[Create an HTTP header](/intl.en-US/Domain Management/Cache settings/Create an HTTP header.md)|Allows you to customize HTTP response headers.|
|[Customize an error page](/intl.en-US/Domain Management/Cache settings/Customize an error page.md)|Allows you to customize an error page for a specific HTTP or HTTPS status code.|
|[Configure a rewrite rule](/intl.en-US/Domain Management/Cache settings/Configure a rewrite rule.md)|Allows you to rewrite requested URIs and redirect the requests to the specified URIs by using 302 redirects.|

