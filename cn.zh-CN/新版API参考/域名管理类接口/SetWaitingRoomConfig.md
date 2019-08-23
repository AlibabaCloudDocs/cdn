# SetWaitingRoomConfig {#doc_api_Cdn_SetWaitingRoomConfig .reference}

调用SetWaitingRoomConfig设置waiting\_room功能，只支持全站加速类型域名。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetWaitingRoomConfig&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetWaitingRoomConfig|操作接口名，系统规定参数，取值：**SetWaitingRoomConfig**。

 |
|AllowPct|Integer|是|30|允许回源比例，取值范围：**0**-**100**。

 |
|DomainName|String|是|example.com|您的加速域名。

 |
|GapTime|Integer|是|20|离开排队后，跳过排队时长，单位：秒。

 |
|MaxTimeWait|Integer|是|30|进入排队后，排队时长，单位：秒。

 |
|WaitUri|String|是|xxx|开启WaitingRoom功能的URI正则字符串。

 |
|WaitUrl|String|是|WaitUrl|排队等待页面URL。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com/?Action=SetWaitingRoomConfig
&DomainName=xxx
&WaitUri=xxx
&AllowPct=30
MaxTimeWait=20
&GapTime=30
&WaitUrl=xxx
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetWaitingRoomConfigResponse>
      <RequestId>AED00EC1-32A8-4D48-BEB9-BD782AF3C6BD</RequestId>
</SetWaitingRoomConfigResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

