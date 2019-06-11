# PushObjectCache {#reference2644 .reference}

调用PushObjectCache将源站的内容主动预热到L2 Cache节点上，用户首次访问可直接命中缓存，缓解源站压力。

支持post请求，参数用form表单。

**说明：** 

-   刷新预热类接口包含 RefreshObjectCaches 刷新接口和PushObjectCache预热接口。
-   同一个 ID 每天最多可提交2000条URL预热。
-   每次请求最多只能提交100条URL预热。
-   每秒最多50次请求。

## 调试 {#section_j01_yyx_yw6 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=PushObjectCache)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_o7s_hjy_1by .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：PushObjectCache。|
|ObjectPath|String|是|示例：`example.com/image/1.png`，多个URL之间需要用换行符`\n`或`\r\n`分隔。|
|Area|String|否|预热区域。取值： -   domestic。
-   overseas。

 |

## 返回参数 {#section_m1w_1wk_7gw .section}

|名称|类型|描述|
|:-|:-|:-|
|PushTaskId|String|预热返回的任务ID，多个任务ID用（,）分隔。|

## 示例 {#section_l0h_hoo_q5z .section}

请求示例

``` {#codeblock_8d4_kc7_as2}
https://cdn.aliyuncs.com?&Action=PushObjectCache&ObjectPath=example.com/test.txt&ObjectType=File&<公共请求参数>       
```

正常返回示例

`JSON`格式

``` {#codeblock_b3a_39t_vy9}
{
  "PushTaskId": "95248880",
  "RequestId": "E5BD4B50-7A02-493A-AE0B-97B9024B4135"
}
```

`XML`格式

``` {#codeblock_pe4_lhz_hga}
<PushObjectCacheResponse>
  <PushTaskId>95250421</PushTaskId>
  <RequestId>5FF9B16E-FBAC-48E5-9052-65B5F0184DB3</RequestId>
</PushObjectCacheResponse>
```

## 错误码 {#section_p92_uk6_a8k .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain operate is not permitted.|403|非法域名，无法操作。|
|OperationDenied|Your account does not open CDN service yet.|403|您未开通CDN服务。开通CDN服务请参见[开通CDN服务](../../../../intl.zh-CN/产品定价/开通CDN服务.md#)。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|InvalidDomain.Offline|The domain provided is offline.|404|域名已下线。|
|QuotaExceeded.Refresh|You've exceeded the prescribed refresh limits.|400|超出当日刷新限制。|
|PreloadQueueFull|Preload queue is full, please try again later!|403|预热队列已满，请您稍后再试（域名正在预热的URL个数已经达到上限，请您稍后重试）。|
|InvalidDomain.Configure\_failed|Failed to configure the provided domain.|500|域名配置失败，无法刷新。|
|MissingParameter|The input parameter "ObjectPath" that is mandatory for processing this request is not supplied.|400|缺少ObjectPath参数。|
|InvalidObjectPath.Malformed|The specific value of parameter ObjectPath is malformed.|400|ObjectPath格式错误。|
|InvalidExtensiveDomain.ValueNotSupported|Extensive domain not supported.|400|不支持泛域名。|
|InvalidObjectPath.Size.Malformed|The size of ObjectPath is bigger than 1000.|400|预热url个数一次不能超过1000。|

