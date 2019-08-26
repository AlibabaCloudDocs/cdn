# DeleteUserUsageDataExportTask {#doc_api_Cdn_DeleteUserUsageDataExportTask .reference}

调用DeleteUserUsageDataExportTask创建历史用量信息导出任务，将详细用量生成excel文件用于下载。最长可创建查询近1年数据的任务，单次导出任务跨度最长为1个月。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DeleteUserUsageDataExportTask&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|TaskId|String|是|10|任务ID。

 |
|Action|String|否|DeleteUserUsageDataExportTask|操作接口名，系统规定参数。取值：**DeleteUserUsageDataExportTask**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DeleteUserUsageDataExportTask
&TaskId=10
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteUserUsageDataExportTaskResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</DeleteUserUsageDataExportTaskResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

