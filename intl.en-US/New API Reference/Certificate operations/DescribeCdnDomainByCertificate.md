# DescribeCdnDomainByCertificate

You can call this operation to query CDN domains by certificate.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainByCertificate&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnDomainByCertificate|The operation that you want to perform. Set the value to **DescribeCdnDomainByCertificate**. |
|SSLPub|String|Yes|yourSSLPub|The public key of the certificate. You must encode the public key with Base64 and then call the encodeURIComponent function. You can specify the public key in the PEM format. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|CertInfos|N/A|N/A|The certificate information returned. |
|CertCaIsLegacy|String|yes|Indicates whether the CA certificate is obsolete.**yes**: obsolete. **no**: active and not obsolete. |
|CertExpireTime|String|Nov 29 00:00:00 2016 GMT|The time when the certificate expires. |
|CertExpired|String|yes|Indicates whether the certificate has expired. **yes**: expired. **no**: not expired. |
|CertStartTime|String|Nov 29 23:59:59 2017 GMT|The time when the certificate starts to take effect. |
|CertSubjectCommonName|String|test.example.com|The name of the certificate owner. |
|CertType|String|RSA|The returned certificate type. Valid responses: **RSA**, **DSA**, and **ECDSA**. |
|DomainList|String|example1.com,example2.com|The CDN domain names that match the certificate. Multiple CDN domain names are separated with commas \(,\). An empty string may be returned for the **DomainList** parameter. |
|DomainNames|String|\*.example1.com,example2.com|The domain names \(DNS fields\) that match the certificate. Multiple domain names are separated with commas \(,\). |
|Issuer|String|C=US, O=Symantec Corporation, OU=Symantec Trust Network, OU=Domain Validated SSL, CN=Symantec Basic DV SSL CA - G1|The certificate authority that issues the certificate. |
|RequestId|String|ASAF2FDS-12SADSA-DDSAE3D-DSADCD4C-CDADS2D|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeCdnDomainByCertificate
&SSLPub=xxx
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnDomainByCertificateResponse>
	  <RequestId>ASAF2FDS-12SADSA-DDSAE3D-DSADCD4C-CDADS2D</RequestId>
	  <content>
		    <Issuer>C=US, O=Symantec Corporation, OU=Symantec Trust Network, OU=Domain Validated SSL, CN=Symantec Basic DV SSL CA - G1</Issuer>
		    <CertType>RSA</CertType>
		    <CertSubjectCommonName>test.example.com</CertSubjectCommonName>
		    <CertStartTime>Nov 29 23:59:59 2017 GMT</CertStartTime>
		    <CertExpireTime>Nov 29 00:00:00 2016 GMT</CertExpireTime>
		    <DomainNames>*.example1.com,example2.com</DomainNames>
		    <DomainList>example1.com,example2.com</DomainList>
		    <CertExpired>yes</CertExpired>
		    <CertCaIsLegacy>yes</CertCaIsLegacy>
	  </content>
</DescribeCdnDomainByCertificateResponse>
```

`JSON` format

```
{
	"content":[
		{
			"CertExpired":"yes",
			"Issuer":"C=US, O=Symantec Corporation, OU=Symantec Trust Network, OU=Domain Validated SSL, CN=Symantec Basic DV SSL CA - G1",
			"DomainNames":"*.example1.com,example2.com",
			"CertSubjectCommonName":"test.example.com",
			"CertType":"RSA",
			"CertExpireTime":"Nov 29 00:00:00 2016 GMT",
			"DomainList":"example1.com,example2.com",
			"CertStartTime":"Nov 29 23:59:59 2017 GMT",
			"CertCaIsLegacy":"yes"
		}
	],
	"RequestId":"ASAF2FDS-12SADSA-DDSAE3D-DSADCD4C-CDADS2D"
}
```

## Error codes

For more information about error codes, visit [API Error Center](https://error-center.aliyun.com/status/product/Cdn).

For more information about error codes, visit [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

