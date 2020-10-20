# DescribeVerifyContent

Queries the ownership verification content of an accelerated domain name.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeVerifyContent&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeVerifyContent|The operation that you want to perform. Set the value to DescribeVerifyContent. |
|DomainName|String|Yes|example.com|The domain name of which the ownership was verified. You can specify only one domain name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Content|String|verify\_dffeb6610035dcb77b413a59c32cd91f|The verification content. |
|RequestId|String|34AB41F1-04A5-496F-8C8D-634BDBE6A9FB|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeVerifyContent
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeVerifyContentResponse>
  <Content>verify_dffeb6610035dcb77b413a59c32cd91f</Content>
  <RequestId>34AB41F1-04A5-496F-8C8D-634BDBE6A9FB</RequestId>
</DescribeVerifyContentResponse>
```

`JSON` format

```
{
  "Content": "verify_dffeb6610035dcb77b413a59c32cd91f",
  "RequestId": "34AB41F1-04A5-496F-8C8D-634BDBE6A9FB"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

