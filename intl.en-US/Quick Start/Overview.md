# Overview {#concept_nwf_psv_tdb .concept}

This topic helps you to quickly learn the operation process and scenarios when you use CDN for the first time.

The following figure shows how to get quickly started with CDN.

![Quick start](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5111/156535316453084_en-US.png)

The following table describes how to get quickly started with CDN.

|No.|Procedure|Scenario|
|---|---------|--------|
|1|[Activate CDN](intl.en-US/Quick Start/Activate CDN.md#)|Before you use the features provided by CDN, you must activate the CDN service.|
|2|[Add a CDN domain](intl.en-US/Quick Start/Add a CDN domain.md#)|If you want to use CDN to accelerate content on a specific website, you need to use the website as the origin site to add a CDN domain for it. CDN caches resources on the origin site to the CDN acceleration node through the CDN domain to accelerate resource access.|
|3|Configure a CNAME record -   [Configure a CNAME on Alibaba Cloud \(HiCloud\)](intl.en-US/Quick Start/Configure a CNAME record/Configure a CNAME on Alibaba Cloud (HiCloud).md#)
-   [Configure a CNAME on Tencent Cloud \(DNSPod\)](intl.en-US/Quick Start/Configure a CNAME record/Configure a CNAME on Tencent Cloud (DNSPod).md#)
-   [Configure a CNAME on Xinnet](intl.en-US/Quick Start/Configure a CNAME record/Configure a CNAME on Xinnet.md#)

 |After the CDN domain is added, CDN will assign the corresponding CNAME address to the domain. If you need to enable the CDN domain, you must configure the CNAME record on the origin site. As a result, requests destined for the CDN domain can be forwarded to the CDN node. How to configure a CNAME record varies by website. Select a method as needed.|

