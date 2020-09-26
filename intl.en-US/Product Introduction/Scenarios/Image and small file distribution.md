---
keyword: [Image and small file distribution, Static content]
---

# Image and small file distribution

If your service involves the distribution of small static web pages or application files, such as image files, HTML files, flash files, CSS files, and JavaScript files, you can select the Image and Small File workload type to accelerate the distribution.

## Scenario

The Image and Small File workload type is suitable for accelerating the distribution of a large number of static resources on websites and applications. Examples of the websites and applications include web portals, e-commerce websites, news websites and applications, and gaming and other entertainment websites. You can separate static and dynamic content. To accelerate the distribution of static content, such as images, small CSS files, and small JavaScript files, we recommend that you use Alibaba Cloud CDN. To accelerate resource loading and distribution of images and short videos on websites, we recommend that you use Alibaba Cloud CDN together with Object Storage Service \(OSS\).

The following figure shows a typical architecture where Alibaba Cloud CDN is used to accelerate the distribution of images and small files.

![Image and small file distribution](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5388901061/p75529.png)

## Issues resolved

-   Websites respond slowly because they contain a large number of small files.
-   The web page load speed and the quality of web services differ across regions. If you send requests for cross-region data access, the websites may respond slowly.
-   During the promotion period, origin servers are more likely to break down due to heavy traffic and high concurrency. The services may become unavailable.
-   Images cannot be compressed or optimized to meet client requirements for image formats and resolution.

## Required Alibaba Cloud products and features

The following table describes Alibaba Cloud products and features that are required to accelerate the distribution of images and small files.

|Product or feature|Description|
|------------------|-----------|
|[Node distribution](/intl.en-US/Product Introduction/Node distribution.md)|Alibaba Cloud CDN has deployed more than 2,800 nodes across the world. The throughput of the entire content delivery network reaches up to 130 Tbit/s. Alibaba Cloud CDN serves major network service providers around the world.|
|Intelligent scheduling|Alibaba Cloud CDN uses an advanced distributed system to schedule requests in all regions and respond to requests within several milliseconds.|
|Elasticity|Alibaba Cloud CDN nodes can automatically respond to requests and reduce workloads on origin servers. You are billed for the service on a pay-as-you-go basis, which helps you save costs.|
|[Intelligent compression](/intl.en-US/Domain Management/Performance optimization/Configure intelligent compression.md)|Alibaba Cloud CDN can compress images in various formats without compromising the quality, and adjust images to fit a wide range of clients to improve overall performance.|

## Related operations

Before you select a workload type for your domain name for CDN in the Alibaba Cloud CDN console, make sure that you have full knowledge about the application scenarios of different workload types. For more information, see [Add a domain](/intl.en-US/Quick Start/Add a domain.md).

