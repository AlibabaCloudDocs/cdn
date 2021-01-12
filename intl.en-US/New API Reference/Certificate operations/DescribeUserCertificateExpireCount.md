# DescribeUserCertificateExpireCount

Queries the number of domain names whose SSL certificates are about to expire or have already expired.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeUserCertificateExpireCount&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeUserCertificateExpireCount|The operation that you want to perform. Set the value to **DescribeUserCertificateExpireCount**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|ExpireWithin30DaysCount|Integer|0|The number of domain names whose SSL certificates are about to expires within 30 days. |
|ExpiredCount|Integer|6|The number of domain names whose SSL certificates have already expired. |
|RequestId|String|F5E8DF64-7175-4186-9B06-F002C0BBD0C5|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeUserCertificateExpireCount
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeUserCertificateExpireCount>
	  <ExpiredCount>6</ExpiredCount>
	  <ExpireWithin30DaysCount>0</ExpireWithin30DaysCount>
	  <RequestId>F5E8DF64-7175-4186-9B06-F002C0BBD0C5</RequestId>
  </DescribeUserCertificateExpireCount>
```

`JSON` format

```
{
    "ExpiredCount": 6,
    "ExpireWithin30DaysCount": 0,
    "RequestId": "F5E8DF64-7175-4186-9B06-F002C0BBD0C5"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

