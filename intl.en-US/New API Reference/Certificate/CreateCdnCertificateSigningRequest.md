# CreateCdnCertificateSigningRequest

You can call this operation to create a certificate signing request \(CSR\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=CreateCdnCertificateSigningRequest&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Required|CreateCdnCertificateSigningRequest|The operation that you want to perform. Set the value to **CreateCdnCertificateSigningRequest**. |
|CommonName|String|Required|xxx|The Common Name of the SSL certificate. |
|SANs|String|No|example.com|The Subject Alternative Name \(SAN\) extension of the SSL certificate. This extension is used to add domain names to the certificate. Separate multiple domain names with commas \(,\). |
|Organization|String|No|Alibaba Inc|The name of the organization. Default value: Alibaba Inc. |
|OrganizationUnit|String|No|Aliyun CDN|The name of the organization unit. Default value: Aliyun CDN. |
|Country|String|No|CN|The country to which the organization belongs. Default value: CN. |
|State|String|No|Zhejiang|The provincial district to which the organization belongs. Default value: Zhejiang. |
|City|String|No|Hangzhou|The city to which the organization belongs. Default value: Hangzhou. |
|Email|String|No|xxx.com|The email address that can be used to contact the organization. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|CommonName|String|example.com|The Common Name of the certificate. |
|Csr|String|xxx|The content of the CSR. |
|PubMd5|String|629bf4fd8104eda171135bcb0f77xxxx|The MD5 value of the certificate public key. |
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=CreateCdnCertificateSigningRequest
&CommonName=xxxx
&SANs=xx.com,xxx.xx.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<CreateCdnCertificateSigningRequestResesponse>
  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
  <CommonName>example.com</CommonName>
  <Csr>-----BEGIN CERTIFICATE REQUEST-----
MIIC/zqTxxxxx
-----END CERTIFICATE REQUEST-----
</Csr>
  <PubMd5>629bf4fd8104eda171135bcb0f77xxxx</PubMd5>
</CreateCdnCertificateSigningRequestResesponse>
```

`JSON` format

```
{
    "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9",
    "CommonName":"example.com",
    "Csr": "-----BEGIN CERTIFICATE REQUEST-----\nMIIC/zqTxxxxx\n-----END CERTIFICATE REQUEST-----\n",
    "PubMd5":"629bf4fd8104eda171135bcb0f77xxxx"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

