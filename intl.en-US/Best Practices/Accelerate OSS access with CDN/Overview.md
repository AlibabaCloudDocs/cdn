# Overview {#concept_828189 .concept}

Alibaba Cloud allows you store static resources on OSS buckets and accelerate the access to the static resources through CDN. This topic describes the details about CDN-accelerated OSS access, including the background information, application scenarios, implementation methods, and related products.

## Background information {#section_8yf_3ua_9ui .section}

Alibaba Cloud CDN works with a precise scheduling system. Your requests for static resources are sent to the corresponding nearest CDN nodes, which allows you to retrieve the required resources as quickly as possible. In this way, the network congestion issues are resolved and the response speed for resource access is improved.

## Scenarios {#section_zy9_ibj_4hd .section}

Static resources stored on OSS buckets include static scripts, images, attachments, and audio or video content. When an end user accesses or downloads static resources that are stored on an OSS bucket, the delivery of the requested resources can be accelerated by CDN. CDN caches the resources on the origin \(OSS bucket\) to the nearest CDN node and automatically returns the requested resources from its cache. The following figure shows the architecture of CDN's accelerating access to resources on an OSS bucket.

![Architecture diagram](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/669798/156860449050521_en-US.png)

This architecture has the following benefits:

-   All user requests are responded through CDN, which minimizes the pressure on the origin server.
-   The CDN Internet traffic cost is lower than the OSS Internet traffic cost.
-   Resources are retrieved from the nearest CDN node to the client, which minimizes the network transmission distance and ensures the quality of static resources.

## How to implement CDN-based OSS access acceleration {#section_uuz_ysm_bwo .section}

For CDN to accelerate the access to an OSS bucket, use one of the following methods:

-   Map the bucket domain name to a CDN domain name, and bind a custom domain name to the CDN domain name. For more information, see [Implement acceleration from the CDN console](reseller.en-US/Best Practices/Accelerate OSS access with CDN/Implement acceleration from the CDN console.md#).
-   Bind the custom domain name to the bucket domain name and enable CDN acceleration. For more information, see [Implement acceleration from the OSS console](reseller.en-US/Best Practices/Accelerate OSS access with CDN/Implement acceleration from the OSS console.md#).

## Related products {#section_y26_vjp_vgq .section}

