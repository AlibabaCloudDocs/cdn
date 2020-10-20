# VerifyDomainOwner

Verifies the ownership of a specified domain name.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=VerifyDomainOwner&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|VerifyDomainOwner|The operation that you want to perform. Set the value to VerifyDomainOwner. |
|DomainName|String|Yes|example.com|The domain name of which you want to verify the ownership. You can specify only one domain name. |
|VerifyType|String|Yes|dnsCheck|The method that you want to use to verify the ownership of the specified domain name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Content|String|verify\_dffeb6610035dcb77b413a59c32cd91f|The verification content. |
|RequestId|String|34AB41F1-04A5-496F-8C8D-634BDBE6A9FB|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=VerifyDomainOwner
&DomainName=example.com
&VerifyType=dnsCheck
&<Common request parameters>
```

Sample success responses

`XML` format

```
<VerifyDomainOwnerResponse>
  <Content>verify_dffeb6610035dcb77b413a59c32cd91f</Content>
  <RequestId>34AB41F1-04A5-496F-8C8D-634BDBE6A9FB</RequestId>
</VerifyDomainOwnerResponse>
```

`JSON` format

```
{
  "Content": "verify_dffeb6610035dcb77b413a59c32cd91f",
  "RequestId": "34AB41F1-04A5-496F-8C8D-634BDBE6A9FB"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|DomainOwnerVerifyFail|Owner verification of the root domain failed.|The error message returned because you have not proven your ownership of the specified domain name. Beginning June 12, 2020, the first time that a domain name is added to Alibaba Cloud CDN, you must prove that you are the owner of the domain name. To prove the ownership, you can add a DNS record or upload the required verification file to Alibaba Cloud CDN. Then, you can call the AddCdnDomain operation to add the domain name to Alibaba Cloud CDN. For more information, see [Verify the ownership of a domain name](/intl.en-US/Quick Start/Verify the ownership of a domain name.md).|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

