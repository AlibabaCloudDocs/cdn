# DeleteSpecificConfig

Deletes specific configurations of an accelerated domain name.

You can call this operation up to 30 times per second with each account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DeleteSpecificConfig&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteSpecificConfig|The operation that you want to perform. Set the value to **DeleteSpecificConfig**. |
|ConfigId|String|Yes|2317|The ID of the configuration that you want to delete. You can specify multiple configuration IDs and separate them with commas \(,\). You can call the operation [DescribeCdnDomainConfigs](~~90924~~) to query the configuration IDs. |
|DomainName|String|Yes|example.com|The accelerated domain name. Only one domain name is supported. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DeleteSpecificConfig
&DomainName=example.com
&ConfigId=2317
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DeleteSpecificConfigResponse>
      <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</DeleteSpecificConfigResponse>
```

`JSON` format

```
{
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|The error message returned because the specified value of the FunctionName parameter is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

