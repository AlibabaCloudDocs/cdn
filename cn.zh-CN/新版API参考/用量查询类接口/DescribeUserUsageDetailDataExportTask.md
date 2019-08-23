# DescribeUserUsageDetailDataExportTask {#doc_api_Cdn_DescribeUserUsageDetailDataExportTask .reference}

调用DescribeUserUsageDetailDataExportTask查询您账户下单个或多个域名5分钟明细数据的导出任务。

**说明：** 该功能从2018年7月20日开始，最长可查询近一年的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeUserUsageDetailDataExportTask&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeUserUsageDetailDataExportTask|操作接口名，系统规定参数。取值：**DescribeUserUsageDetailDataExportTask**。

 |
|PageNumber|String|否|1|取得第几页，取值范围：**1**~**100000**。

 |
|PageSize|String|否|10|分页大小。默认值：**20**；最大值：**50**。取值：**1**~**50**之间的任意整数。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|A91BE91F-0B34-4CBF-8E0F-A2977E15AA52|请求ID。

 |
|UsageDataPerPage| | |每页的用量数据。

 |
|Data| | |数据。

 |
|CreateTime|String|2018-10-09T06:33:38Z|任务创建时间。

 |
|DownloadUrl|String|example.com|下载地址。

 |
|Status|String|success|任务状态。

 |
|TaskConfig| | |任务配置。

 |
|EndTime|String|2018-08-31T15:59:59Z|用量结束时间。

 |
|StartTime|String|2018-07-31T16:00:00Z|用量起始时间。

 |
|TaskId|String|11|任务ID。

 |
|TaskName|String|刷新|任务名称。

 |
|UpdateTime|String|2018-10-09T06:35:46Z|任务最后更新时间。

 |
|PageNumber|Integer|1|当前页。

 |
|PageSize|Integer|10|每页记录数。

 |
|TotalCount|Integer|1|总记录数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeUserUsageDetailDataExportTask
&DomainName=example.com
&PageSize=10
&PageNumber=1
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUserUsageDetailDataExportTaskResponse>
	  <RequestId>A91BE91F-0B34-4CBF-8E0F-A2977E15AA52</RequestId>
	  <UsageDataPerPage>
		    <PageSize>10</PageSize>
		    <TotalCount>1</TotalCount>
		    <PageNumber>1</PageNumber>
		    <Data>
			      <DataItem>
				        <TaskId>11</TaskId>
				        <UpdateTime>2018-10-09T06:35:46Z</UpdateTime>
				        <DownloadUrl>example.com</DownloadUrl>
				        <CreateTime>2018-10-09T06:33:38Z</CreateTime>
				        <Status>success</Status>
				        <TaskConfig>
					          <StartTime>2018-07-31T16:00:00Z</StartTime>
					          <EndTime>2018-08-31T15:59:59Z</EndTime>
				        </TaskConfig>
			      </DataItem>
		    </Data>
	  </UsageDataPerPage>
</DescribeUserUsageDetailDataExportTaskResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"UsageDataPerPage":{
		"Data":{
			"DataItem":[
				{
					"Status":"success",
					"TaskConfig":{
						"EndTime":"2018-08-31T15:59:59Z",
						"StartTime":"2018-07-31T16:00:00Z"
					},
					"CreateTime":"2018-10-09T06:33:38Z",
					"DownloadUrl":"example.com",
					"UpdateTime":"2018-10-09T06:35:46Z",
					"TaskId":11
				}
			]
		},
		"PageNumber":1,
		"TotalCount":1,
		"PageSize":10
	},
	"RequestId":"A91BE91F-0B34-4CBF-8E0F-A2977E15AA52"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

