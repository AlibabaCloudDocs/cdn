# SetSourceHostConfig {#doc_api_Cdn_SetSourceHostConfig .reference}

调用SetSourceHostConfig接口设置回源host功能。

**说明：** 若源站为OSS域名，需将OSS域名设置为回源host（即源站域名），才能正常回源。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetSourceHostConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetSourceHostConfig|操作接口名，系统规定参数。取值：**SetSourceHostConfig**。

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。

 |
|Enable|String|否|On|是否打开自定义host配置。取值：

 -   **on**
-   **off**

 默认值：**on**。

 |
|BackSrcDomain|String|否|www.aliyun.com|自定义回源host，如果Enable是on的话，此参数为必传。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com/?Action=SetSourceHostConfig
&BackSrcDomain=example.com
&DomainName=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetSourceHostConfigResponse>
      <RequestId>AED00EC1-32A8-4D48-BEB9-BD782AF3C6BD</RequestId>
</SetSourceHostConfigResponse>
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
|400|InvalidParameter|The specified value of parameter "Enable" is not valid.|参数“Enable”的值无效。|
|400|MissingBackSrcDomain|The input parameter BackSrcDomain that is mandatory for processing this request is not supplied.|参数BackSrcDomain为必填。|
|400|InvalidBackSrcDomain.Malformed|Specified BackSrcDomain is malformed.|回源域名格式BackSrcDomain不合法。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

