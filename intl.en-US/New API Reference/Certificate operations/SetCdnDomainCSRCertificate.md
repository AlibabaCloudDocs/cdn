# SetCdnDomainCSRCertificate

Configures an SSL certificate for a specified domain name.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=SetCdnDomainCSRCertificate&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|SetCdnDomainCSRCertificate|The operation that you want to perform. Set the value to **SetCdnDomainCSRCertificate**. |
|DomainName|String|Yes|example.com|The accelerated domain name for which you want to configure an SSL certificate. The domain name must have HTTPS secure acceleration enabled. |
|ServerCertificate|String|Yes|xxx|The content of the certificate. The certificate must match the certificate signing request \(CSR\) created by calling the [CreateCdnCertificateSigningRequest](~~144478~~) operation. Make sure that the content of the certificate is encoded in Base64 and then encoded by encodeURIComponent. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=SetCdnDomainCSRCertificate
&DomainName=example.com
&ServerCertificate=xxx
&<Common request parameters>
```

Sample success responses

`XML` format

```
<SetCdnDomainCSRCertificateResponse>
  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</SetCdnDomainCSRCertificateResponse>
```

`JSON` format

```
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Certificate.MissingParameter|You must specify the Certificate parameter.|The error message returned because the Certificate parameter is not set.|
|400|Certificate.EncodeError|An error occurred while encoding the certificate.|The error message returned because a certificate encoding error occurred.|
|400|Certificate.DecodeError|An error occurred while decoding the certificate.|The error message returned because a certificate decoding error occurred.|
|400|Certificate.FormatError|The format of the certificate is invalid.|The error message returned because the format of the certificate is invalid.|
|400|Certificate.MissMatch|The certificate does not match the domain.|The error message returned because the certificate does not match the specified accelerated domain name.|
|400|Certificate.NoPrivateKey|The private key of the certificate does not exist.|The error message returned because the specified private key of the certificate does not exist.|
|500|Internal.ForbidError|You cannot modify the configurations when some features of the domain are in a canary deployment.|The error message returned because a feature of the specified accelerated domain name is in canary release and you cannot modify the configurations.|
|500|Internal.ConfigError|An error occurred while configuring the certificate.|The error message returned because an error occurred while calling the specified operation.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

