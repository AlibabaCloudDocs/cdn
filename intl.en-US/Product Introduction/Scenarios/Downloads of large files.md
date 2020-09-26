---
keyword: [downloads of large files, static content]
---

# Downloads of large files

If your business primarily supports delivery of large static files hosted on websites or application, such as `APK` game installation files, `RAR` application update files, patch files, and audio and video files, you can use Alibaba Cloud CDN to accelerate the downloads of large files.

## Scenarios

Acceleration of large file downloads is suitable for downloading and delivering files that are greater than 20 MB in a variety of formats. We recommend that you use Alibaba Cloud Content Delivery Network \(CDN\) together with Object Storage Service \(OSS\) to accelerate the back-to-origin process, which can save up to two-thirds of the back-to-origin bandwidth costs.

The following figure shows a typical scenario where downloads of large files are accelerated by Alibaba Cloud CDN.

![Downloads of large files](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7329901061/p75328.png)

## Issues resolved

-   End users cannot download files, or the download speed is low.
-   Downloads are easily interrupted when network connections are unstable. Extra resources are consumed to download the resources again.
-   Website content is insecure and vulnerable to hijacking attacks.
-   File storage costs and performance requirements for the origin server are high.

## Required Alibaba Cloud services and features

The following table lists the services and features that are required for solving the preceding issues.

|Service or feature|Benefit|
|------------------|-------|
|[Object Storage Service \(OSS\)](/intl.en-US/Product Introduction/What is OSS?.md)|You can integrate Alibaba Cloud CDN with OSS to accelerate access to websites. This way, you can retrieve content directly from CDN nodes to reduce the costs of Internet data transfer and ensures the high availability of origin servers.|
|[Resumable upload](/intl.en-US/Developer Guide/Objects/Upload files/Multipart upload and resumable upload.md)|This feature resumes uploads on the client side over all types of protocols. This reduces the consumption of downstream bandwidth resources.|
|[HTTPS secure acceleration](/intl.en-US/Domain Management/HTTPS/HTTPS secure acceleration overview.md)|This feature supports a variety of authentication methods to prevent link hijacking.|

## Related operations

Before you select a workload type for your domain name for CDN in the Alibaba Cloud CDN console, make sure that you have full knowledge about the application scenarios of different workload types. For more information, see [Add a domain](/intl.en-US/Quick Start/Add a domain.md).

