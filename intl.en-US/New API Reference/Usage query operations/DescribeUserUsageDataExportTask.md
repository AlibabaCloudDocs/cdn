# DescribeUserUsageDataExportTask

Queries export tasks that were created in the last three months. The tasks were used to export resource usage information.

You can call this operation up to 100 times per second with each account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeUserUsageDataExportTask&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeUserUsageDataExportTask|The operation that you want to perform. Set the value to **DescribeUserUsageDataExportTask**. |
|PageSize|String|No|20|The number of entries to return on each page. Default value: **20**. Maximum value: **50**.

 Valid values: **1** to **50**. |
|PageNumber|String|No|1|The number of the page to return. Valid values: **1** to **100000**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|A91BE91F-0B34-4CBF-8E0F-A2977E15AA52|The ID of the request. |
|UsageDataPerPage|Struct| |The task details on the page. |
|Data|Array| |The description of the task. |
|DataItem| | | |
|CreateTime|String|2019-12-31T08:43:21Z|The time when the task was created. |
|DownloadUrl|String|https://cdn-polaris.xxxx|The download URL. |
|Status|String|success|The status of the task.

 -   created: The task is being created.
-   success: The task creation is successful.
-   failed: The task creation has failed. |
|TaskConfig|Struct| |The configurations of the task. |
|EndTime|String|2019-12-30T15:59:59Z|The end of the time range that was queried. |
|StartTime|String|2019-12-29T16:00:00Z|The start of the time range that was queried. |
|TaskId|String|A91BE91F-0B34-4CBF-8E0F-A2977|The ID of the task. |
|TaskName|String|Refresh|The name of the task. |
|UpdateTime|String|2019-12-31T08:45:02Z|The time when the task was last modified. |
|PageNumber|Integer|1|The page number of the returned page. |
|PageSize|Integer|10|The number of entries that were returned per page. |
|TotalCount|Integer|10|The total number of entries returned. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeUserUsageDataExportTask
&PageSize=10
&PageNumber=1
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeUserUsageDataExportTaskResponse>
  <UsageDataPerPage>
        <Data>
              <DataItem>
                    <Status>success</Status>
                    <TaskConfig>
                          <EndTime>2019-12-30T15:59:59Z</EndTime>
                          <StartTime>2019-12-29T16:00:00Z</StartTime>
                    </TaskConfig>
                    <CreateTime>2019-12-31T08:43:21Z</CreateTime>
                    <DownloadUrl>https://cdn-polaris.xxxx</DownloadUrl>
                    <UpdateTime>2019-12-31T08:45:02Z</UpdateTime>
                    <TaskId>11584</TaskId>
                    <TaskName></TaskName>
              </DataItem>
        </Data>
        <PageNumber>1</PageNumber>
        <TotalCount>1</TotalCount>
        <PageSize>10</PageSize>
  </UsageDataPerPage>
  <RequestId>FB7EC32A-356A-4B33-BA59-6DB1FFF61FD2</RequestId>
</DescribeUserUsageDataExportTaskResponse>
```

`JSON` format

```
{
	"UsageDataPerPage": {
		"Data": {
			"DataItem": [
				{
					"Status": "success",
					"TaskConfig": {
						"EndTime": "2019-12-30T15:59:59Z",
						"StartTime": "2019-12-29T16:00:00Z"
					},
					"CreateTime": "2019-12-31T08:43:21Z",
					"DownloadUrl": "https://cdn-polaris.xxxx",
					"UpdateTime": "2019-12-31T08:45:02Z",
					"TaskId": 11584,
					"TaskName": ""
				}
			]
		},
		"PageNumber": 1,
		"TotalCount": 1,
		"PageSize": 10
	},
	"RequestId": "FB7EC32A-356A-4B33-BA59-6DB1FFF61FD2"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

