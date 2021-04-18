# Pay by traffic

Alibaba Cloud Content Delivery Network \(CDN\) supports the pay by traffic billing method. This billing method calculates fees based on the amount of outbound traffic from CDN nodes. Use Alibaba Cloud CDN based on your actual workload requirements.

## Alibaba Cloud CDN provides resource plans

Alibaba Cloud CDN provides resource plans. For more information, see [CDN Resource Plan](https://common-buy-intl.aliyun.com/?commodityCode=%20cdn_bag_intl#/buy).

![Banner](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6690011061/p65851.png)

## Subscription

Alibaba Cloud CDN provides cost-effective resource plans to pay for outbound traffic. For more information about resource plans, see [CDN pricing](https://common-buy-intl.aliyun.com/?commodityCode=%20cdn_bag_intl#/buy).

## Pay-as-you-go

The pay-as-you-go billing method has the following rules:

-   Billing item: traffic
-   Billing method: pay-as-you-go.
-   Billing rule: You are billed based on the amount of generated network traffic in each region \(inside and outside mainland China\). Billing is based on different pricing tiers. The amount that exceeds the current pricing tier is billed based on the next pricing tier. The calculation cycle is one calendar month.
-   Billing cycle: Billed on an hourly basis and the fees are deducted in real time.
-   Conversion Formula: 1 GB = 1,024 MB.
-   Release schedule of bills: A bill is issued at the end of the current billing cycle. The bill is typically issued within three hours after the end of the current billing cycle, which is subject to the actual system billing time. The amount due is then automatically deducted from your account balance.

For more information about pay by traffic, see [CDN pricing](https://www.alibabacloud.com/zh/product/cdn/pricing?spm=a2796.7980202.1167822.1.16755f45tSDVja).

**Note:** The upper bandwidth limit of pay by traffic is set to 10 Gbit/s by default. If the actual peak bandwidth of your workloads is higher than 10 Gbit/s, choose the pay by bandwidth billing method, or submit a ticket.

## Considerations

The amount of data that is actually charged is higher than the amount of data recorded in logs. The amount of data recorded in CDN logs equals the amount of data captured at the application layer. However, an extra amount of data is consumed to transmit the additional bytes inserted to TCP/IP packet headers and to retransmit TCP packets. Therefore, the actual amount of data is higher than the amount of data captured at the application layer. For more information, see [Differences between billed data transfer and data transfer recorded in logs]().

