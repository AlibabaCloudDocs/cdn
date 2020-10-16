# ListUserCustomLogConfig

Queries all custom log configurations under your Alibaba Cloud account.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ListUserCustomLogConfig&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ListUserCustomLogConfig|The operation that you want to perform. Set the value to **ListUserCustomLogConfig**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|ConfigIds|List|c3bb2c78-2915-4d5a-b6a1-557789255555|The ID of the log configuration. |
|RequestId|String|95D5B69F-8AEC-419B-8F3A-612B35032B0D|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=ListUserCustomLogConfig
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ListUserCustomLogConfigResponse>
	  <RequestId>95D5B69F-8AEC-419B-8F3A-612B35032B0D</RequestId>
	  <ConfigIds>
		    <ConfigId>c3bb2c78-2915-4d5a-b6a1-557789255555</ConfigId>
		    <ConfigId>25473b84-d598-498e-b148-f23d0a255555</ConfigId>
		    <ConfigId>1f1e6c6e-6701-4193-ae4d-54bf3e555555</ConfigId>
	  </ConfigIds>
</ListUserCustomLogConfigResponse>
```

`JSON` format

```
{
    "RequestId": "95D5B69F-8AEC-419B-8F3A-612B35032B0D",
    "ConfigIds": {
        "ConfigId": [
            "c3bb2c78-2915-4d5a-b6a1-557789255555",
            "25473b84-d598-498e-b148-f23d0a255555",
            "1f1e6c6e-6701-4193-ae4d-54bf3e555555"
        ]
    }
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

