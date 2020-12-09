# Configure OCSP stapling

OCSP stapling is an alternative approach to the Online Certificate Status Protocol \(OCSP\) that you can use to validate digital certificates. OCSP stapling allows Alibaba Cloud Content Delivery Network \(CDN\) servers to retrieve OCSP details. This reduces the latency that occurs when clients send requests to validate digital certificates and minimizes the time that is consumed by clients to receive the validation responses. This topic describes the scenarios of OCSP stapling. It also provides details about how to enable this feature in the Alibaba Cloud CDN console.

OCSP extension fields are supported by clients. Otherwise, the OCSP stapling feature cannot take effect.

OCSP details are provided by the certificate authority \(CA\) that issues the digital certificates. Based on the OCSP details, the digital certificates can be validated online based on actual needs.

Issue: Clients such as web browsers send certificate validation requests to the OCSP responders that are provided by CAs. If network connections are intermittent or interrupted, it takes a long period for the clients to receive the validation responses. During this period, blank pages appear and disable expected subsequent operations on the clients.

![OCSP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3631186061/p99426.png)

Solution: Alibaba Cloud CDN provides the OCSP stapling feature. If this feature is enabled, Alibaba Cloud CDN servers send requests to retrieve OCSP details at a low frequency, and cache the retrieved OCSP details. When clients initiate Transport Layer Security \(TLS\) handshakes, Alibaba Cloud CDN servers return the OCSP details and certificate chains to the clients. OCSP stapling provides a quick method for the clients to receive the validation responses. This allows expected subsequent operations on the clients. Another benefit is that the OCSP stapling process does not introduce additional security risks. This is because the OCSP details of digital certificates cannot be forged.

![OCSP Stapling](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4631186061/p99427.png)

**Note:**

-   By default, Alibaba Cloud CDN retrieves and caches the OCSP details for 60 minutes after OCSP Stapling is enabled.
-   After the OCSP details expire, the first certificate validation request that follows the expiration time fails to receive the validation response.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **HTTPS**.

5.  In the **OCSP Stapling** section, turn on **OCSP stapling**.

    ![OCSP Stapling](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0447747061/p99429.png)


