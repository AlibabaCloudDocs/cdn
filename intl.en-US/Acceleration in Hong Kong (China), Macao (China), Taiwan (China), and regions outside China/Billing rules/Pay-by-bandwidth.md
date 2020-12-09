# Pay-by-bandwidth

Alibaba Cloud Content Delivery Network \(CDN\) supports the pay-by-bandwidth metering method. This topic describes the pay-by-bandwidth metering method.

## Pay-as-you-go

The pay-by-bandwidth metering method has the following rules:

-   Billable item: peak bandwidth values.
-   Billing method: pay-as-you-go.
-   Billing rule: you are billed based on the peak bandwidth values in each region. Billing is based on different tiers.
-   Billing cycle: you are billed on a daily basis and the fees are deducted in real time.
-   Issue schedule of bills: A bill is issued at the end of the current billing cycle \(calendar days\).

    The bill of the current day is issued after 00:00:00 \(UTC+8\) on the following day. The time when bills are issued is typically three hours after the billing cycle ends. The system determines the time to issue bills. For example, the bill of June 17 is issued around 03:00:00 \(UTC+8\) on June 18. After a bill is issued, the fees are automatically deducted from your account balance.


For more information about the pay-by-bandwidth metering method, see [CDN Pricing](https://www.alibabacloud.com/product/cdn/pricing).

**Note:** The pay-by-bandwidth metering method bills bandwidth usage based on the daily peak bandwidth values \(Mbit/s\) reached by CDN nodes that are deployed inside and outside mainland China separately.

