# DescribeCdnCertificateList

Queries the list of SSL certificates for specified accelerated domain names.

The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnCertificateList&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnCertificateList|The operation that you want to perform. Set the value to **DescribeCdnCertificateList**. |
|DomainName|String|No|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

By default, this operation queries the list of SSL certificates for all accelerated domain names. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|CertificateListModel|Struct| |The data type of the SSL certificates information. |
|CertList|Array of Cert| |The detailed information about each SSL certificate. |
|Cert| | | |
|CertId|Long|1|The ID of the SSL certificate. |
|CertName|String|Certificate 1|The name of the SSL certificate. |
|Common|String|example.com|The Common Name \(CN\) attribute of the SSL certificate. Typically, the CN is the domain name. |
|Fingerprint|String|xxx|The fingerprint of the SSL certificate. |
|Issuer|String|xxx|The certificate authority \(CA\) that issued the SSL certificate. |
|LastTime|Long|1512388610|The timestamp when the SSL certificate was issued. |
|Count|Integer|2|The number of SSL certificates returned. |
|RequestId|String|FC0E34AC-0239-44A7-AB0E-800DE522C8DA|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeCdnCertificateList
&DomainName=xxx
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnCertificateListResponse>
      <CertificateListModel>
            <Count>2</Count>
            <CertList>
                  <Cert>
                        <CertName>Certificate 1</CertName>
                        <Issuer>xxx</Issuer>
                        <LastTime>1512388610</LastTime>
                        <CertId>1</CertId>
                        <Common>test</Common>
                        <Fingerprint>xxx</Fingerprint>
                  </Cert>
                  <Cert>
                        <CertName>Certificate 2</CertName>
                        <Issuer>xxx</Issuer>
                        <LastTime>1512388659</LastTime>
                        <CertId>2</CertId>
                        <Common>test</Common>
                        <Fingerprint>xxx</Fingerprint>
                  </Cert>
            </CertList>
      </CertificateListModel>
      <RequestId>FC0E34AC-0239-44A7-AB0E-800DE522C8DA</RequestId>
</DescribeCdnCertificateListResponse>
```

`JSON` format

```
{
    "CertificateListModel": {
        "Count": 2,
        "CertList": {
            "Cert": [
                {
                    "CertName": "certificate 1",
                    "Issuer": "xxx",
                    "LastTime": 1512388610,
                    "CertId": 1,
                    "Common": "test",
                    "Fingerprint": "xxx"
                },
                {
                    "CertName": "certificate 2",
                    "Issuer": "xxx",
                    "LastTime": 1512388659,
                    "CertId": 2,
                    "Common": "test",
                    "Fingerprint": "xxx"
                }
            ]
        }
    },
    "RequestId": "FC0E34AC-0239-44A7-AB0E-800DE522C8DA"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

