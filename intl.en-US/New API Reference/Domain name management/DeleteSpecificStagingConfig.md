# DeleteSpecificStagingConfig

Deletes the configurations of an accelerated domain name that is in canary release.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer.](https://api.aliyun.com/#product=Cdn&api=DeleteSpecificStagingConfig&type=RPC&version=2018-05-10)OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteSpecificStagingConfig|The operation that you want to perform. Set the value to **DeleteSpecificStagingConfig**. |
|ConfigId|String|Yes|2317|The configuration IDs. Separate multiple configuration IDs with commas \(,\). For more information about configuration IDs, see [DescribeCdnDomainStagingConfig](~~158565~~). |
|DomainName|String|Yes|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DeleteSpecificStagingConfig
&ConfigId=2317
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DeleteSpecificStagingConfigResponse>
	  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</DeleteSpecificStagingConfigResponse>
```

`JSON` format

```
{
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|The error message returned because the specified value of the FunctionName parameter is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

