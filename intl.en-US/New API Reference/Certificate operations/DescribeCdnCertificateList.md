# DescribeCdnCertificateList

You can call the DescribeCdnCertificateList operation to query the certificates of a specific CDN domain.

## Debugging

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnCertificateList) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to DescribeCdnCertificateList.|
|DomainName|String|No|The name of the CDN domain of which the certificates are queried.|

## Response parameters

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestId|String|The ID of the request.|
|CertificateListModel|CertificateListModel|The certificate information.|

Parameters in CertificateListModel

|Parameter|Type|Description|
|:--------|:---|:----------|
|Count|Integer|The number of certificates returned.|
|CertList|Cert|The detailed information about each certificate.|

Parameters in Cert

|Parameter|Type|Description|
|:--------|:---|:----------|
|CertName|String|The name of the certificate.|
|CertId|Long|The ID of the certificate.|
|Fingerprint|String|The fingerprint of the certificate.|
|Common|String|The common name of the certificate.|
|Issuer|String|The CA that issued the certificate.|
|LastTime|Long|The time when the certificate was issued.|

## Examples

Sample request

```
http://cdn.aliyuncs.com?Action=DescribeCdnCertificateList&DomainName=xxx&<Common request parameters>
```

Sample success response

`JSON` format

```
{
    "CertificateListModel": {
        "Count": 2,
        "CertList": {
            "Cert": [
                {
                    "CertName": "certificate1",
                    "Issuer": "xxx",
                    "LastTime": 1512388610,
                    "CertId": xxx,
                    "Common": "test",
                    "Fingerprint": "xxx"
                },
                {
                    "CertName": "certificate2",
                    "Issuer": "xxx",
                    "LastTime": 1512388659,
                    "CertId": xxx,
                    "Common": "test",
                    "Fingerprint": "xxx"
                }
            ]
        }
    },
    "RequestId": "FC0E34AC-0239-44A7-AB0E-800DE522C8DA"
}
```

This table lists the error codes that the operation can return. For more information, see [Error codes](https://error-center.aliyun.com/status/product/Cdn).

