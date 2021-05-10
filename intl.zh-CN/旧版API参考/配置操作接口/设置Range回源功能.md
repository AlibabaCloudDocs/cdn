# 设置Range回源功能

调用SetRangeConfig设置Range回源功能。

需要源站支持Range请求，即对于HTTP请求头中包含Range字段，源站能够响应正确的206文件分片。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetRangeConfig&type=RPC&version=2014-11-11)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetRangeConfig|操作接口名，系统规定参数。取值：**SetRangeConfig**。 |
|DomainName|String|是|example.com|要开启该功能的加速域名，仅支持单个设置。 |
|Enable|String|是|On|是否配置Range回源功能。取值：

 -   **On**：开启。
-   **Off**：关闭。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=SetRangeConfig
&DomainName=example.com
&Enable=On
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<SetRangeConfigResponse>
      <RequestId>AED00EC1-32A8-4D48-BEB9-BD782AF3C6BD</RequestId>
</SetRangeConfigResponse>
```

`JSON`格式

```
{
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidEnable.ValueNotSupported|The specified value of parameter Enable is not supported.|指定的配置项值不合法，只能是on或off。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cdn)查看更多错误码。

