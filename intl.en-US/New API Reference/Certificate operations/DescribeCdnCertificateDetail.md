# DescribeCdnCertificateDetail

Queries the detailed information about the SSL certificate.

The maximum number of times that each user can call this operation per second is 20.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnCertificateDetail&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnCertificateDetail|The operation that you want to perform. Set the value to **DescribeCdnCertificateDetail**. |
|CertName|String|Yes|cert-15480655xxxx|The ID of the certificate. You can query only one certificate at a time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Cert|String|-----BEGIN CERTIFICATE-----\\nMIIFzDCCBLSgAwIBxxxx|The content of the certificate. |
|CertId|Long|881049|The ID of the certificate. |
|CertName|String|cert-15480655xxxx|The name of the certificate. |
|Key|String|xxxx|The key of the certificate. |
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeCdnCertificateDetail
&CertName=cert-15480655xxxx
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnCertificateDetailResponse>
  <CertId>881049</CertId>
  <RequestId>34D625D3-E316-460C-B87D-85BB5AD8AEAD</RequestId>
  <CertName>cert-15480655xxxx</CertName>
  <Cert>-----BEGIN CERTIFICATE-----
MIIFzDCCBLSgAwIBxxxx</Cert>
  <Key>xxxx</Key>
</DescribeCdnCertificateDetailResponse>
```

`JSON` format

```
{
	"CertId": 881049,
	"RequestId": "34D625D3-E316-460C-B87D-85BB5AD8AEAD",
	"CertName": "cert-15480655xxxx",
	"Cert": "-----BEGIN CERTIFICATE-----\nMIIFzDCCBLSgAwIBxxxx",
    "Key":"xxxx"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

