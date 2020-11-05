# DescribeDomainPvData

Queries the page view \(PV\) data of an accelerated domain name. The data is collected at an interval of one hour. You can query data within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 50.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainPvData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainPvData|The operation that you want to perform. Set the value to **DescribeDomainPvData**. |
|DomainName|String|Yes|test.test.com|The accelerated domain name. You can specify only one domain name. |
|StartTime|String|No|2015-11-28T00:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2015-11-29T00:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|3600|The time interval between the data entries. Unit: seconds. |
|DomainName|String|test.test.com|The accelerated domain name. |
|StartTime|String|2015-11-28T03:00:00Z|The beginning of the time range that was queried. |
|EndTime|String|2015-11-28T04:00:00Z|The end of the time range that was queried. |
|RequestId|String|BCD7D917-76F1-442F-BB75-C810DE34C761|The ID of the request. |
|PvDataInterval|Array of UsageData| |The number of PVs at each interval. |
|UsageData| | | |
|TimeStamp|String|2015-11-28T03:00:00Z|The timestamp of the data. |
|Value|String|9292|The number of PVs. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainPvData
&DomainName=test.test.com
&StartTime=2015-11-28T00:00:00Z
&EndTime=2015-11-29T00:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainPvDataResponse>
	  <DataInterval>3600</DataInterval>
	  <RequestId>BCD7D917-76F1-442F-BB75-C810DE34C761</RequestId>
	  <DomainName>example.com</DomainName>
	  <EndTime>2015-11-29T00:00:00Z</EndTime>
	  <PvDataInterval>
		    <UsageData>
			      <TimeStamp>2015-11-28T03:00:00Z</TimeStamp>
			      <Value>9292</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T23:00:00Z</TimeStamp>
			      <Value>9239</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T07:00:00Z</TimeStamp>
			      <Value>9464</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T12:00:00Z</TimeStamp>
			      <Value>9379</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T22:00:00Z</TimeStamp>
			      <Value>9243</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T10:00:00Z</TimeStamp>
			      <Value>10063</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T15:00:00Z</TimeStamp>
			      <Value>9068</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T14:00:00Z</TimeStamp>
			      <Value>9353</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T04:00:00Z</TimeStamp>
			      <Value>9513</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T02:00:00Z</TimeStamp>
			      <Value>9377</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T08:00:00Z</TimeStamp>
			      <Value>9579</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T20:00:00Z</TimeStamp>
			      <Value>9109</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T09:00:00Z</TimeStamp>
			      <Value>10631</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T06:00:00Z</TimeStamp>
			      <Value>9587</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T01:00:00Z</TimeStamp>
			      <Value>9108</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T16:00:00Z</TimeStamp>
			      <Value>9454</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T21:00:00Z</TimeStamp>
			      <Value>9285</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T19:00:00Z</TimeStamp>
			      <Value>9059</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T00:00:00Z</TimeStamp>
			      <Value>9470</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T05:00:00Z</TimeStamp>
			      <Value>11830</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T13:00:00Z</TimeStamp>
			      <Value>9992</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T17:00:00Z</TimeStamp>
			      <Value>9529</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T18:00:00Z</TimeStamp>
			      <Value>9203</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T11:00:00Z</TimeStamp>
			      <Value>9604</Value>
		    </UsageData>
	  </PvDataInterval>
	  <StartTime>2015-11-28T00:00:00Z</StartTime>
</DescribeDomainPvDataResponse>
```

`JSON` format

```
{
    "DataInterval": "3600",
    "RequestId": "BCD7D917-76F1-442F-BB75-C810DE34C761",
    "DomainName": "example.com",
    "EndTime": "2015-11-29T00:00:00Z",
    "PvDataInterval": {
        "UsageData": [
            {
                "TimeStamp": "2015-11-28T03:00:00Z",
                "Value": "9292"
            },
            {
                "TimeStamp": "2015-11-28T23:00:00Z",
                "Value": "9239"
            },
            {
                "TimeStamp": "2015-11-28T07:00:00Z",
                "Value": "9464"
            },
            {
                "TimeStamp": "2015-11-28T12:00:00Z",
                "Value": "9379"
            },
            {
                "TimeStamp": "2015-11-28T22:00:00Z",
                "Value": "9243"
            },
            {
                "TimeStamp": "2015-11-28T10:00:00Z",
                "Value": "10063"
            },
            {
                "TimeStamp": "2015-11-28T15:00:00Z",
                "Value": "9068"
            },
            {
                "TimeStamp": "2015-11-28T14:00:00Z",
                "Value": "9353"
            },
            {
                "TimeStamp": "2015-11-28T04:00:00Z",
                "Value": "9513"
            },
            {
                "TimeStamp": "2015-11-28T02:00:00Z",
                "Value": "9377"
            },
            {
                "TimeStamp": "2015-11-28T08:00:00Z",
                "Value": "9579"
            },
            {
                "TimeStamp": "2015-11-28T20:00:00Z",
                "Value": "9109"
            },
            {
                "TimeStamp": "2015-11-28T09:00:00Z",
                "Value": "10631"
            },
            {
                "TimeStamp": "2015-11-28T06:00:00Z",
                "Value": "9587"
            },
            {
                "TimeStamp": "2015-11-28T01:00:00Z",
                "Value": "9108"
            },
            {
                "TimeStamp": "2015-11-28T16:00:00Z",
                "Value": "9454"
            },
            {
                "TimeStamp": "2015-11-28T21:00:00Z",
                "Value": "9285"
            },
            {
                "TimeStamp": "2015-11-28T19:00:00Z",
                "Value": "9059"
            },
            {
                "TimeStamp": "2015-11-28T00:00:00Z",
                "Value": "9470"
            },
            {
                "TimeStamp": "2015-11-28T05:00:00Z",
                "Value": "11830"
            },
            {
                "TimeStamp": "2015-11-28T13:00:00Z",
                "Value": "9992"
            },
            {
                "TimeStamp": "2015-11-28T17:00:00Z",
                "Value": "9529"
            },
            {
                "TimeStamp": "2015-11-28T18:00:00Z",
                "Value": "9203"
            },
            {
                "TimeStamp": "2015-11-28T11:00:00Z",
                "Value": "9604"
            }
        ]
    },
    "StartTime": "2015-11-28T00:00:00Z"
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
|400|InvalidDomainName.ValueNotSupported|The specified value of parameter DomainName only support one or empty value.|The error message returned because you can specify at most one accelerated domain name for the DomainName parameter.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

