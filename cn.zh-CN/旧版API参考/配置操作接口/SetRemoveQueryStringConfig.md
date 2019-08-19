# SetRemoveQueryStringConfig {#doc_api_Cdn_SetRemoveQueryStringConfig .reference}

调用SetRemoveQueryStringConfig接口设置过滤参数功能（删除）。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetRemoveQueryStringConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetRemoveQueryStringConfig|操作接口名，系统规定参数。取值：**SetRemoveQueryStringConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |
|AliRemoveArgs|String|是|time|删除指定的参数，多个参数之间用空格隔开，剩余参数将作为hashkey中URL args部分。

 |
|KeepOssArgs|String|否|off|取值范围：

 -   **on**：回源保留所有参数。
-   **off**：关闭。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com?Action=SetRemoveQueryStringConfig
&DomainName=www.macaron.org.cn
&AliRemoveArgs=time
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetRemoveQueryStringConfigResponse>
	  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</SetRemoveQueryStringConfigResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The input parameter aliRemoveArgs that is mandatory for processing this request is not supplied.|参数aliRemoveArgs为必填。|
|400|InvalidKeepOssArgs.ValueNotSupported|The specified value of parameter KeepOssArgs is not supported.|KeepOssArgs 不支持该参数值。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

