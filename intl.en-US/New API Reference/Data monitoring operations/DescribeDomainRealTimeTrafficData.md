# DescribeDomainRealTimeTrafficData

Queries the monitoring data of network traffic for one or more accelerated domain names. The monitoring data is collected every minute. You can query monitoring data collected within the last seven days. The network traffic is measured in bytes.

**Note:** If you do not set **StartTime** or **EndTime**, data collected within the last 24 hours is queried. If you set both **StartTime** and **EndTime**, data collected within the specified time range is queried.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeTrafficData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainRealTimeTrafficData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeTrafficData**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify one or more accelerated domain names. Separate multiple accelerated domain names with commas \(,\). |
|StartTime|String|No|2019-12-10T20:00:00Z|The beginning of the time range to query.

 Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-10T20:01:00Z|The end of the time range to query.

 Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 **Note:** The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|60|The time interval between the data entries, in seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|StartTime|String|2019-12-10T20:00:00Z|The beginning of the time range that was queried. |
|EndTime|String|2019-12-10T20:01:00Z|The end of the time range that was queried. |
|RequestId|String|A666D44F-19D6-490E-97CF-1A64AB962C57|The ID of the request |
|RealTimeTrafficDataPerInterval|Array of DataModule| |The information about the network traffic collected at each interval. |
|DataModule| | | |
|TimeStamp|String|2019-12-10T20:01:00Z|The timestamp of the data returned. |
|Value|String|0|The amount of network traffic. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeDomainRealTimeTrafficData
&DomainName=example.com
&StartTime=2019-12-10T20:00:00Z
&EndTime=2019-12-10T20:01:00Z
&<Common request parameters>
```

Sample responses

`XML` format

```
<DescribeDomainRealTimeTrafficDataResponse>
	  <DomainName>example.com</DomainName>
	  <DataInterval>60</DataInterval>
	  <RealTimeTrafficDataPerInterval>
		    <DataModule>
			      <TimeStamp>2019-12-10T20:00:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2019-12-10T20:01:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
	  </RealTimeTrafficDataPerInterval>
	  <RequestId>A666D44F-19D6-490E-97CF-1A64AB962C57</RequestId>
	  <StartTime>2019-12-10T20:00:00Z</StartTime>
	  <EndTime>2019-12-10T20:01:00Z</EndTime>
</DescribeDomainRealTimeTrafficDataResponse>
```

`JSON` format

```
{
    "DomainName": "example.com",
    "DataInterval": "60",
    "RealTimeTrafficDataPerInterval": {
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
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the specified end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|The error message returned because the end time must be later than the start time.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid. Rectify the start time and try again.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

