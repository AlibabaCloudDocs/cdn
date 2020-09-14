# DescribeCdnCertificateDetail

You can call this operation to query the detailed information about a CDN certificate.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnCertificateDetail&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|DescribeCdnCertificateDetail|The operation that you want to perform. Set the value to **DescribeCdnCertificateDetail**. |
|CertName|String|Yes|xxx|The name of the certificate to query. |

## Response parameters

|Parameter|Type|Example|Description |
|---------|----|-------|------------|
|Cert|String|xxxxx|The certificate content returned. |
|CertId|Long|881049|The ID of the certificate. |
|CertName|String|test|The name of the certificate. |
|Key|String|xxxxx|The key of the certificate. |
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeCdnCertificateDetail
&CertName=xxxx
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnCertificateDetailResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
	  <Cert>xxxxx</Cert>
	  <Key>xxxxx</Key>
	  <CertId>881049</CertId>
	  <CertName>test</CertName>
</DescribeCdnCertificateDetailResponse>
```

`JSON` format

```
{
	"CertId":"881049",
	"Key":"xxxxx",
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9",
	"CertName":"test",
	"Cert":"xxxxx"
}
```

## Error codes

For more information about error codes, visit [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

