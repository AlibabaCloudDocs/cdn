# Overview

Alibaba Cloud Content Delivery Network \(CDN\) supports the pay-by-data-transfer and pay-by-bandwidth billing methods in accelerated regions outside mainland China. This topic describes these two billing methods.

## Purchase guide

When you activate Alibaba Cloud CDN, you can select pay-by-data-transfer or pay-by-bandwidth. For more information about pricing, see [CDN pricing](https://www.alibabacloud.com/product/cdn/pricing).

## Billing methods

|Billing method|Description|Scenario|
|:-------------|:----------|:-------|
|[Pay by traffic](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Billing rules/Pay by traffic.md)|You are charged for the basic services of Alibaba Cloud CDN based on the amount of daily outbound data of CDN nodes.|Your traffic curve shows large fluctuations and bandwidth spikes. The daily bandwidth usage is lower than 30%.|
|[Pay-by-bandwidth](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Billing rules/Pay-by-bandwidth.md)|You are charged for the basic services of Alibaba Cloud CDN based on the daily peak bandwidth values. A bandwidth value is collected every 5 minutes. 288 values are collected every day. The greatest bandwidth value is used as the daily peak bandwidth.|Your traffic curve is relatively flat, and the daily bandwidth usage exceeds 30%.|

**Note:**

-   The bandwidth usage is calculated based on the following formula: Bandwidth usage = Data usage \(GB\)/\[Peak bandwidth \(Mbit/s\) × 10.54\]. If the bandwidth is 1 Mbit/s and the daily bandwidth usage is 100%, the data usage is 10.54 GB.
-   You are charged for only the outbound data from CDN nodes.
-   Alibaba Cloud CDN retains logs within the last three months. If you have questions about the logs or bills, submit an application before the log data expires to check the billing statements with Alibaba Cloud. Expired log data is released and cannot be restored. Billing statements of expired log data is not provided.

## Usage notes

The data transfer that is actually billed is higher than the data transfer recorded in logs. The amount of data recorded in CDN logs equals the amount of data captured at the application layer. However, an extra amount of data is consumed to transmit the additional bytes inserted to TCP/IP packet headers and to retransmit TCP packets. Therefore, the actual amount of data is higher than the amount of data captured at the application layer. For more information, see [Why is the actual billed network traffic different from the network traffic reported by the logging feature?]().

