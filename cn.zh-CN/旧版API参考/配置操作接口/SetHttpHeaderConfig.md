# SetHttpHeaderConfig {#doc_api_Cdn_SetHttpHeaderConfig .reference}

调用SetHttpHeaderConfig接口设置自定义http头。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetHttpHeaderConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetHttpHeaderConfig|操作接口名，系统规定参数。取值：**SetHttpHeaderConfig**。

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。

 |
|HeaderKey|String|是|Content-Type|HTTP头参数。取值：

 -   **Content-Type**
-   **Cache-Control**
-   **Content-Disposition**
-   **Content-Language**
-   **Expires**
-   **Access-Control-Allow-Origin**
-   **Access-Control-Allow-Methods**
-   **Access-Control-Allow-Headers**
-   **Access-Control-Max-Age**
-   **Access-Control-Expose-Headers**
-   **Access-Control-Allow-Credentials**

 |
|HeaderValue|String|是|application|HTTP头参数的取值。

 |
|ConfigId|Long|否|123|配置ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=SetHttpHeaderConfig
&DomainName=www.yourdomain.com
&HeaderKey=Content-Type
&HeaderValue=application
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>FC67A93B-923A-44E4-9AB8-32D8D729059E</RequestId>
	  <HostId>cdn.aliyuncs.com</HostId>
	  <Code>InvalidDomain.NotFound</Code>
	  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"FC67A93B-923A-44E4-9AB8-32D8D729059E",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidHeaderKey.ValueNotSupported|The specified value of parameter HeaderKey is not supported.|指定的HTTP头参数不合法，超出可选范围。取值：Content-Type,Cache-Control,Content-Disposition,Content-Language,Expires,Access-Control-Allow-Origin,Access-Control-Allow-Methods,Access-Control-Allow-Headers,Access-Control-Max-Age,Access-Control-Expose-Headers,Access-Control-Allow-Credentials。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

