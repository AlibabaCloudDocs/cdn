# DescribeCdnDomainStagingConfig

Queries the configurations of multiple features for a domain name in the staging environment.

The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainStagingConfig&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnDomainStagingConfig|The operation that you want to perform. Set the value to **DescribeCdnDomainStagingConfig**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name. |
|FunctionNames|String|Yes|aliauth|The names of the features to query. Separate multiple features with commas \(,\). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainConfigs|Array of DomainConfig| |The configurations of the accelerated domain name. |
|ConfigId|String|6xx5|The ID of the configuration. |
|FunctionArgs|Array of FunctionArg| |The description of each feature. |
|ArgName|String|auth\_type|The key of the parameter. |
|ArgValue|String|req\_auth|The value of the parameter. |
|FunctionName|String|aliauth|The name of the feature. |
|Status|String|success|The status of the configuration.

 -   testing: The configuration is being verified.
-   configuring: The configuration is being applied.
-   success: The configuration has been applied.
-   failed: The task creation has failed. |
|RequestId|String|C80705BF-0F76-41FA-BAD1-5B59296A4E59|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeCdnDomainStagingConfig
&DomainName=example.com
&FunctionNames=aliauth
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnDomainStagingConfigResponse>
      <RequestId>C80705BF-0F76-41FA-BAD1-5B59296A4E59</RequestId>
      <DomainConfigs>
            <Status>success</Status>
            <FunctionArgs>
                  <ArgName>auth_type</ArgName>
                  <ArgName>ali_auth_dual</ArgName>
                  <ArgValue>req_auth</ArgValue>
                  <ArgValue>on</ArgValue>
            </FunctionArgs>
            <ConfigId>6xx5</ConfigId>
            <FunctionName>aliauth</FunctionName>
      </DomainConfigs>
</DescribeCdnDomainStagingConfigResponse>
```

`JSON` format

```
{
    "RequestId": "C80705BF-0F76-41FA-BAD1-5B59296A4E59",
    "DomainConfigs": {
        "Status": "success",
        "FunctionArgs": {
            "ArgName": [
                "auth_type",
                "ali_auth_dual"
                 ],
                "ArgValue": [
                    "req_auth",
                    "on"
                ]
            },
         "ConfigId": "6xx5",
         "FunctionName": "aliauth"
        }
    
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|The error message returned because the specified value of the FunctionName parameter is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

