---
keyword: [cache policy, TTL values of cached resources, CDN]
---

# Configure a cache expiration rule

Alibaba Cloud Content Delivery Network \(CDN\) intelligently caches resources on CDN nodes. This allows users to retrieve resources from the nearest CDN nodes. If you use Alibaba Cloud CDN to accelerate the delivery of static content and do not set an appropriate time-to-live \(TTL\) value for the cached content, Alibaba Cloud CDN frequently redirects requests to origin servers. In this case, the amount of data transfer on the origin servers is increased, and data transfer fees are also increased. We recommend that you set an appropriate TTL value for static content cached on CDN nodes based on your business requirements. You do not need to set a TTL value for dynamic content because dynamic content is retrieved from origin servers in real time. If you set an inappropriate TTL value, the number of requests that are redirected to origin servers increases, and content delivery cannot be accelerated as expected.

## Cache policy parameters

Alibaba Cloud CDN is intended for accelerating the delivery of static content. Dynamic content is retrieved from origin servers in real time, instead of cached on CDN nodes. You can set a TTL value for cached resources based on the file types and update frequency. The maximum TTL value that you can set is three years. For more information, see [Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md).

|File type|Update frequency|TTL value|Example|
|---------|----------------|---------|-------|
|Static files|Less frequently updated|One month or longer|Images and application packages|
|Static files|Frequently updated|Based on business requirements|JS and CSS files|
|Dynamic files|N/A|Zero seconds, which indicates that dynamic content is not cached on CDN nodes|PHP, JSP, and ASP files|

## References

If the cache hit ratio is lower than expected after you use Alibaba Cloud CDN to accelerate content delivery for a domain name, you can configure and enable the prefetch feature. This feature can prefetch content from origin servers to CDN nodes during off-peak hours. For more information, see [Configure the refresh and prefetch features](/intl.en-US/Service Management/Refresh and prefetch/Configure the refresh and prefetch features.md).

