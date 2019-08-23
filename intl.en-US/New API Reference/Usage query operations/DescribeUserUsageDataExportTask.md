# DescribeUserUsageDataExportTask {#reference1729 .reference}

You can call the DescribeUserUsageDataExportTask operation to query the tasks created within the last three months for exporting resource usage information.

## Debugging {#section_t3n_9kb_8rs .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeUserUsageDataExportTask) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_gfj_be8_o3l .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to DescribeUserUsageDataExportTask.|
|PageSize|Integer|No|The number of entries to return on each page.|
|PageNumber|Integer|No|The number of the page to return.|

## Response parameters {#section_k4c_454_s4w .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|TotalCount|Integer|The total number of entries returned.|
|PageSize|Integer|The number of entries returned on each page.|
|PageNumber|Integer|The number of the page returned.|
|UsageDataPerPage|UsageData\[\]|The task details on the page.|

Parameters in UsageData

|Parameter|Type|Description|
|:--------|:---|:----------|
|StartTime|String|The beginning of the time range where the data was queried.|
|EndTime|String|The end of the time range where the data was queried.|
|CreateTime|String|The time when the task was created.|
|UpdateTime|String|The time when the task was last modified.|
|Status|String|The status of the task.|
|DownloadUrl|String|The URL where the task file can be downloaded.|

## Examples {#section_j2q_dmk_gze .section}

Sample request

``` {#codeblock_q83_28l_hy0}
http://cdn.aliyuncs.com?Action=DescribeUserUsageDataExportTask&DomainName=example.com
&PageSize=10
&PageNumber=1
&<Common request parameters>         
```

Sample success response

`JSON` format

``` {#codeblock_fwy_jud_j64}
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
          "DownloadUrl": "example.com",
          "UpdateTime": "2018-10-09T06:35:46Z",
          "CreateTime": "2018-10-09T06:33:38Z",
          "Status": "success"
          "TaskConfig": {
            "StartTime": "2018-07-31T16:00:00Z",
            "EndTime": "2018-08-31T15:59:59Z"
          },
        }
      ]
    }
  }
}
```

## Error codes {#section_nu9_m5t_ynh .section}

|Error code|Error message|HTTP status code|Description|
|----------|-------------|----------------|-----------|
|Throttling|Request was denied due to request throttling.|503|The error message returned because the request was denied due to throttling.|
|IllegalOperation|Illegal domain, operation is not permitted.|403|The error message returned because the specified domain name is invalid.|
|OperationDenied|Your account does not open Cdn service yet.|403|The error message returned because CDN has not been activated for your account.|
|OperationDenied|Your Cdn service is suspended.|403|The error message returned because CDN has been suspended for your account.|
|InvalidParameter|Invalid Parameter.|400|The error message returned because the parameters are invalid.|
|InvalidParameterProduct|Invalid Parameter Product.|400|The error message returned because the specified Product parameter is invalid.|
|InvalidParameterArea|Invalid Parameter Area.|400|The error message returned because the specified Area parameter is invalid.|
|InvalidParameterField|Invalid Parameter Field.|400|The error message returned because the specified Field parameter is invalid.|
|InvalidParameterStartTime|Invalid Parameter StartTime.|400|The error message returned because the specified StartTime parameter is invalid.|
|InvalidParameterEndTime|Invalid Parameter EndTime.|400|The error message returned because the specified EndTime parameter is invalid.|
|InvalidTimeRange|StartTime and EndTime range should less than 1 month.|400|The error message returned because the duration specified by the StartTime and EndTime parameters exceeds the maximum value of 31 days.|

