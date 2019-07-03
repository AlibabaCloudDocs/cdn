# DescribeDomainCustomLogConfig {#reference3345 .reference}

调用DescribeDomainCustomLogConfig获取域名自定义日志格式配置信息。

## 调试 {#section_xr5_wp6_6i3 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainCustomLogConfig)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_ubn_32b_mgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainCustomLogConfig。|
|DomainName|String|是|域名（只支持单个查询）。|

## 返回参数 {#section_fcn_32b_mgb .section}

|名称|类型|描述|
|:-|:-|:-|
|ConfigId|String|日志配置id。|
|Tag|String|日志配置tag信息。|
|Remark|String|具体配置格式。|
|Sample|String|样例。|

## 示例 {#section_zcn_32b_mgb .section}

请求示例

``` {#codeblock_8af_cab_mal}
https://cdn.aliyuncs.com?Action=DescribeDomainCustomLogConfig&DomainName=example.com<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_4ag_qcw_zs7}
{
    "ConfigId": "25473b84-d598-498e-b148-f23d0a27df52",
    "Tag": "xxxxx",
    "Remark": "$time_iso8601_$request_method_$server_protocol.....",
    "Sample": "[9/Jun/2015:01:58:09+0800]188.165.15.75-1542\"-\"\"GET http://example.com/index.html\"2001912830MISS\"Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)",
    "RequestId": "1805F349-0A2B-41D9-B4AD-33632AFC27F1"
}
```

## 错误码 {#section_sqb_hfb_mgb .section}

|错误码|错误信息|HTTP 状态码|描述|
|:--|:---|:-------|:-|
|Config.NotFound|The domain provided doesn't belong to you or doesn't apply any custom log config, please refer to the standard log config.|404|无自定义日志配置信息。|

CDN所有API错误码，详情请参见[CDN错误码](https://error-center.aliyun.com/status/product/Cdn)。

