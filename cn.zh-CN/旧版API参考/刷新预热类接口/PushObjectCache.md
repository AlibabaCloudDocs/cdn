# PushObjectCache {#doc_api_Cdn_PushObjectCache .reference}

调用PushObjectCache接口将源站的内容主动预热到L2 Cache节点上。

首次访问可直接命中缓存，缓解源站压力。支持post请求，参数用form表单。

限制条件：

-   同一个ID每天最多提交刷新预热类请求数量：2000条URL。目前不支持目录级别的预热。
-   刷新预热类接口包含**RefreshObjectCaches** 刷新接口和 **PushObjectCache**预热接口。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=PushObjectCache&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|PushObjectCache|操作接口名，系统规定参数。取值：**PushObjectCache**。

 |
|ObjectPath|String|是|abc.com/image/1.png|输入示例：abc.com/image/1.png，多个URL之间需要用换行符（\\n或\\r\\n）分隔。

 |
|Area|String|否|domestic|预热区域。取值：

 -   **domestic**
-   **overseas**

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PushTaskId|String|95248880|预热返回的任务ID，多个任务ID用逗号（,）分隔。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com?Action=PushObjectCache
&ObjectPath=abc.com/image/1.png	
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PushObjectCacheResponse>
    <PushTaskId>95250421</PushTaskId>
    <RequestId>5FF9B16E-FBAC-48E5-9052-65B5F0184DB3</RequestId>
</PushObjectCacheResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PushTaskId":"95248880",
	"RequestId":"E5BD4B50-7A02-493A-AE0B-97B9024B4135"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|QuotaExceeded.Refresh|You've exceeded the prescribed refresh limits.|超出当日刷新限制。今日刷新数已用完。您可以通过刷新接口查询今日的刷新次数。|
|400|InvalidObjectPath.Malformed|The specific value of parameter ObjectPath is malformed.|参数ObjectPath值格式错误。输入示例：abc.com/image/1.png。多个URL之间需要用换行符（\\n 或 \\r\\n）分隔。|
|400|InvalidExtensiveDomain.ValueNotSupported|Extensive domain not supported.|该操作不支持泛域名。|
|403|PreloadQueueFull|Preload queue is full, please try again later!|预加载队列已满，请您稍后再试。|
|400|InvalidObjectPath.Size.Malformed|The size of ObjectPath is bigger than 1000.|预热url个数请勿超过1000.|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

