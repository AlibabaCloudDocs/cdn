# DescribeDomainCustomLogConfig

Queries the custom log configuration of an accelerated domain name.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainCustomLogConfig&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeDomainCustomLogConfig|The operation that you want to perform. Set the value to **DescribeDomainCustomLogConfig**. |
|DomainName|String|Yes|www.yourdomain.com|The accelerated domain name. You can specify only one domain name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|ConfigId|String|123|The ID of the log configuration. |
|Remark|String|$time\_iso8601\_$request\_method\_$|The format of the log configuration. |
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|The ID of the request. |
|Sample|String|\[9/Jun/2015:01:58:09+0800\]188.165.15.75-1542\\"-\\"\\"GET http://www.aliyun.com/index.html\\|A sample log configuration. |
|Tag|String|book|The tag information about the log configuration. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeDomainCustomLogConfig
&DomainName=www.yourdomain.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainCustomLogConfigResponse>
	  <ConfigId>25473b84-d598-498e-b148-f23d0a27df52</ConfigId>
	  <Tag>xxxxx</Tag>
	  <Remark>$time_iso8601_$request_method_$server_protocol..... </Remark>
	  <Sample>[9/Jun/2015:01:58:09+0800]188.165.15.75-1542"-""GET http://www.aliyun.com/index.html"2001912830MISS"Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)</Sample>
	  <RequestId>1805F349-0A2B-41D9-B4AD-33632AFC27F1</RequestId>
</DescribeDomainCustomLogConfigResponse>
```

`JSON` format

```
{
    "ConfigId": "25473b84-d598-498e-b148-f23d0a27df52",
    "Tag": "xxxxx",
    "Remark": "$time_iso8601_$request_method_$server_protocol.....",
    "Sample": "[9/Jun/2015:01:58:09+0800]188.165.15.75-1542\"-\"\"GET http://www.aliyun.com/index.html\"2001912830MISS\"Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)",
    "RequestId": "1805F349-0A2B-41D9-B4AD-33632AFC27F1"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

