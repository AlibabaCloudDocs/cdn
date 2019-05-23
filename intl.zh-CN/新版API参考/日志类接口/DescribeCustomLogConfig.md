# DescribeCustomLogConfig {#reference3345 .reference}

根据configId查询自定义日志配置详细信息。

## 请求参数 {#section_ubn_32b_mgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeCustomLogConfig。|
|ConfigId|String|是|自定义配置ID|

## 返回参数 {#section_fcn_32b_mgb .section}

|名称|类型|描述|
|:-|:-|:-|
|Tag|String|日志配置tag信息|
|Remark|String|具体配置格式|
|Sample|String|样例|

## 示例 {#section_zcn_32b_mgb .section}

请求示例

```
https://cdn.aliyuncs.com?Action=DescribeCustomLogConfig?ConfigId=2df93fd7-5bbc-48c0-bae2-1ee1032d8d86<公共请求参数>
```

返回示例

```
{
    "Tag": "xxxxx",
    "RequestId": "F32C57AA-7BF8-49AE-A2CC-3F42390F5A16",
    "Sample": "[9/Jun/2015:01:58:09 +0800] 188.165.15.75 - 1542 \"-\" \"GEThttp: //example.com/index.html\" 200",
    "Remark": "$time_iso8601_$request_method_$server_protocol....."
}
```

## 错误码 {#section_sqb_hfb_mgb .section}

|错误码|错误信息|HTTP 状态码|描述|
|:--|:---|:-------|:-|
|Config.NotFound|Config does not exist or does not belong to the current user|404|配置不存在或者不属于当前用户|
|InvalidConfigId|Illegal ConfigId|403|非法的ConfigId|

