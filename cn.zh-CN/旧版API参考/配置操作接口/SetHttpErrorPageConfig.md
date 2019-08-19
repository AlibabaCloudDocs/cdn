# SetHttpErrorPageConfig {#doc_api_Cdn_SetHttpErrorPageConfig .reference}

调用SetHttpErrorPageConfig接口设置加速域名自定义错误页面跳转。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetHttpErrorPageConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetHttpErrorPageConfig|操作接口名，系统规定参数。取值：**SetHttpErrorPageConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |
|ErrorCode|String|是|500|自定义错误码。

 |
|PageUrl|String|是|http%3A%2F%2Fwww.aliyun.com%2Fnotfound%2F|自定义发生错误后跳转到页面URL（该加速域名下的完整路径）。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|A32554F3-F478-4B7F-9FA5-2A41ED2F3B2F|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com?Action=SetHttpErrorPageConfig
&DomainName=www.macaron.org.cn
&ErrorCode=500
&PageUrl=http%3A%2F%2Fwww.aliyun.com%2Fnotfound%2F
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetHttpErrorPageConfigResponse>
	  <RequestId>A32554F3-F478-4B7F-9FA5-2A41ED2F3B2F</RequestId>
</SetHttpErrorPageConfigResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"A32554F3-F478-4B7F-9FA5-2A41ED2F3B2F"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The specified value of parameter DomainName can not be empty.|参数DomainName不能为空。|
|400|MissingParameter|The specified value of parameter ErrorCode can not be empty.|参数ErrorCode不能为空。|
|400|MissingParameter|The specified value of parameter PageUrl can not be empty.|参数PageUrl不能为空。|
|400|InvalidPageUrl.Malformed|The specified value of parameter PageUrl is not malformed.|参数PageUrl格式错误。|
|400|InvalidErrorCode.Malformed|The specified value of parameter ErrorCode is not malformed.|参数ErrorCode 格式错误。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

