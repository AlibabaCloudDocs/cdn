# SetConfigOfVersion

Modifies settings of your Content Delivery Network \(CDN\) service.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=SetConfigOfVersion&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|SetConfigOfVersion|The operation that you want to perform. Set the value to **SetConfigOfVersion**. |
|FunctionArgs|String|Yes|\[\{"argName":"xxxx","argValue":"xxxx"\}\]|The parameter that specifies the feature. |
|VersionId|String|Yes|testVersionId|The ID of the version. |
|ConfigId|String|No|98|The ID of the configuration file. |
|FunctionId|Long|No|98|The ID of the feature. You can set either FunctionId or FunctionName. |
|FunctionName|String|No|testFunctionName|The complete name of the feature. You can set either FunctionId or FunctionName. |
|FunctionMatches|String|No|argName|The name used to match a feature. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|15M66C7B-671A-4297-9187-2Q4477247A75|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=SetConfigOfVersion
&VersionId=testVersionId
&ConfigId=98
&FunctionName=testFunctionName
&FunctionArgs=[{"argName":"xxxx","argValue":"xxxx"}]
&<Common request parameters>
```

Sample success responses

`XML` format

```
<SetConfigOfVersionResponse>
  <RequestId>15M66C7B-671A-4297-9187-2Q4477247A75</RequestId>
</SetConfigOfVersionResponse>
```

`JSON` format

```
{
    "RequestId": "15M66C7B-671A-4297-9187-2Q4477247A75"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidFunctions.Malformed|The specified Functions is incorrectly formatted.|The error message returned because the format of the configuration is invalid.|
|400|InvalidHeaderKey.ValueNotSupported|The specified value of parameter HeaderKey is not supported.|The error message returned because the specified HTTP request header field is invalid. Valid values: Content-Type, Cache-Control, Content-Disposition, Content-Language, Expires, Access-Control-Allow-Origin, Access-Control-Allow-Methods, Access-Control-Allow-Headers, Access-Control-Max-Age, Access-Control-Expose-Headers, and Access-Control-Allow-Credentials.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

