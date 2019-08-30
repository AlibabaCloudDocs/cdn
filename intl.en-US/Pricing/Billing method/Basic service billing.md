# Basic service billing {#concept_m3l_kvl_zdb .concept}

This topic describes the billing methods of CDN basic services and related precautions.

CDN basic services have two billing options, including PayByTraffic and PayByBandwidth.

## Billing methods {#section_fcq_hh5_cgb .section}

|Billing method|Description|Scenario|
|:-------------|:----------|:-------|
|Peak bandwidth|CDN basic services are billed based on the daily peak bandwidth. A bandwidth value is calculated at five minute intervals. A total of 288 values can be obtained each day. The maximum value is used for billing purposes.|The CDN traffic curve is relatively flat, and the daily bandwidth utilization exceeds 30%.|
|Traffic|CDN basic services are billed based on the daily outbound traffic from CDN nodes.|Large fluctuations and bandwidth spikes exist in the CDN traffic curve. The daily bandwidth utilization is less than 30%.|

**Note:** 

-   Bandwidth utilization = Used traffic \(GB\)/\(Peak bandwidth \(Mbit/s\) × 10.54\). If the bandwidth is 1 Mbit/s and the daily bandwidth utilization is 100%, the generated traffic is 10.54 GB.
-   Only the outbound traffic \(downstream traffic\) from CDN nodes is billed.

## Precautions {#section_szf_115_sfb .section}

-   The billed traffic is more than the traffic recorded in logs. The traffic recorded in CDN logs is the traffic recorded in application-layer logs. TCP/IP packet headers and TCP retransmissions consume traffic. Therefore, the generated network traffic is higher than the traffic recorded in application-layer logs.
-   If you spend more than CNY 100,000 on CDN services per month, you can choose a monthly billing method. This method is more cost-effective. You can contact us by submitting a ticket or dialing the pre-sales number \(95187 ext. 1\).

