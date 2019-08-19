# SetIpAllowListConfig {#doc_api_Cdn_SetIpAllowListConfig .reference}

调用SetIpAllowListConfig接口设置加速域名的IP白名单。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetIpAllowListConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetIpAllowListConfig|操作接口名，系统规定参数。取值：**SetIpAllowListConfig**。

 |
|AllowIps|String|是|10.0.0.1%2F24%2C127.0.0.1%2F24|IP白名单。表示此IP列表不受限制，可以正常访问。

 |
|DomainName|String|是|www.macaron.org.cn|您的加速域名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|1C2C0CF5-C259-4B1B-98E1-E70DAC3827FA|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com?Action=SetIpAllowListConfig
&AllowIps=10.0.0.1%2F24%2C127.0.0.1%2F24
&DomainName=www.macaron.org.cn
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetIpAllowListConfigResponse>
      <RequestId>AED00EC1-32A8-4D48-BEB9-BD782AF3C6BD</RequestId>
</SetIpAllowListConfigResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

