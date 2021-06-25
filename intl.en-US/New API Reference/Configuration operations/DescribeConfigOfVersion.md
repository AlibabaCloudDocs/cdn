# DescribeConfigOfVersion

Queries the configurations of a specific configuration group for your Content Delivery Network \(CDN\) service.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeConfigOfVersion&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeConfigOfVersion|The operation that you want to perform. Set the value to **DescribeConfigOfVersion**. |
|VersionId|String|Yes|testID|The ID of the version. |
|FunctionId|Integer|No|98|The ID of the feature. |
|FunctionName|String|No|testFunctionName|The name of the feature. |
|GroupId|Long|No|123456789|The ID of the configuration group. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|AJ5E90E4-977E-497C-81B5-9EB2C1381C4F|The ID of the request. |
|VersionConfigs|Array of VersionConfig| |The configurations. |
|VersionConfig| | | |
|ConfigId|String|98|The ID of the configuration group. |
|FunctionArgs|Array of FunctionArg| |The details about the configurations. |
|FunctionArg| | | |
|ArgName|String|aah|The key of the parameter. |
|ArgValue|String|6|The value of the parameter. |
|FunctionName|String|testFunctionName|The name of the feature. |
|Status|String|success|The status of the configuration group. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeConfigOfVersion
&VersionId=testID
&FunctionId=98
&FunctionName=testFunctionName
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeConfigOfVersionResponse>
  <RequestId>AJ5E90E4-977E-497C-81B5-9EB2C1381C4F</RequestId>
  <VersionConfigs>
        <VersionConfig>
              <Status>success</Status>
              <FunctionArgs>
                    <FunctionArg>
                          <ArgName>aah</ArgName>
                          <ArgValue>6</ArgValue>
                    </FunctionArg>
                    <FunctionArg>
                          <ArgName>test_args</ArgName>
                          <ArgValue>testValue</ArgValue>
                    </FunctionArg>
                    <ConfigId>98</ConfigId>
                    <FunctionName>testFunctionName</FunctionName>
              </FunctionArgs>
        </VersionConfig>
  </VersionConfigs>
</DescribeConfigOfVersionResponse>
```

`JSON` format

```
{
	"RequestId": "AJ5E90E4-977E-497C-81B5-9EB2C1381C4F",
	"VersionConfigs": {
		"VersionConfig": [{
			"Status": "success",
			"FunctionArgs": {
				"FunctionArg": [{
						"ArgName": "aah",
						"ArgValue": "6"
					},
					{
						"ArgName": "test_args",
						"ArgValue": "testValue"
					}

				],
				"ConfigId": "98",
				"FunctionName": "testFunctionName"
			}
		}]
	}
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|The error message returned because the specified value of the FunctionName parameter is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

