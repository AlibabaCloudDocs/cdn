# DescribeRefreshTasks {#doc_api_Cdn_DescribeRefreshTasks .reference}

调用DescribeRefreshTasks查询刷新、预热状态是否在全网生效。

调用该接口前，请您注意：

-   支持根据任务ID查询、URL查询。
-   Taskid与Objectpath都不指定：默认查3天内，第一页的数据（20条）。
-   Taskid与Objectpath可以同时指定。
-   当指定DomainName或TaskStatus时，ObjectType该项为必填。
-   只可查询3天内的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeRefreshTasks&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeRefreshTasks|操作接口名，系统规定参数，取值：**DescribeRefreshTasks**。

 |
|DomainName|String|否|www.yourdomain.com|域名。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|结束时间。

 |
|ObjectPath|String|否|http://aaa.com/1.txt|按路径查询，准确匹配。

 |
|ObjectType|String|否|file|任务类型：

 -   **file**
-   **path**
-   **preload**

 当指定**DomainName**或**TaskStatus**时，该参数为必选项。

 |
|PageNumber|Integer|否|1|取得第几页 取值范围为：**1**~**100000**。

 |
|PageSize|Integer|否|20|分页大小，默认**20**，最大**50**。取值：**1**~**50**之前的任意整数。

 |
|ResourceGroupId|String|否|your resourceGroupId|资源组ID。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|开始时间。

 |
|Status|String|否|Complete|任务状态：

 -   **Complete**：完成。
-   **Refreshing**：刷新中。
-   **Failed**：刷新失败。

 |
|TaskId|String|否|1234321|按任务ID查询刷新状态。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Tasks| | |TaskItem组成的Task任务列表。

 |
|TaskId|String|704225667|任务Id。

 |
|ObjectPath|String|http://aaa.com/1.txt|刷新对象路径。

 |
|Status|String|Complete|状态：

 -   **Complete**：完成。
-   **Refreshing**：刷新中。
-   **Failed**：刷新失败。
-   **Pending**：等待刷新。

 |
|Process|String|100%|进度百分比。

 |
|ObjectType|String|file|任务类型：

 -   **file**
-   **path**
-   **preload**

 |
|CreationTime|String|2014-11-27T08:23:22Z|任务对象创建时间，UTC时间。

 |
|Description|String|Internal Error|刷新预热失败返回错误描述。目前包含三种错误：

 -   **InternalError**
-   **OriginTimeout**
-   **OriginReturn StatusCode 5XX**

 |
|PageSize|Long|1|整页大小。

 |
|PageNumber|Long|10|页码。

 |
|TotalCount|Long|2|总条数。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?&Action=DescribeRefreshTasks
&ObjectPath=
&PageNumber=1
&PageSize=10
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeRefreshTasksResponse>	
	  <Tasks>
		    <CDNTask>
			      <CreationTime>2014-11-27T08:23:22Z</CreationTime>
			      <ObjectPath>http://aaa.com/1.txt</ObjectPath>
			      <Status>Complete</Status>
			      <TaskId>704225667</TaskId>
			      <ObjectType>file</ObjectType>
			      <Process>100%</Process>
		    </CDNTask>
		    <CDNTask>
			      <CreationTime>2014-11-27T08:18:38Z</CreationTime>
			      <ObjectPath>http://bbb.com/1.txt</ObjectPath>
			      <Status>Complete</Status>
			      <TaskId>704222904</TaskId>
			      <ObjectType>file</ObjectType>
			      <Process>100%</Process>
		    </CDNTask>
	  </Tasks>
	  <PageNumber>1</PageNumber>
	  <PageSize>10</PageSize>
	  <TotalCount>2</TotalCount>
	  <RequestId>174F6032-AA26-470D-B90E-36F0EB205BEE</RequestId>
</DescribeRefreshTasksResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":2,
	"PageSize":10,
	"RequestId":"174F6032-AA26-470D-B90E-36F0EB205BEE",
	"Tasks":{
		"CDNTask":[
			{
				"ObjectPath":"http://aaa.com/1.txt",
				"CreationTime":"2014-11-27T08:23:22Z",
				"Status":"Complete",
				"ObjectType":"file",
				"Process":"100%",
				"TaskId":"704225667"
			},
			{
				"ObjectPath":"http://bbb.com/1.txt",
				"CreationTime":"2014-11-27T08:18:38Z",
				"Status":"Complete",
				"ObjectType":"file",
				"Process":"100%",
				"TaskId":"704222904"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

