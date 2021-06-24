# What is the QUIC protocol?

The Quick UDP Internet Connections \(QUIC\) protocol provides enhanced security for data communication between clients and Content Delivery Network \(CDN\) nodes and also accelerates content delivery. This topic describes what is QUIC, how QUIC works, the client requirements, and the billing rules for using the QUIC protocol.

## What is QUIC?

QUIC is an experimental transport layer network protocol that provides the same security capabilities as TLS/SSL and reduces connection and transmission latency. QUIC is developed based on UDP and has an excellent performance in case of weak network connections. When packet loss and network latency issues are severe, QUIC can still provide available services. QUIC can implement different congestion control algorithms at the application layer regardless of what operating system or kernel is used. Compared with TCP, QUIC supports flexible changes based on service requirements. QUIC is a suitable alternative when TCP optimization encounters bottlenecks.

Alibaba Cloud CDN supports the implementation of QUIC at Layer 7 \(HTTP over QUIC\). Supported versions are Q39, Q43, and Q46.

## How QUIC works

The following figure shows how QUIC works with Alibaba Cloud CDN.

![Diagram](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5163723061/p54879.png)

## Client requirements

QUIC has the following requirements for clients:

-   If you use Google Chrome, the QUIC versions supported by Alibaba Cloud CDN are Q39, Q43, and Q46. Google Chrome can directly send QUIC requests to Alibaba Cloud CDN.
-   If you use a self-developed app, the app must be integrated with a network library such as lsquic-client or Cronet that supports QUIC.

## Billing rules for QUIC

QUIC is a value-added service and you are charged for the number of QUIC requests. For more information, see [CDN pricing](https://www.alibabacloud.com/product/cdn/pricing).

**Note:** If QUIC requests contain an HTTPS header, you are charged for only HTTPS or QUIC requests based on relevant rules. The billing rules for HTTPS requests and QUIC requests are mutually exclusive. Each request is billed as an HTTPS request or a QUIC request.

Billing rules for QUIC:

-   QUIC requests are identified based on UDP. They are not identified based on the request header.
-   Alibaba Cloud CDN checks whether a request is a QUIC request first. If a request is identified as a QUIC request, you are charged for a QUIC request. Otherwise, you are charged for an HTTPS request.

## Enable QUIC

The first private preview of QUIC has completed in June 2020. QUIC is unavailable to new users of Alibaba Cloud CDN. The second private preview will soon begin. You can apply for participation in the private preview.

