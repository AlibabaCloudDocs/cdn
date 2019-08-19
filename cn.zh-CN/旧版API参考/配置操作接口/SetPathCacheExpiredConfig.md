# SetPathCacheExpiredConfig {#doc_api_Cdn_SetPathCacheExpiredConfig .reference}

调用SetPathCacheExpiredConfig接口修改目录过期配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetPathCacheExpiredConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetPathCacheExpiredConfig|操作接口名，系统规定参数。取值：**SetPathCacheExpiredConfig**。

 |
|CacheContent|String|是|/static/html/|填写路径。

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。

 |
|TTL|String|是|600|缓存时间设置。单位：秒。

 |
|Weight|String|否|22|该配置权重值。

 取值范围：1~99。数值越大, 优先级越高。

 默认值：1。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com/?Action=SetPathCacheExpiredConfig
&CacheContent=%2Fstatic%2Fhtml%2F
&DomainName=example.com
&TTL=600
&Weight=50
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetPathCacheExpiredConfigResponse>
      <RequestId>AED00EC1-32A8-4D48-BEB9-BD782AF3C6BD</RequestId>
</SetPathCacheExpiredConfigResponse>
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
|400|InvalidCacheContent.Malformed|The specified value of parameter CacheContent is malformed.|缓存配置地址输入不符合规范。|
|400|InvalidWeight.Malformed|The specified value of parameter Weight is malformed.|指定的权重值不合法，格式错误。|
|400|InvalidWeight.ValueNotSupported|The specified value of parameter Weight is not supported.|指定的权重值不合法，超出可选范围。|
|400|InvalidTTL.Malformed|The specified value of parameter TTL is malformed.|参数TTL的参数格式错误，请检查更新后重试。|
|400|InvalidTTL.ValueNotSupported|The specified value of parameter TTL is not supported.|TTL的参数格式不支持。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

