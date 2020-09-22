# DescribeDomainCertificateInfo

Queries the certificate information about an accelerated domain name.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainCertificateInfo&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainCertificateInfo|The operation that you want to perform. Set the value to **DescribeDomainCertificateInfo**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|CertInfos|Array| |The certificate information. |
|CertInfo| | | |
|CertDomainName|String|example.com|The domain name that is specified in the certificate. |
|CertExpireTime|String|2018-06-03T22:03:39Z|The time when the certificate expires. |
|CertLife|String|months|The unit of the validity period of the certificate.

-   **months**: The validity period is measured in months.
-   **years**: The validity period is measured in years. |
|CertName|String|example.com|The name of the certificate. |
|CertOrg|String|Let's Encrypt|The name of the certificate authority \(CA\) that issued the certificate. |
|CertStartTime|String|2018-06-03T22:03:39Z|The time when the certificate became effective. |
|CertType|String|free|The type of the certificate. Valid values:

-   **free**: a free certificate.
-   **cas**: a certificate purchased from Alibaba Cloud SSL Certificates Service.
-   **upload**: a user-uploaded certificate. |
|CertUpdateTime|String|2018-06-03T22:03:39Z|The time when the certificate was renewed. |
|DomainCnameStatus|String|ok|The status of the CNAME of the domain name.

-   **ok**: The domain name points to a CNAME assigned from Alibaba Cloud Content Delivery Network \(CDN\).
-   **cname\_error**: An error occurred and the domain name cannot point to the CNAME.
-   **top\_domain\_cname\_error**: An error occurred to the CNAME of the top-level domain name. The domain name cannot point to the CNAME.
-   **unsupport\_wildcard**: Wildcard domain names are not supported. |
|DomainName|String|example.com|The accelerated domain name. |
|ServerCertificate|String|asdadaxxxx|The public key of the certificate. |
|ServerCertificateStatus|String|on|The status of HTTPS.

-   **on**: enabled
-   **off**: disabled |
|Status|String|success|The status of the certificate.

-   **success**: The certificate is effective.
-   **checking**: The system is checking whether the domain name is accelerated by Alibaba Cloud CDN.
-   **cname\_error**: The domain name is not accelerated by Alibaba Cloud CDN.
-   **top\_domain\_cname\_error**: The top-level domain name is not an accelerated domain name.
-   **domain\_invalid**: The domain name contains invalid characters.
-   **unsupport\_wildcard**: Wildcard domain names are not supported.
-   **applying**: The application for a certificate is in the process.
-   **fget\_token\_timeout**: The application for a certificate timed out.
-   **check\_token\_timeout**: The verification timed out.
-   **get\_cert\_timeout**: The request to obtain the certificate timed out.
-   **failed**: The application for a certificate failed. |
|RequestId|String|5C1E43DC-9E51-4771-82C0-7D5ECEB547A1|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeDomainCertificateInfo
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainCertificateInfo>
      <CertInfos>
            <CertInfo>
                  <Status>success</Status>
                  <CertLife>3 months</CertLife>
                  <ServerCertificateStatus>on</ServerCertificateStatus>
                  <CertType>cas</CertType>
                  <CertName>example.com</CertName>
                  <CertDomainName>example.com</CertDomainName>
                  <DomainName>example.com</DomainName>
                  <CertOrg>Let's Encrypt</CertOrg>
                  <CertExpireTime>2018-06-03T22:03:39Z</CertExpireTime>
            </CertInfo>
      </CertInfos>
      <RequestId>5C1E43DC-9E51-4771-82C0-7D5ECEB547A1</RequestId>
</DescribeDomainCertificateInfo>
```

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

## Errors

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

