---
keyword: [Alibaba Cloud CDN, brief introduction]
---

# Brief introduction to Alibaba Cloud CDN

This topic introduces Alibaba Cloud Content Delivery Network \(CDN\) and its metering methods. For more information, see the "References" section in this topic. For more information about how to get started with Alibaba Cloud CDN and the basic features of this service, continue with the topics in this chapter.

## What is Alibaba Cloud CDN?

Alibaba Cloud Content Delivery Network \(CDN\) is a distributed network built over the transport network that consists of edge nodes deployed in different regions across the world. Alibaba Cloud CDN caches static and dynamic resources from origin servers to the edge nodes and allows users to retrieve desired content from the edge nodes. Alibaba Cloud CDN reduces workloads on origin servers to prevent network congestion. You can use Alibaba Cloud CDN to accelerate website content delivery in different regions or scenarios.

Alibaba Cloud has deployed over 2,800 nodes across the world. More than 2,300 nodes are deployed across 31 provincial regions inside mainland China. Among these nodes, a large number of them are deployed in first-tier cities and provincial capitals. More than 500 nodes are deployed across 70 regions outside mainland China, including China \(Hong Kong\), China \(Macao\), and China \(Taiwan\). Alibaba Cloud CDN supports a total bandwidth capacity of 130 Tbit/s and 10 GE network interface controllers \(NICs\). Each CDN node provides 40 TB to 1.5 PB of data storage, and a bandwidth capacity of 40 Gbit/s to 200 Gbit/s.

Alibaba Cloud CDN is applicable to the following scenarios:

-   [Image and small file distribution](/intl.en-US/Product Introduction/Scenarios/Image and small file distribution.md): Your websites or applications offer downloads of images and small files in formats such as HTML, CSS, and JavaScript.
-   [Delivery of large files](/intl.en-US/Product Introduction/Scenarios/Delivery of large files.md): Your websites or applications offer downloads of files larger than 20 MB, such as game applications, client applications, or mobile apps.
-   [ApsaraVideo for VOD](/intl.en-US/Product Introduction/Scenarios/ApsaraVideo for VOD.md): Your websites or applications offer on-demand video streaming or short video streaming. Mainstream media formats such as MP4 and FLV are supported.
-   [DCDN](/intl.en-US/Product Introduction/Scenarios/DCDN.md): Dynamic Route for CDN \(DCDN\) is an independent Alibaba Cloud service and can accelerate the delivery of dynamic content. You can also use DCDN to separately accelerate the delivery of static and dynamic content.
-   [SCDN](/intl.en-US/Product Introduction/Scenarios/SCDN.md): If your website is vulnerable to attacks and requires delivery acceleration, you can use SCDN to reinforce the security of your workloads.

During the use of Alibaba Cloud CDN, you can determine the acceleration effect based on multiple factors. These factors include the latency, download speed, website content loading speed, packet loss rate, ratio between the number of back-to-origin requests and the total number of requests, and cache hit ratio.

## Metering methods

Alibaba Cloud CDN is charged for basic services and value-added services.

-   Basic services support the pay-by-bandwidth and pay-by-data-transfer metering methods.

    The pay-by-bandwidth metering method applies if the amount of network traffic that goes through your accelerated domain name remains relatively stable but the bandwidth utilization exceeds a daily rate of 30%. The pay-by-data-transfer metering method applies if the amount of network traffic that goes through your accelerated domain name encounters substantial fluctuations and bandwidth spikes but the daily bandwidth utilization is lower than 30%.

    If you choose pay-by-data-transfer, you can purchase an outbound data transfer plan on an annual basis to minimize the costs. For more information, see [CDN Resource Plan](https://common-buy-intl.alibabacloud.com/?spm=a2c63.p38356.879954.4.798276ad33R6vU&commodityCode=%20cdn_bag_intl#/buy).

-   Value-added services are charged for HTTP requests, HTTPS requests, QUIC requests, real-time log entries, content moderation, and DCDN.

## References

For more information about the latest updates of Alibaba Cloud CDN, see [Release notes for Alibaba Cloud CDN](/intl.en-US/.md).

For more information about Alibaba Cloud CDN, see:

-   [Performance indicators of Alibaba Cloud CDN](/intl.en-US/Product Introduction/Performance indicators of Alibaba Cloud CDN.md)
-   [Node distribution](/intl.en-US/Product Introduction/Node distribution.md)
-   [How CDN works](/intl.en-US/Product Introduction/Architecture.md)
-   [Benefits](/intl.en-US/Product Introduction/Benefits.md)
-   [Case studies](/intl.en-US/Product Introduction/Case studies.md)
-   [Terms](/intl.en-US/Product Introduction/Terms.md)

For more information about the metering methods of Alibaba Cloud CDN, see:

-   [Pricing of basic services](/intl.en-US/Pricing/Billing method/Pricing of basic services.md)
-   [Billing of value-added services](/intl.en-US/Pricing/Billing method/Billing of value-added services.md)
-   [Change the metering method](/intl.en-US/Pricing/Change the metering method.md)
-   [Overdue payments](/intl.en-US/Pricing/Overdue payments.md)

## Get started with Alibaba Cloud CDN

For more information about how to get started with Alibaba Cloud CDN, see:

-   [Get started with Alibaba Cloud CDN](/intl.en-US/Guide for New Users/Get started with Alibaba Cloud CDN.md)
-   [Brief introduction to basic features of Alibaba Cloud CDN](/intl.en-US/Guide for New Users/Brief introduction to basic features of Alibaba Cloud CDN.md)

