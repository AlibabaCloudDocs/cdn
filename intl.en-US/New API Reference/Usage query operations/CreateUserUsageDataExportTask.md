# CreateUserUsageDataExportTask

Creates a task to export your resource usage history. The information is exported to a PDF file.

The maximum number of times that each user can call this operation per second is 100.

**Note:** You can create a task that queries data of up to the last one year. The maximum time range that can be queried is one month.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=CreateUserUsageDataExportTask&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|CreateUserUsageDataExportTask|The operation that you want to perform. Set the value to **CreateUserUsageDataExportTask**. |
|EndTime|String|Yes|2015-12-10T21:00:00Z|The end of the time range to query. The end time must be later than the start time.

Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|StartTime|String|Yes|2015-12-10T20:00:00Z|The start of the time range to query. The time interval at which the specified data is collected is five minutes.

Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|TaskName|String|No|Refresh|The name of the task. |
|Language|String|No|zh-cn|The language of the exported file.

-   **zh-cn**: Chinese. This is the default value.
-   **en-us**: English. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|EndTime|String|2015-12-10T21:00:00Z|The end of the time range where the QPS data was queried. |
|RequestId|String|ED61C6C3-8241-4187-AAA7-5157AE175CEC|The ID of the request. |
|StartTime|String|2015-12-10T20:00:00Z|The beginning of the time range that was queried. |
|TaskId|String|129456|The ID of the task. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=CreateUserUsageDataExportTask
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<CreateUserUsageDataExportTaskResponse>
      <RequestId>ED61C6C3-8241-4187-AAA7-5157AE175CEC</RequestId>
      <StartTime>2015-12-10T20:00:00Z</StartTime>
      <EndTime>2015-12-10T21:00:00Z</EndTime>
      <TaskId>129456</TaskId>
</CreateUserUsageDataExportTaskResponse>
```

`JSON` format

```
{
  "RequestId": "ED61C6C3-8241-4187-AAA7-5157AE175CEC",
  "StartTime": "2015-12-10T20:00:00Z",
  "EndTime": "2015-12-10T21:00:00Z",
  "TaskId": "129456"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

