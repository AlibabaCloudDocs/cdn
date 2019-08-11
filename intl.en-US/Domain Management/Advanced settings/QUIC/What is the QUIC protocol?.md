# What is the QUIC protocol? {#concept_1322820 .concept}

If the connection between a client and a CDN node uses the QUIC protocol for data communication, the connection can ensure the security of data transmission and improve the resource access efficiency. This topic describes what is QUIC, how QUIC works, and client requirements and billing of the QUIC protocol.

## What is QUIC? {#section_bhc_u76_dw2 .section}

Quick UDP Internet Connections \(QUIC\) is an experimental transport layer network protocol that provides the same security as TLS/SSL and has reduced connection and transmission latency. Based on UDP, QUIC has excellent performance in case of weak network connections. When packet loss and network latency are severe, QUIC can still provide available services. QUIC can implement different congestion control algorithms at the application layer without the support of the operating system and the kernel. Compared with the traditional TCP protocol, QUIC allows future changes to be made more easily. This protocol is very suitable for businesses that encounter bottlenecks in TCP protocol optimization.

Currently, Alibaba Cloud CDN supports the layer-7 QUIC \(HTTP over QUIC\) protocol. The version number is Q39.

## How QUIC works {#section_64k_g5v_v3k .section}

The following figure shows how QUIC is used in Alibaba Cloud CDN.

![QUIC schematic](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1054402/156552298752635_en-US.png)

## Client requirements {#section_mib_tch_z1i .section}

The QUIC protocol has the following requirements for a client:

-   If you use Google Chrome, only version Q43 is supported. The QUIC protocol supported by Alibaba Cloud CDN is version Q39. You cannot use Google Chrome to directly send QUIC requests to Alibaba Cloud CDN.
-   If you use a self-developed app, the app must integrate a network library that supports the QUIC protocol, such as lsquic-client or Cronet.

## QUIC billing {#section_gtm_36l_pj0 .section}

The QUIC protocol is a value-added service and incurs additional fees for the number of QUIC requests. For more information, see [CDN pricing](https://www.aliyun.com/price/product?spm=5176.175459.915900.btn2.3749312f2FsBxF#/cdn/detail).

**Note:** For a QUIC request whose protocol header is HTTPS, it will not be repeatedly charged in both HTTPS requests and QUIC requests. The HTTPS request billing and the QUIC request billing are mutually exclusive. One request is charged for only one type of requests.

-   QUIC requests are not identified by the request header. Whether a request is a QUIC request is determined by the UDP protocol.
-   CDN first checks whether the request is a QUIC request. If yes, the request is billed according to the QUIC billing rules. CDN will no longer check whether the request is an HTTPS request. If no, CDN continues to check whether the request is an HTTPS request.

