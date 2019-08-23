# PushObjectCache {#doc_api_Cdn_PushObjectCache .reference}

调用PushObjectCache将源站的内容主动预热到L2 Cache节点上，您首次访问可直接命中缓存，缓解源站压力。

支持post请求，参数用form表单。

**说明：** 

 

-   刷新预热类接口包含 RefreshObjectCaches 刷新接口和PushObjectCache预热接口。

-   同一个ID每天最多可提交2000条URL预热。
-   每次请求最多只能提交100条URL预热。
-   每秒最多50次请求。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=PushObjectCache&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|PushObjectCache|操作接口名，系统规定参数，取值：**PushObjectCache**。

 |
|ObjectPath|String|是|abc.com/image/1.png|多个URL之间需要用换行符（\\n）或（\\r\\n）分隔。

 |
|Area|String|否|domestic|预热区域。取值：

 -   **domestic**。
-   **overseas**。

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
http(s)://[Endpoint]/?Action=PushObjectCache
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

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

