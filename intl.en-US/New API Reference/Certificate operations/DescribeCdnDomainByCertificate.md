# DescribeCdnDomainByCertificate

Queries accelerated domain names by SSL certificate.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainByCertificate&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnDomainByCertificate|The operation that you want to perform. Set the value to **DescribeCdnDomainByCertificate**. |
|SSLPub|String|Yes|yourSSLPub|The public key of the SSL certificate. You must encode the public key in Base64 and then call the encodeURIComponent function to encode the public key again.

 The public key must be in the PEM format. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|CertInfos|Array| |The information about the SSL certificate. |
|CertInfo| | | |
|CertCaIsLegacy|String|yes|Indicates whether the SSL certificate is obsolete. Valid values:

 -   **yes**: The certificate is obsolete.
-   **no**: The certificate is working as expected. |
|CertExpireTime|String|Nov 29 00:00:00 2016 GMT|The time when the certificate expires. |
|CertExpired|String|yes|Indicates whether the certificate is expired. Valid values:

 -   **yes**: The certificate is expired.
-   **no**: The certificate is not expired. |
|CertStartTime|String|Nov 29 23:59:59 2017 GMT|The time when the certificate became effective. |
|CertSubjectCommonName|String|test.example.com|The name of the certificate owner. |
|CertType|String|RSA|The type of the certificate. Valid responses: **RSA**, **DSA**, and **ECDSA**. |
|DomainList|String|example1.com,example2.com|If a value is returned, the value matches the certificate. Multiple domain names are separated with commas \(,\). |
|DomainNames|String|\*.example1.com,example2.com|The domain names \(DNS fields\) that match the certificate. Multiple domain names are separated with commas \(,\). |
|Issuer|String|C=US, O=Symantec Corporation, OU=Symantec Trust Network, OU=Domain Validated SSL, CN=Symantec Basic DV SSL CA - G1|The certificate authority that issues the certificate. |
|RequestId|String|ASAF2FDS-12SADSA-DDSAE3D-DSADCD4C-CDADS2D|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeCdnDomainByCertificate
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
    "RequestId": "ASAF2FDS-12SADSA-DDSAE3D-DSADCD4C-CDADS2D",
    "content": [
        {
            "Issuer": "C=US, O=Symantec Corporation, OU=Symantec Trust Network, OU=Domain Validated SSL, CN=Symantec Basic DV SSL CA - G1",
            "CertType": "RSA",
            "CertSubjectCommonName": "test.example.com",
            "CertStartTime": "Nov 29 23:59:59 2017 GMT",
            "CertExpireTime": "Nov 29 00:00:00 2016 GMT",
            "DomainNames": "*.example1.com,example2.com",
            "DomainList": "example1.com,example2.com",
            "CertExpired": "yes",
            "CertCaIsLegacy": "yes"
        }
     ]
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Certificate.FormatError|The format of the certificate is invalid.|The error message returned because the format of the specified certificate is invalid.|
|500|InternalError|The request processing has failed due to backend service exception.|The error message returned because an internal error occurred. Try again later. If the error persists, submit a ticket.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

