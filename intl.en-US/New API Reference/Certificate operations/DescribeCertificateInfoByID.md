# DescribeCertificateInfoByID

Queries the information about a specific SSL certificate.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCertificateInfoByID&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCertificateInfoByID|The operation that you want to perform. Set the value to **DescribeCertificateInfoByID**. |
|CertId|String|Yes|1644xx|The ID of the SSL certificate. You can query only one SSL certificate at a time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|CertInfos|Array of CertInfo| |The information about the SSL certificate. |
|CertInfo| | | |
|CertExpireTime|String|2098-02-08 08:02:07 +0000 UTC|The time when the SSL certificate expires. |
|CertId|String|1644xx|The ID of the SSL certificate. |
|CertName|String|example\_cert|The name of the SSL certificate. |
|CertType|String|cas|The type of the SSL certificate. Valid values:

 -   free: a free SSL certificate.
-   cas: an SSL certificate purchased from Alibaba Cloud SSL Certificates Service.
-   upload: a user-uploaded SSL certificate. |
|CreateTime|String|2015-12-21 08:02:07 +0000 UTC|The time when the SSL certificate became effective. |
|DomainList|String|\["example.com"\]|The list of domain names that use the SSL certificate. |
|HttpsCrt|String|-----BEGIN CERTIFICATE-----\\nxxx-----END CERTIFICATE-----\\n|The content of the SSL certificate. |
|RequestId|String|5C1E43DC-9E51-4771-82C0-7D5ECEB547A1|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeCertificateInfoByID
&CertId=1644xx
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCertificateInfoByIDResponse>
  <CertInfos>
        <CertInfo>
              <CertId>1644xx</CertId>
              <CertName>example_cert</CertName>
              <CreateTime>2015-12-21 08:02:07 +0000 UTC</CreateTime>
              <HttpsCrt>-----BEGIN CERTIFICATE-----
xxx-----END CERTIFICATE-----
</HttpsCrt>
              <CertType>cas</CertType>
              <CertExpireTime>2098-02-08 08:02:07 +0000 UTC</CertExpireTime>
              <DomainList>example.com</DomainList>
        </CertInfo>
  </CertInfos>
  <RequestId>5C1E43DC-9E51-4771-82C0-7D5ECEB547A1</RequestId>
</DescribeCertificateInfoByIDResponse>
```

`JSON` format

```
{
  "CertInfos": {
    "CertInfo": [{
        "CertId": "1644xx",
        "CertName": "example_cert",
        "CreateTime": "2015-12-21 08:02:07 +0000 UTC",
        "HttpsCrt": "-----BEGIN CERTIFICATE-----\nxxx-----END CERTIFICATE-----\n",
        "CertType": "cas",
        "CertExpireTime": "2098-02-08 08:02:07 +0000 UTC",
        "DomainList": ["example.com"]
      }]
  },
  "RequestId": "5C1E43DC-9E51-4771-82C0-7D5ECEB547A1"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

