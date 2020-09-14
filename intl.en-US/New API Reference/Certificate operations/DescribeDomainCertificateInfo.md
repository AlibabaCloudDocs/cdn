# DescribeDomainCertificateInfo

You can call the DescribeDomainCertificateInfo operation to query the certificate information of a CDN domain.

## Debugging

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainCertificateInfo) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to DescribeDomainCertificateInfo.|
|DomainName|String|Yes|The name of the CDN domain of which the certificate information is queried.|

## Response parameters

|Parameter|Type|Description|
|:--------|:---|:----------|
|CertInfos|CertInfo\[\]|The certificate information.|

Parameters in CertInfo

|Parameter|Type|Description|
|:--------|:---|:----------|
|DomainName|String|The name of the CDN domain.|
|CertName|String|The name of the certificate.|
|CertDomainName|String|The domain name that matches the certificate.|
|CertStartTime|String|The time when the certificate starts to take effect.|
|CertUpdateTime|String|The time when the certificate was last updated.|
|CertExpireTime|String|The time when the certificate expires.|
|CertLife|String|The validity period of the certificate. -   months: The validity period is measured in months.
-   years: The validity period is measured in years. |
|CertType|String|The type of the certificate. -   free: a free certificate
-   cas: a certificate purchased from Alibaba Cloud SSL Certificates Service
-   upload: a user uploaded certificate |
|ServerCertificateStatus|String|The status of HTTPS. -   on: The HTTPS protocol is enabled.
-   off: The HTTPS protocol is disabled. |
|Status|String|The status of the certificate. -   success: The certificate has taken effect.
-   checking: The system is checking whether the domain has been accelerated by using Alibaba Cloud CDN.
-   cname\_error: No valid CNAME record has been added for the CDN domain.
-   top\_domain\_cname\_error: No valid CNAME record has been added for the primary domain.
-   domain\_invalid: The domain name contains invalid characters.
-   unsupport\_wildcard: The domain name is a wildcard domain name, which is not supported.
-   applying: The certificate is in the application process.
-   get\_token\_timeout: The certificate application request has timed out.
-   check\_token\_timeout: The verification has timed out.
-   get\_cert\_timeout: The request for obtaining the certificate has timed out.
-   failed: The certificate application request failed. |
|ServerCertificate|String|The public key of the certificate.|
|DomainCnameStatus|String|The status of the CNAME. -   ok: The CNAME has been accelerated by using Alibaba Cloud CDN.
-   cname\_error: No valid CNAME record has been added for the CNAME of the CDN domain.
-   top\_domain\_cname\_error: No valid CNAME record has been added for the CNAME of the primary domain.
-   unsupport\_wildcard: the CNAME is a wildcard domain name, which is not supported. |

## Examples

Sample request

```
http://cdn.aliyuncs.com?Action=DescribeDomainCertificateInfo&DomainName=example.com&<Common request parameters>
```

Sample success response

`JSON` format

```
{
  "CertInfos": {
    "CertInfo": [
      {
        "Status": "success",
        "CertLife": "3 months",
        "ServerCertificateStatus": "on",
        "CertType": "cas",
        "CertName": "example.com",
        "CertDomainName": "example.com",
        "DomainName": "example.com",
        "CertOrg": "Let's Encrypt",
        "CertExpireTime": "2018-06-03T22:03:39Z"
      }
    ]
  },
  "RequestId": "5C1E43DC-9E51-4771-82C0-7D5ECEB547A1"
}
```

## Error codes

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|The error message returned because the specified domain does not exist or does not belong to you.|

This table lists the error codes that the operation can return. For more information, see [Error codes](https://error-center.aliyun.com/status/product/Cdn).

