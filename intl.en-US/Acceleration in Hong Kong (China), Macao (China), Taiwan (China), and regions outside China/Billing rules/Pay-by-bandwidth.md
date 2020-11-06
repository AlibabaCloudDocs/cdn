# Pay-by-bandwidth

Alibaba Cloud Content Delivery Network \(CDN\) supports the pay-by-bandwidth billing method. This topic describes the pay-by-bandwidth billing method.

## Pay-as-you-go

The pay-as-you-go billing method has the following rules:

-   Billing item: peak bandwidth values
-   Billing method: pay-as-you-go.
-   Billing rule: you are billed based on the peak bandwidth values in each region. Billing is based on different tiers.
-   Billing cycle: billed on an hourly basis and the fees are deducted in real time.
-   Release schedule of bills: A bill is issued at the end of the current billing cycle \(calendar days\).

    The bill of the current day is issued after 00:00:00 \(UTC+8\) on the following day. The time when bills are issued is typically three hours after the billing cycle ends. The system determines the time to issue bills. For example, the bill of June 17 is issued around 03:00:00 \(UTC+8\) on June 18. After a bill is issued, the fees are automatically deducted from your account balance.


For more information about pay-by-bandwidth, see [CDN pricing](https://www.alibabacloud.com/zh/product/cdn/pricing?spm=a2796.7980202.1167822.1.16755f45tSDVja).

**Note:** The pay-by-peak bandwidth billing method indicates that you are billed based on the daily maximum bandwidth values \(Mbit/s\) reached by CDN nodes that are deployed inside and outside mainland China separately.

