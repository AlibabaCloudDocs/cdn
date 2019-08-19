# SetHttpsOptionConfig {#doc_api_Cdn_SetHttpsOptionConfig .reference}

调用SetHttpsOptionConfig接口设置域名的HTTP2.0开关。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetHttpsOptionConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetHttpsOptionConfig|操作接口名，系统规定参数。取值：**SetHttpsOptionConfig**。

 |
|DomainName|String|是|xxx|域名。

 |
|Http2|String|是|on|HTTP2.0开关。取值：

 -   **on**
-   **off**

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|6649A92B-F105-48A0-BC94-E5BB38570652|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com/?Action=SetHttpsOptionConfig
&DomainName=xxx
&Http2=on
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetHttpsOptionConfigResponse>
      <RequestId>AED00EC1-32A8-4D48-BEB9-BD782AF3C6BD</RequestId>
</SetHttpsOptionConfigResponse>
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
|400|MissingParameter|The specified value of parameter DomainName can not be empty.|参数DomainName不能为空。|
|400|HttpsNotEnabled|Please open https first.|请先开通HTTPS安全加速功能。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

