# Overview {#concept_1062417 .concept}

Alibaba Cloud CDN can accelerate the delivery of static resources on ECS instances. Resources that can be stored on ECS instances include static resources and dynamic resources. If you access a dynamic resource on an ECS instance, the ECS instance directly returns the requested dynamic resource to you. If you access a static resource on an ECS instance, CDN accelerates your access and returns you the requested static resource from the cache on the CDN node. This topic describes the details about CDN-accelerated ECS access, including the background information, application scenarios, implementation methods, and related products.

## Background information {#section_e7n_975_ep6 .section}

Alibaba Cloud CDN works with a precise scheduling system. Your requests for static resources are sent to the corresponding nearest CDN nodes, which allows you to retrieve the required resources as quickly as possible. In this way, the network congestion issues are resolved and the response speed for resource access is improved.

## Scenarios {#section_5xq_foy_hqw .section}

Dynamic resources stored on ECS instances include Web programs and databases. Static resources include static scripts, images, attachments, and audio or video content. When you access or download a resource from an ECS instance that serves as the origin, the resource is directly returned to you if it is dynamic. If the requested resource is static, your access can be accelerated by CDN. CDN caches the resources on the ECS instance to the nearest CDN node and returns the requested resource from its cache. The following figure shows the architecture of CDN's accelerating access to resources on an ECS instance.

![Architecture diagram](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/855874/156860463951266_en-US.png)

**Note:** If you want to accelerate the delivery of dynamic resources on the ECS instance, you can use the Dynamic Route for CDN service. For more information, see [Dynamic Route for CDN documentation](https://help.aliyun.com/product/64812.html).

This architecture has the following benefits:

-   All user requests are responded through CDN, which minimizes the pressure on the origin server.
-   The CDN Internet traffic cost is lower than the ECS Internet traffic cost.
-   Resources are retrieved from the nearest CDN node to the client, which minimizes the network transmission distance and ensures the quality of static resources.

## How to implement CDN-based ECS access acceleration {#section_rcj_rmc_3iw .section}

For CDN to accelerate the delivery of resources on an ECS instance, you need to bind the domain name or IP address of the ECS instance to a CDN domain and enable CDN acceleration for the CDN domain. For more information, see [Implement acceleration from the CDN console](reseller.en-US/Best Practices/Accelerate ECS access with CDN/Implement acceleration from the CDN console.md#).

## Related products {#section_7pf_xpx_lg8 .section}

