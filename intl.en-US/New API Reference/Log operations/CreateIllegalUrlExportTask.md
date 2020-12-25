# CreateIllegalUrlExportTask

Creates a task to export invalid URLs.

**Before you call this operation, take note of the following considerations:**

-   You can query data only by day. You can query data of the last month or later.
-   In most cases, a file that contains invalid URLs is generated five minutes after you create an export task. You can call the [DescribeIllegalUrlExportTask](~~156506~~) operation to query the URL where you can download the file.
-   The maximum number of times that each user can call this operation per second is 1.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=CreateIllegalUrlExportTask&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|CreateIllegalUrlExportTask|The operation that you want to perform. Set the value to **CreateIllegalUrlExportTask**. |
|TaskName|String|Yes|exampleTask|The name of the export task. |
|TimePoint|String|Yes|2019-09-30T16:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the YYYY-MM-DDThh:mm:ssZ format. The finest granularity is one day. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|The ID of the request. |
|TaskId|String|tu\_4b37ea97\_a7fa\_4d36\_b363\_061c1fxxxx|The ID of the export task. You can use task IDs to query tasks. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com? Action=CreateIllegalUrlExportTask
&TaskName=exampleTask
&TimePoint=2019-09-30T16:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<CreateIllegalUrlExportTaskResponse>
  <RequestId>64D28B53-5902-409B-94F6-FD46680144FE</RequestId>
  <TaskId>tu_4b37ea97_a7fa_4d36_b363_061c1fxxxx</TaskId>
</CreateIllegalUrlExportTaskResponse>
```

`JSON` format

```
{
	"RequestId": "64D28B53-5902-409B-94F6-FD46680144FE",
    "TaskId": "tu_4b37ea97_a7fa_4d36_b363_061c1fxxxx"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

