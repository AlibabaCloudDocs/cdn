# DescribeRealtimeDeliveryAcc

Queries the number of real-time log deliveries.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeRealtimeDeliveryAcc&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeRealtimeDeliveryAcc|The operation that you want to perform. Set the value to **DescribeRealtimeDeliveryAcc**. |
|StartTime|String|No|2016-10-20T04:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2016-10-20T05:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end of the time range to query. The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

 -   If the time span between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time span between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   If the time span between StartTime and EndTime is 31 days or longer, the valid value is **86400**. Default value: **86400**. |
|Project|String|No|Project|The name of the Log Service project that is used for real-time log delivery. By default, all projects are queried. |
|LogStore|String|No|LogStore|The name of the Logstore that collects log data from Alibaba Cloud Content Delivery Network \(CDN\) in real time. By default, all Logstores are queried. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|ReatTimeDeliveryAccData|Array of AccData| |The information about real-time log delivery. |
|AccData| | | |
|FailedNum|Integer|2|The number of failed attempts to deliver log data to Log Service. |
|SuccessNum|Integer|2|The number of successful deliveries of log data to Log Service. |
|TimeStamp|String|2018-09-03T06:00:00Z|The timestamp of the data. |
|RequestId|String|684306D2-2511-4977-991D-CE97E91FD7C0|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeRealtimeDeliveryAcc
&StartTime=2016-10-20T04:00:00Z
&EndTime=2016-10-20T05:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeRealtimeDeliveryAccResponse>
	  <RequestId>684306D2-2511-4977-991D-CE97E91FD7C0</RequestId>
	  <ReatTimeDeliveryAccData>
		    <AccData>
			      <TimeStamp>2018-09-03T06:00:00Z</TimeStamp>
			      <FailedNum>0</FailedNum>
			      <SuccessNum>321321</SuccessNum>
		    </AccData>
		    <AccData>
			      <TimeStamp>2018-09-03T07:00:00Z</TimeStamp>
			      <FailedNum>0</FailedNum>
			      <SuccessNum>32943</SuccessNum>
		    </AccData>
	  </ReatTimeDeliveryAccData>
</DescribeRealtimeDeliveryAccResponse>
```

`JSON` format

```
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
            
        ]
    }
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

