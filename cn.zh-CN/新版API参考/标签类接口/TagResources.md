# TagResources {#doc_api_Cdn_TagResources .reference}

调用TagResources资源打标接口。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=TagResources&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|TagResources|操作接口名，系统规定参数，取值：**TagResources**。

 |
|ResourceId.N|RepeatList|是|example.com|资源ID，CDN为域名，N的取值范围为**1**~**50**。

 |
|ResourceType|String|是|DOMAIN|固定值：**DOMAIN**。

 |
|RegionId|String|否|ch-shanghai|地域ID。

 |
|Tag.N.Key|String|否|env|标签键。N的取值范围为**1**~**20**。

 |
|Tag.N.Value|String|否|value|标签键。N的取值范围为**1**~**20**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|97C68796-EB7F-4D41-9D5B-12B909D76508|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com/?Action=TagResoruces
&ResourceId.1=example.com
&ResourceType=DOMAIN
&Tag.1.Key=env
&Tag.1.Value=''
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<TagResourcesResponse>
	  <RequestId>97C68796-EB7F-4D41-9D5B-12B909D76508</RequestId>
</TagResourcesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

