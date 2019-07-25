# BatchDeleteCdnDomainConfig {#doc_api_Cdn_BatchDeleteCdnDomainConfig .reference}

调用BatchDeleteCdnDomainConfig接口删除域名配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=BatchDeleteCdnDomainConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchDeleteCdnDomainConfig|操作接口名，系统规定参数。取值：**BatchDeleteCdnDomainConfig**。

 |
|DomainNames|String|是|www.macaron.org.cn,xxx.org.com|您的加速域名，多个用英文半角逗号分隔。

 |
|FunctionNames|String|是|referer\_white\_list\_set,https\_force|功能列表名称，用逗号分隔。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|该条任务请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=BatchDeleteCdnDomainConfig
&DomainNames=www.macaron.org.cn,xxx.org.com
&FunctionNames=referer_white_list_set,https_force
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
	  <RequestId>4F001F79-F67A-43DF-B512-BB4DFB7109FB</RequestId>
	  <HostId>cdn.aliyuncs.com</HostId>
	  <Code>InvalidDomain.NotFound</Code>
	  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"4F001F79-F67A-43DF-B512-BB4DFB7109FB",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|此方法不支持。|
|400|DeleteFunctionFailed|Batch delete functions failed.|批量删除功能失败。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

