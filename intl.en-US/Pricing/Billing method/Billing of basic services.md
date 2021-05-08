---
keyword: [CDN pricing, CDN billing rules]
---

# Billing of basic services

This topic describes the metering methods of and considerations for basic services of Alibaba Cloud Content Delivery Network \(CDN\).

## Purchase basic services of Alibaba Cloud CDN

Beginning January 8, 2021, Alibaba Cloud Content Delivery Network \(CDN\) uses the pay-by-data-transfer metering method by default. After Alibaba Cloud CDN is activated, the metering method cannot be changed in the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com). To change to the pay-by-bandwidth metering method, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) or contact your sales manager. For more information, see [CDN Pricing](https://www.alibabacloud.com/product/cdn/pricing).

## Purchase data transfer plans

Alibaba Cloud CDN supports data transfer plans. For more information, see [CDN Resource Plan](https://common-buy-intl.aliyun.com/?commodityCode=%20cdn_bag_intl#/buy).

**Note:**

-   Regions outside mainland China are divided into the following billable regions based on the location where the CDN nodes are deployed: North America, Europe, Asia Pacific 1, Asia Pacific 2, Asia Pacific 3, Middle East, Africa, and South America.
-   If your workloads are deployed in different regions, you must purchase data transfer plans that can be used in these regions.

## Pay-by-data-transfer

Description: You are charged for the amount of daily outbound data transfer of CDN nodes based on tiered pricing strategies.

Applicable scenarios: The network traffic fluctuates and the bandwidth usage spikes. The daily bandwidth usage is lower than 30%.

How to purchase: Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com) and make a purchase.

## Pay-by-bandwidth

Description: You are charged based on daily peak bandwidth values. A bandwidth value is collected every 5 minutes. A total of 288 values are collected every day. The highest bandwidth value is the daily peak bandwidth value.

Applicable scenarios: The network traffic is relatively flat and the daily bandwidth usage exceeds 30%.

How to purchase: If you want to use the pay-by-bandwidth metering method and the peak bandwidth value within the last 30 days exceeds 5 Gbit/s, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) or contact your sales manager. Alibaba Cloud determines whether to approve your application based on factors such as service security and resource quotas. After your application is approved, you can make a purchase in the Alibaba Cloud CDN console.

## Considerations

The amount of data transfer that is actually billed is higher than the amount of data transfer recorded in logs. The amount of data transfer recorded in CDN logs equals the amount of data transfer captured at the application layer. However, an extra amount of data is consumed to transmit the additional bytes inserted to TCP or IP packet headers and to retransmit TCP packets. Therefore, the actual amount of data transfer is higher than the amount of data transfer captured at the application layer. For more information, see [Why is the actual billed network traffic different from the network traffic reported by the logging feature?]()

