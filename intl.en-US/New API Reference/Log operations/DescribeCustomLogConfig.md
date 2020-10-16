# DescribeCustomLogConfig

Queries the detailed information about a custom log configuration.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCustomLogConfig&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCustomLogConfig|The operation that you want to perform. Set the value to **DescribeCustomLogConfig**. |
|ConfigId|String|Yes|123|The ID of the custom configuration. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Remark|String|$time\_iso8601\_$request\_method\_$|The format of the log configuration. |
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|The ID of the request. |
|Sample|String|"\[9/Jun/2015:01:58:09 +0800\] 188.165.15.75 - 1542 \\"-\\" \\"GEThttp: //www.aliyun.com/index.html\\" 200|A sample log configuration. |
|Tag|String|img1|The tag information about the log configuration. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeCustomLogConfig
&ConfigId=123
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCustomLogConfigResponse>
      <Tag>xxxxx</Tag>
      <RequestId>F32C57AA-7BF8-49AE-A2CC-3F42390F5A16</RequestId>
      <Sample>[9/Jun/2015:01:58:09 +0800] 188.165.15.75 - 1542 "-" "GEThttp: //www.aliyun.com/index.html" 200</Sample>
      <Remark>$time_iso8601_$request_method_$server_protocol..... </Remark>
</DescribeCustomLogConfigResponse>
```

`JSON` format

```
{ "Tag": "xxxxx", "RequestId": "F32C57AA-7BF8-49AE-A2CC-3F42390F5A16", "Sample": "[9/Jun/2015:01:58:09 +0800] 188.165.15.75 - 1542 \"-\" \"GEThttp: //www.aliyun.com/index.html\" 200", "Remark": "$time_iso8601_$request_method_$server_protocol....." }
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

