# DescribeRealtimeDeliveryAcc {#reference_qn5_qly_dgb .reference}

You can call the DescribeRealtimeDeliveryAcc operation to query the number of real-time log deliveries.

## Request parameters {#section_obx_rly_dgb .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeRealtimeDeliveryAcc.|
|StartTime|String|No|The beginning of the time range where the log data is queried. -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.

 |
|EndTime|String|No| -   The end of the time range where the log data is queried. The end time must be later than the start time.
-   The maximum time range that can be queried is one year.
-   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.

 |
|Interval|String|No| -   The data sampling interval. Unit: seconds. Valid values: 300, 3600, and 86400.
-   If you do not specify this parameter or the specified parameter value is invalid, the default value applies. If the specified time range is no more than three days, the default value is 300.
-   If the specified time range is more than three days and no more than 30 days, the default value is 3600.
-   If the specified time range is more than 30 days, the default value is 86400.

 |
|Project|String|No|The project name for the real-time log delivery.|
|Logstore|String|No|The Logstore name for the real-time log delivery.|

## Response parameters {#section_vbx_rly_dgb .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestId|String|The ID of the request.|

Parameters in AccData

|Parameter|Type|Description|
|:--------|:---|:----------|
|TimeStamp|String|The timestamp of the data.|
|FailedNum|Integer|The number of failed attempts to import log data to Log Service.|
|SuccessNum|Integer|The number of successful attempts to import log data to Log Service.|

## Examples {#section_ybx_rly_dgb .section}

Sample request

``` {#codeblock_ia8_i75_jhy}
http://cdn.aliyuncs.com?Action=DescribeRealtimeDeliveryAcc&StartTime=2015-12-10T20:00:00Z&EndTime=2015-12-10T21:05:00Z
&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_bl9_fey_apk}
{
    "RequestId": "684306D2-2511-4977-991D-CE97E91FD7C0",
    "ReatTimeDeliveryAccData": {
        "AccData": [
            {
                "TimeStamp": "2018-09-03T06:00:00Z",
                "FailedNum": 0,
                "SuccessNum": 321321
            },
            {
                "TimeStamp": "2018-09-03T07:00:00Z",
                "FailedNum": 0,
                "SuccessNum": 32943
            }
            ...
        ]
    }
}
```

## Error codes {#section_zbx_rly_dgb .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|InvalidStartTime.Malformed|Specified StartTime is malformed.|400|The error message returned because the specified StartTime parameter is invalid.|
|InvalidEndTime.Malformed|Specified EndTime is malformed.|400|The error message returned because the specified EndTime parameter is invalid.|
|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|400|The error message returned because the time range specified by the EndTime and StartTime parameters exceeds the maximum value of 90 days.|
|InvalidEndTime.Mismatch|Specified EndTime does not math the specified StartTime.|400|The error message returned because the specified EndTime parameter is earlier than the specified StartTime parameter.|

