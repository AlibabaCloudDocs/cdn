# DescribeRefreshTasks

Queries the status of refresh or prefetch tasks that belong to a specified accelerated domain name.

**Note:**

-   You can query the status of tasks by task ID or URL.
-   You can set both the **TaskId** and **ObjectPath** parameters. If you do not set the **TaskId** or **ObjectPath** parameter, data entries on the first page \(20 entries\) collected within the last three days are returned.
-   You can query only data collected within the last three days.
-   The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeRefreshTasks&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeRefreshTasks|The operation that you want to perform. Set the value to **DescribeRefreshTasks**. |
|TaskId|String|No|1234321|The task ID by which the task status is queried. |
|ObjectPath|String|No|http://aaa.com/1.txt|The path of the object. The path is used as a condition for an exact match. |
|PageNumber|Integer|No|1|The number of the page to return. Valid values: **1** to **100000**. |
|ObjectType|String|No|file|The type of the task. Valid values:

 -   **file**: refreshes an individual file.
-   **directory**: refreshes files under the specified directories.
-   **preload**: prefetches an individual file.

 **Note:** If you set the **DomainName** or **TaskStatus** parameter, you must also set the **ObjectType** parameter. |
|DomainName|String|No|www.yourdomain.com|The accelerated domain name to which the tasks belong. You can specify only one accelerated domain name in each call. By default, this operation queries the status of tasks for all accelerated domain names. |
|Status|String|No|Complete|The status of the task. Valid values:

 -   **Complete**: The task is completed.
-   **Refreshing**: The task is in progress.
-   **Failed**: The task failed. |
|PageSize|Integer|No|20|The number of entries to be returned on each page. Default value: **20**. Maximum value: **100**. Valid values: **1** to **100**. |
|StartTime|String|No|2017-12-21T08:00:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2017-12-22T08:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 **Note:** The end time must be later than the start time. |
|ResourceGroupId|String|No|rg-acfmyuji4b6r4\*\*|The ID of the resource group. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Tasks|Array of CDNTask| |A list of tasks. |
|CDNTask| | | |
|TaskId|String|704225667|The ID of the task. |
|ObjectPath|String|http://aaa.com/1.txt|The path of the object. |
|Status|String|Complete|The status of the task. Valid values:

 -   **Complete**: The task is completed.
-   **Refreshing**: The task is in progress.
-   **Failed**: The task has failed.
-   **Pending**: The task is pending. |
|Process|String|100%|The progress of the task, in percentage. |
|ObjectType|String|file|The type of the task. Valid values:

 -   **file**: refreshes an individual file.
-   **directory**: refreshes files under the specified directories.
-   **preload**: prefetches an individual file. |
|CreationTime|String|2014-11-27T08:23:22Z|The time when the task was created. The time is displayed in UTC. |
|Description|String|Internal Error|The type of the error returned when the refresh or prefetch task failed. Valid values:

 -   **InternalError**: An internal error occurred.
-   **OriginTimeout**: The response from the origin server timed out.
-   **OriginReturn StatusCode 5XX**: The origin server returned a 5XX error. |
|PageSize|Long|1|The number of entries returned per page. |
|PageNumber|Long|10|The number of the returned page. |
|TotalCount|Long|2|The total number of entries returned. |
|RequestId|String|174F6032-AA26-470D-B90E-36F0EB205BEE|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeRefreshTasks
&ObjectPath=http://aaa.com/1.txt
&PageNumber=1
&PageSize=10
&<Common request parameters>
```

Sample responses

`XML` format

```
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

`JSON` format

```
{
	"Tasks": {
		"CDNTask": [
            {
			"CreationTime": "2014-11-27T08:23:22Z",
			"ObjectPath": "http://aaa.com/1.txt",
			"Status": "Complete",
			"TaskId": "704225667",
			"ObjectType": "file",
			"Process": "100%"
		}, {
			"CreationTime": "2014-11-27T08:18:38Z",
			"ObjectPath": "http://bbb.com/1.txt",
			"Status": "Complete",
			"TaskId": "704222904",
			"ObjectType": "file",
			"Process": "100%"
		}
      ]
	},
	"PageNumber": 1,
	"PageSize": 10,
	"TotalCount": 2,
	"RequestId": "174F6032-AA26-470D-B90E-36F0EB205BEE"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

