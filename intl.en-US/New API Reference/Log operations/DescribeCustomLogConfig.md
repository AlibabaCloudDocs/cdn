# DescribeCustomLogConfig {#reference3345 .reference}

You can call the DescribeCustomLogConfig operation to query the detailed information about a custom log configuration. You can use the ConfigId parameter to specify a custom log configuration.

## Debugging {#section_jcc_wap_prp .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCustomLogConfig) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_ubn_32b_mgb .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to DescribeCustomLogConfig.|
|ConfigId|String|Yes|The ID of the log configuration.|

## Response parameters {#section_fcn_32b_mgb .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|Tag|String|The tag information of the log configuration.|
|Remark|String|The format of the log configuration.|
|Sample|String|The sample log configuration.|

## Examples {#section_zcn_32b_mgb .section}

Sample request

``` {#codeblock_7rg_nr4_5xm}
https://cdn.aliyuncs.com? Action=DescribeCustomLogConfig?ConfigId=2df93fd7-5bbc-48c0-bae2-1ee1032d8d86<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_vf6_dg3_cq0}
{
    "Tag": "xxxxx",
    "RequestId": "F32C57AA-7BF8-49AE-A2CC-3F42390F5A16",
    "Sample": "[9/Jun/2015:01:58:09 +0800] 188.165.15.75 - 1542 \"-\" \"GEThttp: //example.com/index.html\" 200",
    "Remark": "$time_iso8601_$request_method_$server_protocol....."
}
```

## Error codes {#section_sqb_hfb_mgb .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|Config.NotFound|Config does not exist or does not belong to the current user|404|The error message returned because the specified log configuration does not exist or does not belong to you.|
|InvalidConfigId|Illegal ConfigId|403|The error message returned because the specified ConfigId parameter is invalid.|

