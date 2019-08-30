# FAQ {#concept_371543 .concept}

-   [Why am I still being charged after my CDN is suspended?](#section_o69_4e5_r87)
-   [What is 95th percentile bandwidth billing?](#section_6xd_ewl_qey)
-   [How is the traffic billed when CDN nodes retrieve resources from OSS?](#section_vqv_h1w_oo2)
-   [If the origin server is located outside Mainland China, how is the acceleration service of CDN nodes in Mainland China billed?](#section_3ue_eo2_rt1)
-   [Why cannot my traffic package be used to offset traffic fees?](#section_bcn_0d3_inu)
-   [What is the difference between billed traffic and log monitoring traffic?](#section_zxj_ldg_kh1)
-   [What is the preferential usage order of CDN or DCDN resource packages?](#section_4x3_ouz_srr)
-   [How to view the usage of HTTPS requests?](#section_xop_rhg_23w)

## Why am I still being charged after my CDN is suspended? {#section_o69_4e5_r87 .section}

-   If your local DNS server has caches that have not expired, domain name resolution requests will be sent to your local DNS server even after your CDN is suspended. This will consume a small amount of traffic.
-   Some types of downloading software also have a local DNS cache. Before the cache expires, resolution requests for disabled domain names will still be sent to the local DNS server. This will consume a small amount of traffic.

## What is 95th percentile bandwidth billing? {#section_6xd_ewl_qey .section}

-   95th percentile bandwidth billing is only applicable to users who spend more than CNY 100,000 on CDN per month. This monthly billing method is more flexible. To use this billing method, you can directly contact Alibaba Cloud.
-   Billing item: 95th percentile bandwidth

    **Note:** 

    -   95th percentile bandwidth billing is based on each calendar month. During each calendar month, effective bandwidth values collected every five minutes are sorted in descending order. Then, the top 5% of these values are discarded. The highest one of the remaining values is considered as the 95th percentile bandwidth value and is billable. For example, a month has 30 days. A data point is collected every five minutes. 12 data points are collected every hour. 8,640 data points are collected every month. All these data points are sorted in descending order. The highest 5% of 8,640 data points \(432 data points\) are discarded. The 433rd data point is billable.
    -   The 95th percentile bandwidths for accounts in Mainland China and outside Mainland China are calculated separately. Bandwidth values for both accounts in Mainland China and outside Mainland China are sorted in descending order. Their 95th percentile bandwidth values are collected and billed.
-   Billing rules

    -   Billing method: pay-as-you-go.
    -   Billing rule: Tiered pricing applies to the 95th percentile bandwidth. The fees for accounts in Mainland China and outside Mainland China are separately accumulated on a calendar month basis.
    -   Billing cycle: a calendar month.
    -   Valid days: If you change the billing method to 95th percentile bandwidth billing within the billing cycle, the valid days indicate the number of days from the day when 95th percentile bandwidth billing takes effect to the end of the month. For example, if 95th percentile bandwidth billing took effect on April 5, 2016, the bill for April 2016 contains 26 valid days.
    -   Effective factor: the ratio between the number of valid days in a calendar month and the total number of days in a calendar month. For example, the bill for April 2016 contains 26 valid days. The effective factor of this month is 0.86666667.
    -   Final fees: To obtain the final fees, you can multiply the fees calculated based on the billing rule by the effective factor.
    **Note:** 

    -   Issuing time of bills: When a billing cycle ends, a bill will be issued in the early morning on the first day of the next calendar month. For example, the February bill for the 95th percentile bandwidth consumed from 2017-02-01 00:00:00 to 2017-02-28 23:59:59 was issued on March 1.
    -   Settlement time: After bills are issued on the first day of each calendar month, fees are deducted from your account automatically. Make sure that you have enough balance in your account when bills are issued and payments are settled. For more information, see [Overdue payments](reseller.en-US/Pricing/Overdue payments.md#). You can go to the [Usage page of the CDN console](https://cdn.console.aliyun.com/?spm=a2c4g.11186623.2.8.d76365a8u9GLOM#/usage/usageQuery) to view the 95th percentile bandwidth for the current month and estimate how much it will cost.
    -   The effective time of a new billing method:
        -   When you change the billing method from PayByTraffic or PayByBandwidth to 95th percentile bandwidth billing, the new billing method will take effect at 00:00 on the next day.
        -   When you change the billing method from 95th percentile bandwidth billing to PayByTraffic or PayByBandwidth, the new billing method will take effect at 00:00 on the first day of the next calendar month. You cannot change the billing method again within the month. For more information, see [CDN pricing](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.9.d76365a8u9GLOM#/cdn/detail).

## How is the traffic billed when CDN nodes retrieve resources from OSS? {#section_vqv_h1w_oo2 .section}

Only outbound traffic from CDN nodes and OSS is billed. Therefore, the service from which the traffic flows is billed. When CDN nodes retrieve resources from OSS, traffic flows from OSS to CDN. Therefore, the traffic is billed on OSS. For more information about OSS billing methods, see [Billing items](../../../../reseller.en-US/Pricing/Billing items.md#).

![](images/47996_en-US.png)

## If the origin server is located outside Mainland China, how is the acceleration service of CDN nodes in Mainland China billed? {#section_3ue_eo2_rt1 .section}

Only outbound traffic from CDN nodes is billed. If you select Mainland China as the acceleration region, and the origin server is located outside Mainland China, the acceleration service of CDN nodes is billed based on the pricing standard in Mainland China.

## Why cannot my traffic package be used to offset traffic fees? {#section_bcn_0d3_inu .section}

-   Billing methods

    A CDN traffic package is only used to offset traffic fees when you select PayByTraffic. If you select PayByBandwidth, you cannot use your CDN traffic package to offset traffic fees.

-   Value-added service fees

    If you purchase CDN or DCDN resource packages and select PayByTraffic, charges may still incur. In this case, check whether value-added services are enabled, such as HTTPS, real-time logging, or pornographic image detection. Value-added services are billed on the PayByTraffic basis. The system automatically deducts fees from your account balance. You can purchase a resource package. For more information, see [Value-added service billing](reseller.en-US/Pricing/Billing method/Value-added service billing.md#).

-   Fees for CDN nodes outside Mainland China

    CDN nodes outside Mainland China are billed on the PayByTraffic basis. If you select All Regions Excluding Mainland China or All Regions Including Mainland China as acceleration regions, select appropriate regions when you purchase downstream traffic packages. For more information about the pricing of CDN nodes outside Mainland China, see [CDN pricing](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail).


## What is the difference between billed traffic and log monitoring traffic? {#section_zxj_ldg_kh1 .section}

Log monitoring traffic indicates the traffic data recorded in the logs. The actual network traffic is 7% to 15% higher than the traffic measured at the application layer due to the following reasons:

-   Traffic consumption of TCP/IP headers

    HTTP requests are based on TCP/IP. The maximum size of each packet is 1,500 bytes, including 40-byte headers of TCP/IP. TCP/IP headers consume traffic. The operation of adding headers is performed by the protocol stack in the kernel. Therefore, the traffic consumed by headers cannot be measured by the application layer and cannot be recorded in logs. The traffic accounts for more than 2.74% \(40/1,460\) of the traffic measured by logs. In most cases, that ratio is about 3%.

-   TCP retransmission

    Under normal circumstances, 3% to 10% of the packets sent will be discarded over the Internet based on the load condition of the physical network. Servers will retransmit these discarded packets. Retransmission is performed by the protocol stack in the kernel. Therefore, the retransmission traffic cannot be measured by the application layer. The ratio between the retransmission traffic and the traffic measured in logs depends on the network quality. The ratio is low when the Internet load is light. In the case of heavy Internet load, the ratio will rise, ranging between 3% and 7%.


Therefore, 7% to 15% of network consumption \(based on industry standards\) is added to the original traffic and the average value of 10% is used. The combined traffic is billed.

## What is the preferential usage order of CDN or DCDN resource packages? {#section_4x3_ouz_srr .section}

-   CDN or DCDN resource packages can only be used when you select PayByTraffic.
-   The preferential usage order of multiple CDN or DCDN resource packages is to use the resource package that expires first.

**Note:** Before resource packages expire, consumed traffic is deducted from the resource packages on a daily basis. For the excess traffic, the PayByTraffic billing method is used.

## How to view the usage of HTTPS requests? {#section_xop_rhg_23w .section}

You can use the following methods to view the number of HTTPS requests:

-   Method 1
    1.  Log on to the [CDN console](https://cdnnext.console.aliyun.com).
    2.  On the Overview page, view the number of HTTPS requests.

        ![](http://icms-static-translation.oss-cn-hangzhou.aliyuncs.com/SP_19/DNCDN11855815/images/47999_zh-CN.png?Expires=1565342390&OSSAccessKeyId=LTAIJfoPL6wmrirR&Signature=iMGE4YiZYB6ZMK3F9bPcemjHHEk%3D)

-   Method 2
    1.  Log on to the [CDN console](https://cdnnext.console.aliyun.com).
    2.  In the left-side navigation pane, choose **Monitoring** \> **Resource Monitoring**.
    3.  On the Resource Monitoring page, click the Visits tab. You can view the number of HTTPS requests based on multiple dimensions such as domain, provider, and region.

        ![](http://icms-static-translation.oss-cn-hangzhou.aliyuncs.com/SP_19/DNCDN11855815/images/48000_zh-CN.png?Expires=1565342391&OSSAccessKeyId=LTAIJfoPL6wmrirR&Signature=sa4wLnvZ5UpxT%2Fx%2Bd94kv%2BDOU8w%3D)


