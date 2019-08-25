# ModifyRealtimeLogDelivery {#doc_api_Cdn_ModifyRealtimeLogDelivery .reference}

调用ModifyRealtimeLogDelivery更改域名实时日志投递。一个域名同时仅支持投递单个logstore。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=ModifyRealtimeLogDelivery&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyRealtimeLogDelivery|操作接口名，系统规定参数，取值：**ModifyRealtimeLogDelivery**。

 |
|Domain|String|是|example.com|修改实时日志投递的域名。

 |
|Logstore|String|是|LogstoreName|实时投递sls的ProjectName。

 |
|Project|String|是|ProjectName|实时投递sls的LogStoreName。

 |
|Region|String|是|ch-shanghai|实时投递sls的Region，详情请参见[实时日志投递用户Region列表](~~27232~~)。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|9732E117-8A37-49FD-A36F-ABBB87556CA7|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?Action=ModifyRealtimeLogDelivery
&Domain=xxx.com
&Project=test
&Logstore=test
&Region=test
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyRealtimeLogDeliveryResponse>
	  <RequestId>9732E117-8A37-49FD-A36F-ABBB87556CA7</RequestId>
</ModifyRealtimeLogDeliveryResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"9732E117-8A37-49FD-A36F-ABBB87556CA7"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

