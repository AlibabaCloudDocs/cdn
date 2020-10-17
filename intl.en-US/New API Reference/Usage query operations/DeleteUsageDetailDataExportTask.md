# DeleteUsageDetailDataExportTask

Deletes a task that was used to export usage details.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DeleteUsageDetailDataExportTask&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteUsageDetailDataExportTask|The operation that you want to perform. Set the value to **DeleteUsageDetailDataExportTask**. |
|TaskId|String|Yes|10|The ID of the export task that you want to delete. You can call the DescribeUserUsageDataExportTask operation to query task IDs. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DeleteUsageDetailDataExportTask
&TaskId=10
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DeleteUsageDetailDataExportTaskResponse>
      <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</DeleteUsageDetailDataExportTaskResponse>
```

`JSON` format

```
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

