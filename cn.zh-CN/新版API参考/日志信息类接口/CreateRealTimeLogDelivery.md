# CreateRealTimeLogDelivery {#doc_api_Cdn_CreateRealTimeLogDelivery .reference}

调用CreateRealTimeLogDelivery创建域名实时日志投递。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=CreateRealTimeLogDelivery&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateRealTimeLogDelivery|操作接口名，系统规定参数，取值：**CreateRealtimeLogDelivery**。

 |
|Domain|String|是|example.com|开启实时日志投递服务域名。

 |
|Logstore|String|是|Logstore|实时投递sls的LogStoreName。

 |
|Project|String|是|test|实时投递sls的ProjectName。

 |
|Region|String|是|cn-shanghai|实时投递sls的Region。详情请参见[实时日志投递用户Region列表](~~27232~~)。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|F32C57AA-7BF8-49AE-A2CC-9F42390F5A19|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?Action=CreateRealTimeLogDelivery
?Domain=xxx.com
&Project=test
&Logstore=test
&Region=test
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateRealTimeLogDeliveryResponse>
	  <RequestId>F32C57AA-7BF8-49AE-A2CC-9F42390F5A19</RequestId>
</CreateRealTimeLogDeliveryResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"F32C57AA-7BF8-49AE-A2CC-9F42390F5A19"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

