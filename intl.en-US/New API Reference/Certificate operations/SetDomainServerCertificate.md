# SetDomainServerCertificate

Configures a Secure Sockets Layer \(SSL\) certificate for an accelerated domain name.

The maximum number of times that each user can call this operation per second is 10.

Method: POST.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=SetDomainServerCertificate&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|SetDomainServerCertificate|The operation that you want to perform. Set the value to SetDomainServerCertificate. |
|DomainName|String|Yes|example.com|The accelerated domain name for which you want to configure the SSL certificate. The type of request supported by the domain name must be HTTPS.

 You can specify only one domain name in each query. |
|ServerCertificateStatus|String|Yes|on|Specifies whether to enable the SSL certificate. Valid values:

 -   **on**: enables the SSL certificate.
-   **off**: disables the SSL certificate. This is the default value. |
|CertName|String|No|myCert1|The name of the SSL certificate. You can specify only one certificate name. |
|CertType|String|No|cas|The type of the SSL certificate. Valid values:

 -   **upload**: a user-uploaded SSL certificate.
-   **cas**: an SSL certificate purchased from Alibaba Cloud SSL Certificates Service.
-   **free**: a free SSL certificate.

 **Note:** If this parameter is set to **cas**, the **PrivateKey** parameter is optional. |
|ServerCertificate|String|No|----BEGIN CERTIFICATE----- MIIFz\*\*\*\*-----END CERTIFICATE-----|The content of the SSL certificate. Specify the content of the certificate only if you want to enable the SSL certificate. |
|PrivateKey|String|No|----BEGIN RSA PRIVATE KEY-----QswCQ\*\*\*\*----END RSA PRIVATE KEY-----|The private key. Specify the private key only if you want to enable the SSL certificate. |
|ForceSet|String|No|1|Specifies whether to check the certificate name for duplicates. If you set the value to 1, the system does not perform the check and overwrites the information about the certificate that uses the same name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.comAction=SetDomainServerCertificate
&DomainName=example.com
&CertType=cas
&CertName=myCert1
&ServerCertificateStatus=on
&ServerCertificate=----BEGIN CERTIFICATE----- MIIFz****-----END CERTIFICATE-----
&<Common request parameters>
```

Sample success responses

`XML` format

```
<SetDomainServerCertificateResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</SetDomainServerCertificateResponse>
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
|400|Certificate.NotFind|Not find the certificate info.|The error message returned because the specified SSL certificate does not exist.|
|400|Certificate.MissMatch|The certificate is not match the private key.|The error message returned because the specified SSL certificate and private key do not match.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

