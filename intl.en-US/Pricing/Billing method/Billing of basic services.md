---
keyword: [CDN pricing, CDN billing rules]
---

# Billing of basic services

This topic describes the metering methods of and considerations for basic services of Alibaba Cloud Content Delivery Network \(CDN\).

## Data transfer plans for Alibaba Cloud CDN

Alibaba Cloud CDN supports data transfer plans. For more information, see [CDN Resource Plan](https://common-buy-intl.aliyun.com/?commodityCode=%20cdn_bag_intl#/buy).

![Banner](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6690011061/p65851.png)

## Purchase basic services of Alibaba Cloud CDN

By default, basic services of Alibaba Cloud CDN use the pay-by-data-transfer metering method. To change to the pay-by-bandwidth metering method, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) or contact your sales manager. For more information about pay-by-data-transfer, see [CDN Pricing](https://www.alibabacloud.com/zh/product/cdn/pricing?spm=a2796.7980202.1167822.1.16755f45tSDVja).

## Metering methods

|Metering method|Description|Scenario|
|:--------------|:----------|--------|
|Pay-by-data-transfer|You are charged for basic services based on the amount of daily outbound data transfer of CDN nodes.|Your traffic curve shows large fluctuations and bandwidth spikes. The daily bandwidth usage is lower than 30%.|
|Pay-by-bandwidth|You are charged for basic services based on daily peak bandwidth values. A bandwidth value is collected every 5 minutes. A total of 288 values are collected every day. The highest bandwidth value is used as the daily peak bandwidth value.**Note:** To change to the pay-by-bandwidth metering method, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) or contact your sales manager.

|Your traffic curve is relatively flat and the daily bandwidth usage exceeds 30%.|
|Data transfer plans|You can make a one-off payment for a data transfer plan. The validity period of a data transfer plan is one year.|Data transfer plans support only the pay-by-data-transfer metering method. If the current metering method is pay-by-bandwidth, the remaining quota in the data transfer plan is suspended. The remaining quota is available only after you change the metering method to pay-by-data-transfer.|

**Note:**

-   The bandwidth usage is calculated based on the following formula: Bandwidth usage = Data transfer \(GB\)/\[Peak bandwidth \(Mbit/s\) × 10.54\]. If the bandwidth is 1 Mbit/s and the daily bandwidth usage is 100%, the data transfer is about 10.54 GB per day.
-   You are charged for basic services based on the amount of only outbound data transfer of CDN nodes.

## Considerations

The data transfer that is actually charged is higher than the data transfer recorded in logs. The amount of data transfer recorded in CDN logs equals the amount of data transfer captured at the application layer. However, an extra amount of data is consumed to transmit the additional bytes inserted to TCP or IP packet headers and to retransmit TCP packets. Therefore, the actual amount of data transfer is higher than the amount of data transfer captured at the application layer. For more information, see [Why is the actual billed network traffic different from the network traffic reported by the logging feature?]()

