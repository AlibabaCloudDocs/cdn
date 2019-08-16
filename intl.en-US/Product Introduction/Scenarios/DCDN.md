# DCDN {#concept_727666 .concept}

This topic describes the DCDN function of Alibaba Cloud CDN. You can use DCDN to enhance network performance and user experience. The slow response and packet loss may be caused by issues such as a combination of dynamic and static resources, cross-provider operation, network instability, dependence on single-line origins, traffic spikes, and network congestion.

## Background information {#section_el0_zdt_iyl .section}

By default, DCDN accelerates only dynamic resources. That is, all static resource requests are directed to their origins through optimal routes. You can specify static content types or paths so that the system can automatically distinguish between dynamic and static resources. As a result, static resources are cached on edge CDN nodes and dynamic resources are distributed in acceleration to expedite the overall content distribution at full speeds.

DCDN integrates dynamic acceleration and static acceleration. It has become an independent Alibaba Cloud product named [DCDN](https://www.alibabacloud.com/product/dcdn?), which is widely used for e-commerce, social networking, government, enterprise, gaming, and finance platforms.

## Benefits {#section_iqc_4hv_cpk .section}

By using DCDN, you can resolve the following issues:

-   Diverse, complex dynamic content lowers page loading speeds.
-   Issues such as dependence on single-line origins, traffic spikes, and network congestion cause page loading latency and content distribution failures.
-   Traditional communications protocols cannot ensure gaming users' access to real-time, highly concurrent dynamic content while maintaining stable network performance.
-   Load imbalance incurs pressure on origins in the event of traffic spikes.
-   Content is susceptible to hijacking and unauthorized changes, therefore service providers require network links and content distribution mechanisms that are more secure and efficient than HTTP.

## Required Alibaba Cloud functions {#section_zhv_wsx_k50 .section}

-   Separate acceleration of dynamic and static content: Dynamic content is accelerated by using intelligent routing, transmission protocol optimization, and link multiplexing, whereas static content is cached on edge CDN nodes to increase the overall resource loading speed.
-   Real-time detection and smooth internetworking: process heavy traffic loads while ensuring round-the-clock network availability.
-   Back-to-origin load balance, primary/secondary backup, connection multiplexing, and ordered back-to-origin processes: reduce pressure and fault risks on origins.
-   Full-link HTTPS secure acceleration, anti-leech, and IP-based traffic policing: make origins secure.
-   Rule customization, information monitoring, and alarming: You can define dynamic or static acceleration rules and cache rules, monitor data, and receive alarms in case of exceptions.

