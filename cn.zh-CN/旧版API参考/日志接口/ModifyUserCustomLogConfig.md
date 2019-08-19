# ModifyUserCustomLogConfig {#doc_api_Cdn_ModifyUserCustomLogConfig .reference}

调用ModifyUserCustomLogConfig接口修改用户下自定义日志配置信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=ModifyUserCustomLogConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyUserCustomLogConfig|操作接口名，系统规定参数，取值：**ModifyUserCustomLogConfig**。

 |
|ConfigId|String|是|1232|日志配置ID。

 |
|Tag|String|是|music|日志配置tag信息（不超过256个字符） 。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?Action=ModifyUserCustomLogConfig
&Tag=xxxx
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyUserCustomLogConfigResponse>
	  <RequestId>CEC1492F-EB71-4481-94CF-34BA007DC8E1</RequestId>
</ModifyUserCustomLogConfigResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"CEC1492F-EB71-4481-94CF-34BA007DC8E1"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

