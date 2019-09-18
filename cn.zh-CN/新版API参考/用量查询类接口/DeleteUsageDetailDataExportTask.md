# DeleteUsageDetailDataExportTask {#doc_api_Cdn_DeleteUsageDetailDataExportTask .reference}

调用DeleteUsageDetailDataExportTask删除用量详细数据导出任务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DeleteUsageDetailDataExportTask&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|TaskId|String|是|10|任务ID。

 |
|Action|String|否|DeleteUsageDetailDataExportTask|操作接口名，系统规定参数。取值：**DeleteUsageDetailDataExportTask**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DeleteUsageDetailDataExportTask
&TaskId=10
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteUsageDetailDataExportTaskRResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</DeleteUsageDetailDataExportTaskRResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

