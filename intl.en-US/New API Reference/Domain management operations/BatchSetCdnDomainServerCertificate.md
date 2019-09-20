# BatchSetCdnDomainServerCertificate {#doc_api_Cdn_BatchSetCdnDomainServerCertificate .reference}

You can call this operation to configure an SSL certificate for one or more CDN domains.

## Debugging {#api_explorer .section}

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=BatchSetCdnDomainServerCertificate&type=RPC&version=2018-05-10)

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|BatchSetCdnDomainServerCertificate|The operation that you want to perform. Set the value to **BatchSetCdnDomainServerCertificate**.

 |
|DomainName|String|Yes|example.com|The name of the CDN domain to which the certificate belongs. The CDN domain must have HTTPS secure acceleration enabled. You can specify multiple CDN domain names and separate them with commas \(,\).

 |
|SSLProtocol|String|Yes|on|Specifies whether to enable the SSL certificate.

 -   **on**: enables the SSL certificate.
-   **off**: disables the SSL certificate.

 Default value: **off**.

 |
|SSLPub|String|No|yourSSLPub|The content of the certificate. Specify the content of the certificate only if you enable the SSL certificate.

 |
|SSLPri|String|No|yourSSLPri|The private key. Specify the private key only if you enable the SSL certificate.

 |
|CertName|String|No|yourCertName|The name of the certificate.

 |
|CertType|String|No|cas|The type of the certificate. **upload**: an uploaded local certificate. **cas**: a certificate purchased from Alibaba Cloud SSL Certificates Service.

 |
|Region|String|No|your region|The ID of your region.

 |
|ForceSet|String|No|1|Specifies whether to check the certificate name for duplicates. If you set the value to 1, the system does not perform the check and overwrites the information of the existing certificate with the same name.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|The ID of the request.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}
http://cdn.aliyuncs.com?Action=BatchSetCdnDomainServerCertificate
&DomainName=example.com
&SSLProtocol=on
&SSLPub=xxx
&SSLPri=yyy
&<Common request parameters>
```

Sample success responses

`XML` format

``` {#xml_return_success_demo}
<BatchSetCdnDomainServerCertificateResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</BatchSetCdnDomainServerCertificateResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## Error codes { .section}

For more information about error codes, visit [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

