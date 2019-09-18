# CreateUsageDetailDataExportTask {#doc_api_Cdn_CreateUsageDetailDataExportTask .reference}

调用CreateUsageDetailDataExportTask创建用量详细数据导出任务，将详细用量生成excel文件用于下载。

最长可创建查询近一年数据的任务，单次导出任务跨度最长为一个月。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=CreateUsageDetailDataExportTask&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateUsageDetailDataExportTask|操作接口名，系统规定参数。取值：**CreateUsageDetailDataExportTask**。

 |
|EndTime|String|是|2015-12-10T21:00:00Z|获取数据结束时间点。结束时间需大于起始时间。

 日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|StartTime|String|是|2015-12-10T20:00:00Z|获取数据起始时间点。

 日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Type|String|是|flow|需要获取的用量类型：**flow**或**vas**。

 |
|DomainNames|String|否|example.com|如果域名组为空，则以该字段提供的域名为准导出数据。

 如果未填写该参数, 则导出用户维度数据。

 |
|Group|String|否|xxx|域名组信息,。如果该信息不为空，则忽略DomainNames字段。

 |
|Language|String|否|en|导出文件的语言，支持**zh-cn**和**en-us**，分别为简体中文和英文，默认为中文**zh-cn**。

 |
|TaskName|String|否|刷新|任务名称。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|EndTime|String|2015-12-10T21:00:00Z|结束时间。

 |
|RequestId|String|ED61C6C3-8241-4187-AAA7-5157AE175CEC|请求ID。

 |
|StartTime|String|2015-12-10T20:00:00Z|开始时间。

 |
|TaskId|String|123456|任务ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=CreateUsageDetailDataExportTask
&Type=flow
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateUsageDetailDataExportTaskResponse>
	  <RequestId>ED61C6C3-8241-4187-AAA7-5157AE175CEC</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T21:00:00Z</EndTime>
	  <TaskId>123456</TaskId>
</CreateUsageDetailDataExportTaskResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"ED61C6C3-8241-4187-AAA7-5157AE175CEC",
	"EndTime":"2015-12-10T21:00:00Z",
	"TaskId":"123456",
	"StartTime":"2015-12-10T20:00:00Z"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

