# Management of SSL certificates

Alibaba Cloud Content Delivery Network \(CDN\) provides a wide array of API operations that can be used to manage Secure Sockets Layer \(SSL\) certificates. The procedures for calling the API operations can be complex. This topic describes the features of the API operations to help you understand the use of the API operations.

## Procedure for calling the latest CDN API

![Management of SSL certificates 01](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2940530161/p207762.png)

**Note:** If an SSL certificate is uploaded to Alibaba Cloud CDN by calling certificate signing request \(CSR\) management operations, the method to renew the SSL certificate is the same as renewing certificates issued by Alibaba Cloud Security.

The following table describes the certificate management operations.

|API|Description|
|---|-----------|
|[AddCdnDomain](/intl.en-US/New API Reference/Domain name management/AddCdnDomain.md)|Adds a domain name to Alibaba Cloud CDN.|
|[VerifyDomainOwner](/intl.en-US/New API Reference/Domain name management/VerifyDomainOwner.md)|Verifies the ownership of a specified domain name.|
|[DescribeVerifyContent](/intl.en-US/New API Reference/Domain name management/DescribeVerifyContent.md)|Queries the ownership verification content of an accelerated domain name.|
|[DescribeDomainCertificateInfo](/intl.en-US/New API Reference/Certificate operations/DescribeDomainCertificateInfo.md)|Queries the certificate information about an accelerated domain name.|
|[SetDomainServerCertificate](/intl.en-US/New API Reference/Certificate operations/SetDomainServerCertificate.md)|Configures an SSL certificate for an accelerated domain name.|
|[DescribeCdnHttpsDomainList](/intl.en-US/New API Reference/Certificate operations/DescribeCdnHttpsDomainList.md)|Queries the information about the SSL certificates under your Alibaba Cloud account.|
|[DescribeCdnCertificateDetail](/intl.en-US/New API Reference/Certificate operations/DescribeCdnCertificateDetail.md)|Queries the detailed information about an SSL certificate.|
|[DescribeCdnDomainByCertificate](/intl.en-US/New API Reference/Certificate operations/DescribeCdnDomainByCertificate.md)|Queries accelerated domain names by SSL certificate.|
|[BatchSetCdnDomainServerCertificate](/intl.en-US/New API Reference/Certificate operations/BatchSetCdnDomainServerCertificate.md)|Enables, disables, or modifies the SSL certificates of one or more accelerated domain names.|

## Procedure for calling the earlier CDN API

When you call API operations, we recommend that you follow the procedure for calling the latest CDN API.

![Management of SSL certificates](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6468101061/p168788.png)

For more information, see [Certificate management](/intl.en-US/New API Reference/List of operations by function.md).

