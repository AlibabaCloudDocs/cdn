# Overview

Alibaba Cloud Content Delivery Network \(CDN\) supports the EdgeScript \(ES\) feature. This feature allows you to customize your CDN service by running scripts if the standard configurations in the Alibaba Cloud CDN console cannot meet your business requirements.

ES supports easy-to-learn syntax and provides a large library of functions. You can use the syntax and functions to customize CDN features.

![4](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4160738161/p255418.png)

ES provides encapsulated functions, simple decision making statements, and built-in variables that can be recognized by CDN nodes. Alibaba Cloud CDN invokes functions based on specified variables. This allows you to customize features such as authentication, caching, throttling, adding request headers, and deleting request headers. ES is an agile service that helps you customize CDN features based on your business requirements.

![7](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4630738161/p255500.png)

-   For more information about variables, see [EdgeScript built-in variables](/intl.en-US/EdgeScript/EdgeScript built-in variables.md).
-   For more information about functions, see [EdgeScript built-in functions](https://help.aliyun.com/document_detail/126869.html?spm=a2c4g.11186623.6.730.d7aa4d674Q9xAO).
-   For more information about logical functions, see [Logical functions](/intl.en-US/EdgeScript/EdgeScript built-in functions/Logical functions.md).

## Billing

ES is free of charge.

## Scenarios

|Scenario|Description|
|--------|-----------|
|Customize authentication logic|Authentication logic customization is commonly required by hotlink protection for on-demand video streaming and live streaming. ES allows you to customize authentication logic to authenticate requests based on parameters, cookies, or algorithms. Authentication reinforces protection for resources on your origin server.|
|Customize request and response headers|ES allows you to modify request and response headers based on your business requirements.|
|Rewrite and redirect requests|If your website supports different languages, requests destined for the website are redirected to the URLs that point to content written in the requested language. For example, requests that require the English or German language are redirected from the China site to the English or German site.|
|A/B Test|Before you release a new feature, you can use Alibaba Cloud CDN to run A/B tests. You can send requests that carry different request headers or URLs to different origin servers. These requests trigger different features on the origin servers.|
|Customize caching|If the standard time-to-live \(TTL\) values or cache expiration rules for cached content cannot meet your business requirements in certain scenarios, you can run scripts to create custom caching rules.|
|Throttle requests|ES allows you to throttle requests from different users, such as free users and paying users. You can run scripts to configure and enable throttling.|
|Block requests|ES allows you to run scripts to block requests from specified IP addresses. You can specify the regions or logic based on which requests are blocked. You can also create anti-bot policies to protect your resources from bots.|

