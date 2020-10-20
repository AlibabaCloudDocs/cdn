# SetCdnDomainStagingConfig

Configures a domain name to be accelerated in the staging environment.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer.](https://api.aliyun.com/#product=Cdn&api=SetCdnDomainStagingConfig&type=RPC&version=2018-05-10)OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|SetCdnDomainStagingConfig|The operation that you want to perform. Set the value to **DescribeCdnDomainConfigs**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name. |
|Functions|String|Yes|\[\{"functionArgs":\[\{"argName":"enable","argValue":"on"\},\{"argName":"pri","argValue":"1"\},\{"argName":"rule","argValue":"xxx"\}\],"functionName":"edge\_function"\}\]|A list of features in the following format:

 ```

[{"functionArgs":[{"argName":"Parameter key","argValue":"Parameter value"},{"argName":"xx","argValue":"xx"}],"functionName": Feature name"}]

```

 You can specify one or more parameters. Separate multiple parameters with commas \(,\). |

Some features, such as EdgeScript functions \(edge\_function\), support more than one configuration record. To update one of the configuration records, set the configId parameter to specify the record.

```

[{"functionArgs":[{"argName":"enable","argValue":"on"},{"argName":"pri","argValue":"1"},{"argName":"rule","argValue":"yyy"}],"ConfigId":123456,"functionName":"edge_function"}]

```

Note: Set parameter values in the format of a string.

|Feature name

|Parameter |
|--------------|-----------|
|edge\_function: EdgeScript functions

|Required parameters:

 rule: the domain-specific language \(DSL\) script.

 pri: the priority of the script.

 enable: specifies whether to enable the script. Valid values: on and off.

 Optional parameters:

 name: the name of the script. The name can contain only letters and underscores \(\_\).

 pos: specifies whether to execute the script at the start or end of the request processing pipeline.

 brk: after the rule is hit, the subsequent rules at the specified position are skipped.

 option: an extension used to perform response header debugging.

 grammar: an extension used to specify the scripting language. Valid values: es2 and js. You can also leave this parameter empty.

 jsmode: an extension used to manage the domain name whitelist in JavaScript. Valid value: redirect and bypass. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=SetCdnDomainStagingConfig
&DomainName=example.com
&Functions=[{"functionArgs":[{"argName":"enable","argValue":"on"},{"argName":"pri","argValue":"1"},{"argName":"rule","argValue":"xxx"}],"functionName":"edge_function"}]
&<Common request parameters>
```

Sample success responses

`XML` format

```
<SetCdnDomainStagingConfigResponse>
      <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</SetCdnDomainStagingConfigResponse>
```

`JSON` format

```
{
  "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368" 
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

