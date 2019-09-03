# RefreshObjectCaches {#doc_api_Cdn_RefreshObjectCaches .reference}

调用RefreshObjectCaches刷新节点上的文件内容。刷新指定URL内容至Cache节点，支持URL批量刷新。

支持post请求，参数用form表单。

**说明：** 

-   刷新预热类接口包含**RefreshObjectCaches**刷新接口和**PushObjectCache**预热接口。
-   同一个ID 每天最多可提交2000条URL刷新和100个目录刷新。
-   每次请求最多只能提交1000条URL刷新。
-   每秒最多50次请求。
-   单个ID的刷新队列最大限制为1000条，根据提交的先后顺序来刷新。如果队列任务堆积到1000条，则需要等提交的刷新请求完成之后才能提交新的，以此来保持队列大小始终不超过1000。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=RefreshObjectCaches&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|RefreshObjectCaches|操作接口名，系统规定参数，取值：**RefreshObjectCaches**。

 |
|ObjectPath|String|是|abc.com/image/1.png|多个URL之间需要用换行符（\\n）或（\\r\\n）分隔。

 |
|ObjectType|String|否|File|刷新的类型， 其值可以为**File**或**Directory**。默认值：**File**。

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
&ObjectPath=example.com/test.txt
&ObjectType=File
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<RefreshObjectCaches>	
  <RefreshTaskId>704222904</RefreshTaskId>
	  <RequestId>D61E4801-EAFF-4A63-AAE1-FBF6CE1CFD1C</RequestId>
</RefreshObjectCaches>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RefreshTaskId":"704222904",
	"RequestId":"D61E4801-EAFF-4A63-AAE1-FBF6CE1CFD1C"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

