# Implement acceleration from the CDN console {#task_996199 .task}

This topic describes how to implement CDN acceleration for the access to ECS instances from the CDN console.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, click **Add Domain Name**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/669802/156860470660439_en-US.png)

4.  Use an ECS instance as the origin, configure the CDN domain information, and select **IP** or **Origin Domain** as the origin type. 

    |Parameter|Description|
    |:--------|:----------|
    |**Domain Name**|Enter a domain name, for example, ch.aliyun.com.|
    |**Business Type**|Content delivery varies by business type. Select the appropriate business type based on your stored content and usage.     -   [Image and Small File](reseller.en-US/Product Introduction/Scenarios/Images and small files.md#)
    -   [Large File Download](reseller.en-US/Product Introduction/Scenarios/Images and small files.md#)
    -   [VOD](reseller.en-US/Product Introduction/Scenarios/VOD.md#)
    -   [Live Streaming](../reseller.en-US/Product Introduction/Scenarios/Live Streaming.md#)
 |
    |**Origin Info**|Select the OSS bucket domain for which you want to accelerate the content delivery.     -   OSS Domain
    -   IP
    -   Origin Domain
    -   FC Domain
 |
    |**Port**|Select an access port as needed.     -   80
    -   443
 |
    |**Region**|Select the region to be accelerated based on your business requirements.     -   Mainland China
    -   All Regions Including Mainland China
    -   All Regions Excluding Mainland China
 |

5.  Click **Next**, and wait for the approval of the manual review.
6.  After the CDN domain is approved, the CDN domain is displayed in the **Domain Names** list, and the status is displayed as **Enabled**. 

    After a CDN domain is added, a CNAME is automatically generated. For the CDN service to take effect for the domain, you must add a CNAME record at your DNS service provider. For more information, see [Configure a CNAME record on Alibaba Cloud DNS \(HiChina\)](../reseller.en-US/Quick Start/Configure a CNAME record/Configure a CNAME record on Alibaba Cloud DNS (HiChina).md#), [Configure a CNAME on Tencent Cloud \(DNSPod\)](../reseller.en-US/Quick Start/Configure a CNAME record/[DO NOT TRANSLATE].md#), or [Configure a CNAME on Xinnet](../reseller.en-US/Quick Start/Configure a CNAME record/[DO NOT TRANSLATE].md#).


