# Query SSL certificates of domain names

This topic describes how to query the status of SSL certificates configured for domain names under your Alibaba Cloud account.

SSL certificates are configured for your domain names. For more information, see [Configure an SSL certificate for multiple domain names at a time](/intl.en-US/Service Management/Certificate service/Configure an SSL certificate for multiple domain names at a time.md).

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Security & Protection** \> **HTTPS Center**.

3.  On the **HTTPS Center** page, view the information about an SSL certificate.

    The **accelerated domain name** associated with the certificate, the **Certificate Name**, and the **Certificate Status** are displayed on this page. The following table describes the states of an SSL certificate.

    |Certificate state|Description|
    |-----------------|-----------|
    |Valid|The SSL certificate is valid.|
    |The specified domain name does not match the SSL certificate.|If the domain name and the SSL certificate do not match, you must update the certificate. For more information, see [Configure an SSL certificate for multiple domain names at a time](/intl.en-US/Service Management/Certificate service/Configure an SSL certificate for multiple domain names at a time.md).|
    |Expiring|The SSL certificate is about to expire. Renew your certificate at the earliest opportunity. For more information, see [Manual renewal](/intl.en-US/Renew Certificates/Manual renewal.md).|
    |Expired|The SSL certificate has expired. You can renew the certificate based on your business requirements. For more information, see [Configure an SSL certificate for multiple domain names at a time](/intl.en-US/Service Management/Certificate service/Configure an SSL certificate for multiple domain names at a time.md).|


## API operations

You can call the related API operation to query the SSL certificates of your domain names. For more information, see [DescribeCdnHttpsDomainList](/intl.en-US/New API Reference/Certificate operations/DescribeCdnHttpsDomainList.md).

