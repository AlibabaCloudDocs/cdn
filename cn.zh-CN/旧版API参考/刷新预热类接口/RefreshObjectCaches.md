# RefreshObjectCaches {#doc_api_Cdn_RefreshObjectCaches .reference}

调用RefreshObjectCaches接口刷新节点上的文件内容。

 **调用该接口前，请您注意：** 

-   刷新指定URL内容至Cache节点，支持URL批量刷新。
-   支持post请求，参数用form表单。
-   刷新预热类接口包含**RefreshObjectCaches**刷新接口和 **PushObjectCache**预热接口。
-   同一个ID每天最多提交预热刷新类请求数量如下：
    -   URL：2000条。
    -   目录：100个。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=RefreshObjectCaches&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|RefreshObjectCaches|操作接口名，系统规定参数。取值：**RefreshObjectCaches**。

 |
|ObjectPath|String|是|abc.com/image/1.png|多个URL之间需要用换行符（\\n或\\r\\n）分隔。

 |
|ObjectType|String|否|File|刷新的类型，可选。取值：

 -   **File**
-   **Directory**

 默认值：**File**。

 **说明：** 当ObjectType值为Directory时，ObjectPath结尾需加正斜线（/）。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RefreshTaskId|String|704222904|刷新返回的任务ID，多个任务ID用逗号（,）分隔。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?&Action=RefreshObjectCaches
&ObjectPath=test.example.com/test.txt
&ObjectType=File
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<RefreshObjectCachesResponse>
    <RefreshTaskId>704225667</RefreshTaskId>
    <RequestId>AB14769A-A5F2-4CCD-B85B-3368DFF63C0A</RequestId>
</RefreshObjectCachesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RefreshTaskId":"704222904",
	"RequestId":"D61E4801-EAFF-4A63-AAE1-FBF6CE1CFD1C"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|QuotaExceeded.Refresh|You've exceeded the prescribed refresh limits.|超出当日刷新限制。今日刷新数已用完。您可以通过刷新接口查询今日的刷新次数。|
|400|ObjectPath.Malformed|The specified value of parameter ObjectPath is malformed.|参数ObjectPath值格式错误。输入示例：abc.com/image/1.png。多个URL之间需要用换行符（\\n 或 \\r\\n）分隔。|
|400|InvalidObjectPath.Malformed|The specific value of parameter ObjectPath is malformed.|参数ObjectPath值格式错误。输入示例：abc.com/image/1.png。多个URL之间需要用换行符（\\n 或 \\r\\n）分隔。|
|400|InvalidExtensiveDomain.ValueNotSupported|Extensive domain not supported.|该操作不支持泛域名。|
|400|QuotaPerMinuteExceeded.Refresh|You've exceeded the prescribed refresh limits per minute.|每分钟刷新频率超过上限。|
|400|TooMany.Refresh|there is too many refresh task, please wait a moment.|刷新任务太多，请您稍后再试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

