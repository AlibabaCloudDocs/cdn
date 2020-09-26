# Overview

You can analyze log data of Alibaba Cloud Content Delivery Network \(CDN\) to locate and resolve issues. This improves the overall performance of your CDN service. This topic describes the log management features of Alibaba Cloud CDN and the related services.

## Log management features

Alibaba Cloud CDN supports the following log management features:

|Feature|Description|
|-------|-----------|
|[Download logs](/intl.en-US/Service Management/Log Management/Download logs.md)|You can query log data within the specified time range or for a specified domain name, and then download the log data.|
|[Log storage](/intl.en-US/Service Management/Log Management/Log storage.md)|By default, Alibaba Cloud CDN retains log data for up to one month. To retain log data for a longer period of time, import the log data to Object Storage Service \(OSS\). This allows you to analyze the log data at any time.|

## Related services

The log management features of Alibaba Cloud CDN can be integrated with the following services:

-   Function Compute

    Function Compute supports various events for CDN. You can use Function Compute events to import log data of Alibaba Cloud CDN to another service, refresh and prefetch content, add domain names to be accelerated, delete accelerated domain names, enables domain names, and disables domain names. For more information about how these events are triggered, see [CDN event triggers](https://www.alibabacloud.com/help/zh/doc-detail/73333.htm).

    For more information about Function Compute, see [What is Function Compute](https://www.alibabacloud.com/help/zh/doc-detail/52895.htm).

-   Object Storage Service \(OSS\)

    For more information about OSS, see [What is OSS?](/intl.en-US/Product Introduction/What is OSS?.md)


