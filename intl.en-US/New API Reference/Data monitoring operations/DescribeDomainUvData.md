# DescribeDomainUvData

Queries the unique visitor \(UV\) data of an accelerated domain name. The data was collected at an interval of one hour. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   You can specify only one accelerated domain name or all accelerated domain names under your account.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainUvData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainUvData|The operation that you want to perform. Set the value to **DescribeDomainUvData**. |
|DomainName|String|Yes|test.test.com|The accelerated domain name. You can specify only one domain name. |
|StartTime|String|No|2019-11-29T00:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-11-29T04:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|3600|The time interval between the data entries. Unit: seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|EndTime|String|2019-11-29T04:00:00Z|The end of the time range that was queried. |
|RequestId|String|E9D3257A-1B7C-414C-90C1-8D07AC47BCAC|The ID of the request. |
|StartTime|String|2019-11-29T00:00:00Z|The beginning of the time range that was queried. |
|UvDataInterval|Array| |The number of UVs at each time interval. |
|UsageData| | | |
|TimeStamp|String|2019-11-29T00:00:00Z|The timestamp of the data returned. |
|Value|String|318|The number of UVs. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainUvData
&DomainName=example.com
&StartTime=2019-11-29T00:00:00Z
&EndTime=2019-11-29T04:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainUvDataResponse>
  <DataInterval>3600</DataInterval>
  <RequestId>17276F0E-66F4-4547-B9C6-42E2547362D4</RequestId>
  <DomainName>example.com</DomainName>
  <EndTime>2019-11-29T04:00:00Z</EndTime>
  <StartTime>2019-11-29T00:00:00Z</StartTime>
  <UvDataInterval>
        <UsageData>
              <TimeStamp>2019-11-29T00:00:00Z</TimeStamp>
              <Value>2</Value>
        </UsageData>
        <UsageData>
              <TimeStamp>2019-11-29T01:00:00Z</TimeStamp>
              <Value>12</Value>
        </UsageData>
        <UsageData>
              <TimeStamp>2019-11-29T02:00:00Z</TimeStamp>
              <Value>6</Value>
        </UsageData>
        <UsageData>
              <TimeStamp>2019-11-29T03:00:00Z</TimeStamp>
              <Value>7</Value>
        </UsageData>
        <UsageData>
              <TimeStamp>2019-11-29T04:00:00Z</TimeStamp>
              <Value>5</Value>
        </UsageData>
  </UvDataInterval>
</DescribeDomainUvDataResponse>
```

`JSON` format

```
{
	"DataInterval": "3600",
	"RequestId": "17276F0E-66F4-4547-B9C6-42E2547362D4",
	"DomainName": "example.com",
	"EndTime": "2019-11-29T04:00:00Z",
	"StartTime": "2019-11-29T00:00:00Z",
	"UvDataInterval": {
		"UsageData": [
			{
				"TimeStamp": "2019-11-29T00:00:00Z",
				"Value": "2"
			},
			{
				"TimeStamp": "2019-11-29T01:00:00Z",
				"Value": "12"
			},
			{
				"TimeStamp": "2019-11-29T02:00:00Z",
				"Value": "6"
			},
			{
				"TimeStamp": "2019-11-29T03:00:00Z",
				"Value": "7"
			},
			{
				"TimeStamp": "2019-11-29T04:00:00Z",
				"Value": "5"
			}
		]
	}
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|MissingParameter|StartTime and EndTime can not be single.|The error message returned because both the StartTime and EndTime parameters must be set.|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|The error message returned because the end time must be later than the start time.|
|400|InvalidDomainName.ValueNotSupported|The specified value of parameter DomainName only support one or empty value.|The error message returned because you can specify at most one accelerated domain name.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

