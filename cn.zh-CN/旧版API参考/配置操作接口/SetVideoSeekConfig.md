# SetVideoSeekConfig {#doc_api_Cdn_SetVideoSeekConfig .reference}

调用SetVideoSeekConfig接口设置拖拽播放功能。

**说明：** 

-   需要源站支持range请求，即对于HTTP请求头中包含Range字段，源站能够响应正确的206文件分片。
-   目前支持文件格式有：MP4和FLV。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetVideoSeekConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetVideoSeekConfig|操作接口名，系统规定参数。取值：**SetVideoSeekConfig**。

 |
|DomainName|String|是|www.macaron.org.cn|加速域名。

 |
|Enable|String|是|On|是否配置拖拽播放功能。取值：

 -   **On**
-   **Off**

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com/?Action=SetVideoSeekConfig
&Enable=on
&DomainName=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetVideoSeekConfigResponse>
      <RequestId>AED00EC1-32A8-4D48-BEB9-BD782AF3C6BD</RequestId>
</SetVideoSeekConfigResponse>
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
|400|InvalidEnable.ValueNotSupported|The specified value of parameter Enable is not supported.|指定的配置项值不合法，只能是on或off。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

