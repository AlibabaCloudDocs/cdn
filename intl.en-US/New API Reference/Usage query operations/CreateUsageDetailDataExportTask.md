# CreateUsageDetailDataExportTask

Creates a task to export resource usage details to an Excel file.

**Note:**

-   You can create a task that queries data of up to the last year. The maximum time range that can be queried is one month.
-   The maximum number of times that each Alibaba Cloud account can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=CreateUsageDetailDataExportTask&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|CreateUsageDetailDataExportTask|The operation that you want to perform. Set the value to **CreateUsageDetailDataExportTask**. |
|EndTime|String|Yes|2019-12-10T21:00:00Z|The end of the time range to query. The end time must be later than the start time.

 Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|StartTime|String|Yes|2019-12-10T20:00:00Z|The beginning of the time range to query.

 Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|Type|String|Yes|flow|The type of content based on which the data is generated. Valid values:

 -   **flow**: network traffic and bandwidth.
-   **vas**: requests. |
|Group|String|No|xxx|The group of accelerated domain names based on which the resource usage details are generated. If you set this parameter, ignore the DomainNames parameter. |
|DomainNames|String|No|example.com|The accelerated domain names based on which the resource usage details are generated. If you do not specify a domain name group, resource usage details are exported based on this parameter.

 If you do not set this parameter, resource usage details are exported based on user accounts. |
|TaskName|String|No|Refresh|The name of the task. |
|Language|String|No|en-us|The language of the exported file. Valid values:

 -   **zh-cn**: Chinese. This is the default value.
-   **en-us**: English. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|EndTime|String|2015-12-10T21:00:00Z|The end of the time range that was queried. |
|RequestId|String|ED61C6C3-8241-4187-AAA7-5157AE175CEC|The ID of the request. |
|StartTime|String|2015-12-10T20:00:00Z|The beginning of the time range that was queried. |
|TaskId|String|123456|The ID of the task. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/?Action=CreateUsageDetailDataExportTask
&Type=flow
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<Common request parameters>
```

Sample success response

`XML` format

```
<CreateUsageDetailDataExportTaskResponse>
	  <RequestId>ED61C6C3-8241-4187-AAA7-5157AE175CEC</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T21:00:00Z</EndTime>
	  <TaskId>123456</TaskId>
</CreateUsageDetailDataExportTaskResponse>
```

`JSON` format

```
{
  "RequestId": "ED61C6C3-8241-4187-AAA7-5157AE175CEC",
  "StartTime": "2015-12-10T20:00:00Z",
  "EndTime": "2015-12-10T21:00:00Z",
  "TaskId": "123456"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

