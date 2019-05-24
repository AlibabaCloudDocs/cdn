# SetReqAuthConfig {#doc_api_Cdn_SetReqAuthConfig .reference}

调用SetReqAuthConfig接口设置加速域名的访问鉴权配置。

-   [配置URL鉴权](https://helpcdn.aliyun.com/document_detail/85117.html)
-   [python版本的鉴权代码示例](https://helpcdn.aliyun.com/document_detail/85116.html)

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=SetReqAuthConfig)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetReqAuthConfig|操作接口名，系统规定参数。取值：**SetReqAuthConfig**。

 |
|AuthType|String|是|no\_auth|鉴权类型。取值：

 -   **no\_auth**：关闭
-   **type\_a**：A方式
-   **type\_b**：B方式
-   **type\_c**：C方式
-   **type\_d**：D方式
-   **type\_e**：E方式

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。

 |
|AuthRemoteDesc|String|否|aaa|模式字符串。

 |
|Key1|String|否|fd8eqw3Q|主鉴权key。输入大小写字母或数字，长度1到64位。

 |
|Key2|String|否|v83ka2np|副鉴权Key。输入大小写字母或数字，长度1到64位。

 |
|TimeOut|String|否|2400|有效时间，输入数字。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetReqAuthConfig
&AuthType=no_auth
&DomainName=www.yourdomain.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>B3F26442-6169-48BA-B691-35669A32AFF0</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidAuthType.ValueNotSupported</Code>
  <Message>The specified value of parameter AuthType is not supported.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The specified value of parameter AuthType is not supported.",
	"RequestId":"B3F26442-6169-48BA-B691-35669A32AFF0",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidAuthType.ValueNotSupported"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidTimeOut.Malformed|The specified value of parameter TimeOut is malformed.|参数TimeOut格式错误，请检查更新后重试。|
|400|InvalidTimeOut.ValueNotSupported|The specified value of parameter TimeOut is not supported.|TIMEOUT参数格式不支持。|
|400|InvalidAuthType.ValueNotSupported|The specified value of parameter AuthType is not supported.|不支持参数AuthType。|
|400|InvalidKey1.MissingParameter|The parameter Key1 is missing.|参数Key1 不存在。|
|400|InvalidKey1.Malformed|The parameter Key1 is malformed.|参数Key1 格式错误。|
|400|InvalidKey2.Malformed|The parameter Key2 is malformed.|参数Key2 格式错误。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

