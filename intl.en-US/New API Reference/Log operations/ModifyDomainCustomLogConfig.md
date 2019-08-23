# ModifyDomainCustomLogConfig {#reference3345 .reference}

You can call the ModifyDomainCustomLogConfig operation to modify a custom log configuration for a CDN domain.

## Debugging {#section_7nk_2et_j64 .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=ModifyDomainCustomLogConfig) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_ubn_32b_mgb .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to ModifyDomainCustomLogConfig.|
|DomainName|String|Yes|The name of the CDN domain.|
|ConfigId|String|Yes|The ID of the log configuration.|

## Response parameters {#section_fcn_32b_mgb .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestID|String|The ID of the request.|

## Examples {#section_zcn_32b_mgb .section}

Sample request

``` {#codeblock_e7r_6tj_3iv}
https://cdn.aliyuncs.com?Action=ModifyDomainCustomLogConfig&DomainName=xxx&ConfigId=xxx&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_9mh_mi4_s5q}
{
  "RequestId": "15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## Error codes {#section_sqb_hfb_mgb .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|InvalidConfigId|Invalid configId, configId not found or doesn't belong to current user.|404|The error message returned because the specified log configuration was not defined by the current user or does not exist.|

