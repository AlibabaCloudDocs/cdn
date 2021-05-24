# BatchSetCdnDomainServerCertificate

Enables, disables, or modifies the SSL certificates of one or more accelerated domain names at a time.

**Note:** The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=BatchSetCdnDomainServerCertificate&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|BatchSetCdnDomainServerCertificate|The operation that you want to perform. Set the value to **BatchSetCdnDomainServerCertificate**. |
|DomainName|String|Yes|example.com|The accelerated domain name to which the SSL certificate belongs. The type of request supported by the accelerated domain name must be HTTPS. You can specify multiple accelerated domain names and separate them with commas \(,\).

 **Note:** You can manage the SSL certificates of up to 50 accelerated domain names in each call. |
|SSLProtocol|String|Yes|on|Specifies whether to enable the SSL certificate. Valid values:

 -   **on**: enables the SSL certificate.
-   **off**: disables the SSL certificate. This is the default value. |
|SSLPub|String|No|yourSSLPub|The content of the SSL certificate. Specify the content of the certificate only if you want to enable the SSL certificate. |
|SSLPri|String|No|yourSSLPri|The private key. Specify the private key only if you enable the SSL certificate. |
|CertName|String|No|yourCertName|The name of the certificate. |
|CertType|String|No|cas|The type of the SSL certificate. Valid values:

 -   **upload**: a user-uploaded SSL certificate.
-   **cas**: a certificate that is issued by SSL Certificates Service. |
|Region|String|No|your region|The region. |
|ForceSet|String|No|1|Specifies whether to check the certificate name for duplicates. If you set the value to 1, the system does not perform the check and overwrites the information about the existing certificate that uses the same name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/?Action=BatchSetCdnDomainServerCertificate
&DomainName=example.com
&SSLProtocol=on
&SSLPub=xxx
&SSLPri=yyy
&<Common request parameters>
```

Sample success responses

`XML` format

```
<BatchSetCdnDomainServerCertificateResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</BatchSetCdnDomainServerCertificateResponse>
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
|400|Certificate.FormatError|The format of the certificate is invalid.|The error message returned because the format of the specified SSL certificate is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

