# Overview

This topic describes how to get started with Alibaba Cloud Content Delivery Network \(CDN\) and the relevant scenarios.

The following figure shows how to get started with Alibaba Cloud CDN.

![Quick start](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6759177951/p54964.png)

The following table illustrates the steps for quick start.

|No.|Step|Scenario|
|---|----|--------|
|1|[Activate the CDN service](/intl.en-US/Quick Start/Activate the CDN service.md)|Before you use the features provided by Alibaba Cloud CDN, you must activate the Alibaba Cloud CDN service.|
|2|[Add a domain](/intl.en-US/Quick Start/Add a domain.md)|If you need to use Alibaba Cloud CDN to accelerate the delivery of content on a specific website, you must specify the website as the origin, and create an accelerated domain for the origin. By using the accelerated domain, Alibaba Cloud CDN caches the content from the origin to a CDN node to accelerate content delivery.|
|3|Configure a canonical name \(CNAME\) record -   [Configure a CNAME record in Alibaba Cloud DNS](/intl.en-US/Quick Start/Configure a CNAME record/Configure a CNAME record in Alibaba Cloud DNS.md)
-   [Configure a CNAME on Tencent Cloud \(DNSPod\)](/intl.en-US/Quick Start/Configure a CNAME record/Configure a CNAME on Tencent Cloud (DNSPod).md)
-   [Configure a CNAME record on Xinnet](/intl.en-US/Quick Start/Configure a CNAME record/Configure a CNAME record on Xinnet.md)

|After you create the accelerated domain, Alibaba Cloud CDN team will assign the corresponding CNAME to the accelerated domain. To enable the CDN service, you must add a CNAME record to the DNS records of the accelerated domain to map the accelerated domain to the CNAME. In this way, requests for the accelerated domain can be sent to a CDN node. You can configure a CNAME record with multiple Domain Name System \(DNS\) hosting providers. Select a DNS hosting provider as needed.|
|4|[Stop the CDN service](/intl.en-US/Quick Start/Stop the CDN service.md)|If you no longer need the Alibaba Cloud CDN service, you can delete the specified accelerated domain name in the Alibaba Cloud CDN console. After the accelerated domain name is deleted, no charges will be incurred.|

