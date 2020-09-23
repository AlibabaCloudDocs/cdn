# DescribeDomainSrcQpsData

Queries the number of queries per second for back-to-origin requests. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   You can specify one or more accelerated domain names. Separate multiple domain names with commas \(,\).
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainSrcQpsData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|DescribeDomainSrcQpsData|The operation that you want to perform. Set the value to **DescribeDomainSrcQpsData**. |
|DomainName|String|No|example.com|The accelerated domain names that you want to query. Separate multiple domain names with commas \(,\).

 By default, all accelerated domain names are queried. |
|StartTime|String|No|2019-11-30T05:33:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 If you do not specify this parameter, data collected within the last 24 hours is queried. |
|EndTime|String|No|2019-11-30T05:40:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the StartTime and EndTime parameters. Valid values:

 -   Less than 3 days: 300, 3600, and 86400 The default value is 300.
-   3 to 31 \(excluded\) days: 3600 and 86400. The default value is 3600.
-   No less than 31 days: 86400. The default value is 86400. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The minimum time interval between the entries returned. Unit: seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|EndTime|String|2019-11-30T05:40:00Z|The end of the time range that was queried. |
|RequestId|String|7CBCD6AD-B016-42E5-AE0B-B3731DE8F755|The ID of the request. |
|SrcQpsDataPerInterval|Array| |The back-to-origin bandwidth information returned at each interval. |
|DataModule| | | |
|TimeStamp|String|2015-12-10T21:00:00Z|The timestamp of the data returned. |
|Value|String|0|The number of queries per second. |
|StartTime|String|2019-11-30T05:33:00Z|The beginning of the time range that was queried. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainSrcQpsData
&DomainName=example.com
&StartTime=2019-11-30T05:33:00Z
&EndTime=2019-11-30T05:40:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainSrcQpsDataResponse>
  <DomainName>example.com</DomainName>
  <DataInterval>300</DataInterval>
  <SrcQpsDataPerInterval>
        <DataModule>
              <TimeStamp>2019-11-30T05:33:00Z</TimeStamp>
              <Value>0</Value>
        </DataModule>
        <DataModule>
              <TimeStamp>2019-11-30T05:34:00Z</TimeStamp>
              <Value>0</Value>
        </DataModule>
  </SrcQpsDataPerInterval>
  <RequestId>7CBCD6AD-B016-42E5-AE0B-B3731DE8F755</RequestId>
  <StartTime>2019-11-30T05:33:00Z</StartTime>
  <EndTime>2019-11-30T05:40:00Z</EndTime>
</DescribeDomainSrcQpsDataResponse>
```

`JSON` format

```
{
    "DomainName": "example.com",
    "DataInterval": 300,
    "SrcQpsDataPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2019-11-30T05:33:00Z",
                "Value": 0
            },
            {
                "TimeStamp": "2019-11-30T05:34:00Z",
                "Value": 0
            }
        ]
    },
    "RequestId": "7CBCD6AD-B016-42E5-AE0B-B3731DE8F755",
    "StartTime": "2019-11-30T05:33:00Z",
    "EndTime": "2019-11-30T05:40:00Z"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|MissingParameter|StartTime and EndTime can not be single.|The error message returned because both the StartTime and EndTime parameters must be set.|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|The error message returned because the end time must be later than the start time.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

