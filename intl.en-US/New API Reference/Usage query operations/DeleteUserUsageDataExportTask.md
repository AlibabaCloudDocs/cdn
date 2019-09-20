# DeleteUserUsageDataExportTask {#doc_api_Cdn_DeleteUserUsageDataExportTask .reference}

You can call this operation to delete a usage history export task.

## Debugging {#api_explorer .section}

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DeleteUserUsageDataExportTask&type=RPC&version=2018-05-10)

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|TaskId|String|Yes|10|The ID of the task to be deleted.

 |
|Action|String|No|DeleteUserUsageDataExportTask|The operation that you want to perform. Set the value to **DeleteUserUsageDataExportTask**.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|The ID of the request.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DeleteUserUsageDataExportTask
&TaskId=10
&<Common request parameters>
```

Sample success responses

`XML` format

``` {#xml_return_success_demo}
<DeleteUserUsageDataExportTaskResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</DeleteUserUsageDataExportTaskResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## Error codes { .section}

For more information about error codes, visit [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

