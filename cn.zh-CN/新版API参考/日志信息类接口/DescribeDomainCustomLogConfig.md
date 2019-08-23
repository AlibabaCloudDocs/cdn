# DescribeDomainCustomLogConfig {#doc_api_Cdn_DescribeDomainCustomLogConfig .reference}

调用DescribeDomainCustomLogConfig获取域名自定义日志格式配置信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainCustomLogConfig&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|DomainName|String|是|www.yourdomain.com|域名（只支持单个查询）。

 |
|Action|String|否|DescribeDomainCustomLogConfig|操作接口名，系统规定参数，取值：**DescribeDomainCustomLogConfig**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ConfigId|String|123|日志配置ID。

 |
|Remark|String|$time\_iso8601\_$request\_method\_$|具体配置格式。

 |
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求ID。

 |
|Sample|String|\[9/Jun/2015:01:58:09+0800\]188.165.15.75-1542\\"-\\"\\"GET http://www.aliyun.com/index.html\\|样例。

 |
|Tag|String|book|日志配置tag信息。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com/?Action=DescribeDomainCustomLogConfig
&DomainName=www.yourdomain.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainCustomLogConfigResponse>
	  <ConfigId>25473b84-d598-498e-b148-f23d0a27df52</ConfigId>
	  <Tag>xxxxx</Tag>
	  <Remark>$time_iso8601_$request_method_$server_protocol.....</Remark>
	  <Sample>[9/Jun/2015:01:58:09+0800]188.165.15.75-1542"-""GET http://www.aliyun.com/index.html"2001912830MISS"Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)</Sample>
	  <RequestId>1805F349-0A2B-41D9-B4AD-33632AFC27F1</RequestId>
</DescribeDomainCustomLogConfigResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Tag":"xxxxx",
	"RequestId":"1805F349-0A2B-41D9-B4AD-33632AFC27F1",
	"Sample":"[9/Jun/2015:01:58:09+0800]188.165.15.75-1542\"-\"\"GET http://www.aliyun.com/index.html\"2001912830MISS\"Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)",
	"ConfigId":"25473b84-d598-498e-b148-f23d0a27df52",
	"Remark":"$time_iso8601_$request_method_$server_protocol....."
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

