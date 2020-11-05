# DescribeDomainRealTimeSrcTrafficData

Queries the monitoring data of back-to-origin traffic for an accelerated domain name. The data is collected at an interval of one minute. The network traffic is measured in bytes. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   You can specify one or more domain names. Separate multiple domain names with commas \(,\).
-   The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeSrcTrafficData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainRealTimeSrcTrafficData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeSrcTrafficData**. |
|DomainName|String|Yes|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|StartTime|String|No|2019-12-10T20:00:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-10T20:01:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|60|The time interval between the entries returned. Unit: seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|EndTime|String|2019-12-10T20:01:00Z|The end of the time range that was queried. |
|RealTimeSrcTrafficDataPerInterval|Array of DataModule| |The back-to-origin network traffic returned at each interval. |
|DataModule| | | |
|TimeStamp|String|2019-12-10T20:01:00Z|The timestamp of the data. |
|Value|String|0|The consumed network traffic. |
|RequestId|String|A666D44F-19D6-490E-97CF-1A64AB962C57|The ID of the request. |
|StartTime|String|2019-12-10T20:00:00Z|The beginning of the time range that was queried. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeSrcTrafficData
&DomainName=example.com
&StartTime=2019-12-10T20:00:00Z
&EndTime=2019-12-10T20:01:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainRealTimeSrcTrafficDataResponse>
      <DomainName>example.com</DomainName>
      <DataInterval>60</DataInterval>
      <RealTimeSrcTrafficDataPerInterval>
            <DataModule>
                  <TimeStamp>2019-12-10T20:00:00Z</TimeStamp>
                  <Value>0</Value>
            </DataModule>
            <DataModule>
                  <TimeStamp>2019-12-10T20:01:00Z</TimeStamp>
                  <Value>0</Value>
            </DataModule>
      </RealTimeSrcTrafficDataPerInterval>
      <RequestId>A666D44F-19D6-490E-97CF-1A64AB962C57</RequestId>
      <StartTime>2019-12-10T20:00:00Z</StartTime>
      <EndTime>2019-12-10T20:01:00Z</EndTime>
</DescribeDomainRealTimeSrcTrafficDataResponse>
```

`JSON` format

```
{
    "DomainName": "example.com",
    "DataInterval": "60",
    "RealTimeSrcTrafficDataPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2019-12-10T20:00:00Z",
                "Value": "0"
            },
            {
                "TimeStamp": "2019-12-10T20:01:00Z",
                "Value": "0"
            }
        ]
    },
    "RequestId": "A666D44F-19D6-490E-97CF-1A64AB962C57",
    "StartTime": "2019-12-10T20:00:00Z",
    "EndTime": "2019-12-10T20:01:00Z"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|MissingParameter|StartTime and EndTime can not be single.|The error message returned because both the StartTime and EndTime parameters must be set.|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|The error message returned because the end time must be later than the start time.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is not supported.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

