---
keyword: [large file delivery, static content]
---

# Delivery of large files

If your business supports delivery of large static files hosted on websites or applications, you can use Alibaba Cloud Content Delivery Network \(CDN\) to accelerate the delivery of large files. Examples of large files include `APK` game installation files, `RAR` application update files, patch files, audio files, and video files.

## Scenarios

Acceleration of large file delivery is suitable for downloading and delivering files that are greater than 20 MB. We recommend that you use Alibaba Cloud CDN together with Object Storage Service \(OSS\) to accelerate the back-to-origin process. This can save up to two-thirds of the back-to-origin bandwidth costs.

The following figure shows how the delivery of large files is accelerated by Alibaba Cloud CDN.

![Delivery of large files](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7329901061/p75328.png)

## Problems solved

Acceleration of large file delivery can address the following issues:

-   Users cannot download files, or the download speed is low.
-   Downloads are easily interrupted when network connections are unstable. Extra resources are consumed to download the resources again.
-   Website content is exposed to potential risks and vulnerable to hijacking attacks.
-   File storage costs and performance requirements for the origin server are high.

## Related services and features

The following table lists the services and features that are required for solving the preceding issues.

|Service or feature|Description|
|------------------|-----------|
|[OSS](/intl.en-US/Product Introduction/What is OSS?.md)|You can integrate Alibaba Cloud CDN with OSS to accelerate access to resources. This way, you can retrieve content directly from CDN nodes to reduce the costs of Internet data transfer and ensure the high availability of the origin server.|
|[Resumable upload](/intl.en-US/Developer Guide/Objects/Upload files/Multipart upload and resumable upload.md)|This feature resumes uploads on the client side over all types of protocols. This reduces the consumption of downstream bandwidth resources.|
|[HTTPS secure acceleration](/intl.en-US/Domain Management/HTTPS/Overview.md)|This feature supports a variety of authentication methods to prevent link hijacking.|

## Related operations

Before you select a workload type for your domain name for CDN in the Alibaba Cloud CDN console, make sure that you have full knowledge about the application scenarios of different workload types. For more information, see [Add a domain name to Alibaba Cloud CDN](/intl.en-US/Quick Start/Add a domain name to Alibaba Cloud CDN.md).

