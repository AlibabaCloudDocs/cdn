# Overview {#concept_744832 .concept}

If CDN wants to accelerate static resource delivery, it loads the resources on an origin site to the CDN node that is closest to the visitor. When the visitor wants to access the static resources, CDN retrieves the resources from the CDN node instead of retrieving the resources from the origin site, which is time-consuming. This reduces the resource delivery time.

CDN supports the following cache functions.

|Function|Description|
|--------|-----------|
|[Create a cache expiration rule](reseller.en-US/Domain Management/Cache settings/Create a cache expiration rule.md#)|Allows you to configure the time to live \(TTL\) of static resources in a specified directory or with a specified file extension, and specify their caching priority. CDN then caches the specified static resources based on their priority.|
|[Set status code expiration time](reseller.en-US/Domain Management/Cache settings/Set status code expiration time.md#)|Allows you to configure the TTL of error responses for resources in a specified directory or with a specified file extension.|
|[Create an HTTP header](reseller.en-US/Domain Management/Cache settings/Create an HTTP header.md#)|Allows you to customize HTTP response header fields.|
|[Customize an error page](reseller.en-US/Domain Management/Cache settings/Customize an error page.md#)|Allows you to specify a custom error page for specific HTTP or HTTPS status codes.|
|[Configure a rewrite rule](reseller.en-US/Domain Management/Cache settings/Configure a rewrite rule.md#)|Allows you to redirect request URIs to specified URIs by using 302 redirect.|

