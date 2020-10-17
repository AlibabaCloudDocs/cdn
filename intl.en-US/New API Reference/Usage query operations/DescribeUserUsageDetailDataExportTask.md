# DescribeUserUsageDetailDataExportTask

Queries tasks that were used to export resource usage details of one or more accelerated domain names under your account. The resource usage information was collected at intervals of five minutes within a specific time range.

**Note:** This operation has been available starting from July 20, 2018. You can query data generated within the last 12 months.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeUserUsageDetailDataExportTask&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeUserUsageDetailDataExportTask|The operation that you want to perform. Set the value to **DescribeUserUsageDetailDataExportTask**. |
|PageSize|String|No|10|The number of entries to return on each page. Default value: **20**. Maximum value: **50**.

 Valid values: **1** to **50**. |
|PageNumber|String|No|1|The number of the page to return. Valid values: **1** to **100000**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|A91BE91F-0B34-4CBF-8E0F-A2977E15AA52|The ID of the request. |
|UsageDataPerPage|Struct| |The usage details returned per page. |
|Data|Array of DataItem| |The information about the task. |
|DataItem| | | |
|CreateTime|String|2018-10-09T06:33:38Z|The time when the task was created. |
|DownloadUrl|String|https://test.oss-cn-beijing.aliyuncs.com/billing\_data/xxx|The download URL. |
|Status|String|success|The status of the task. |
|TaskConfig|Struct| |The configurations of the task. |
|EndTime|String|2018-08-31T15:59:59Z|The end of the time range that was queried. |
|StartTime|String|2018-07-31T16:00:00Z|The start of the time range that was queried. |
|TaskId|String|11|The ID of the task. |
|TaskName|String|Refresh|The name of the task. |
|UpdateTime|String|2018-10-09T06:35:46Z|The last time when the task was modified. |
|PageNumber|Integer|1|The current page number. |
|PageSize|Integer|10|The number of the entries returned per page. |
|TotalCount|Integer|1|The total number of entries returned. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeUserUsageDetailDataExportTask
&PageSize=10
&PageNumber=1
&<Common request parameters>
```

Sample success responses

`XML` format

```
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
                    <DownloadUrl>https://test.oss-cn-beijing.aliyuncs.com/billing_data/xxx</DownloadUrl>
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

`JSON` format

```
{
  "RequestId": "A91BE91F-0B34-4CBF-8E0F-A2977E15AA52",
  "UsageDataPerPage": {
    "PageSize": 10,
    "TotalCount": 1,
    "PageNumber": 1,
    "Data": {
      "DataItem": [
        {
          "TaskId": 11,
          "UpdateTime": "2018-10-09T06:35:01Z",
          "DownloadUrl": "https://test.oss-cn-beijing.aliyuncs.com/billing_data/xxx",
          "UpdateTime": "2018-10-09T06:35:46Z",
          "CreateTime": "2018-10-09T06:33:38Z",
          "Status": "success",
          "TaskConfig": {
            "StartTime": "2018-07-31T16:00:00Z",
            "EndTime": "2018-08-31T15:59:59Z"
          }
        }
      ]
    }
  }
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

