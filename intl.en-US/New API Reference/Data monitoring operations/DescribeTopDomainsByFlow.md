# DescribeTopDomainsByFlow

Queries the top N domain names ranked by network traffic. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the current month is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeTopDomainsByFlow&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeTopDomainsByFlow|The operation that you want to perform. Set the value to **DescribeTopDomainsByFlow**. |
|StartTime|String|No|2019-12-22T08:00:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-23T08:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |
|Limit|Long|No|20|The maximum number of domain names to return. Valid values: **1** to **100**. Default value: **20**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70|The ID of the request. |
|StartTime|String|2019-12-22T08:00:00Z|The beginning of the time range that was queried. |
|EndTime|String|2019-12-23T08:00:00Z|The end of the time range that was queried. |
|TopDomains|Array of TopDomain| |The top N domain names ranked by network traffic. |
|TopDomain| | | |
|DomainName|String|test.test.com|The accelerated domain name. |
|Rank|Long|1|The ranking of the accelerated domain names. |
|TotalTraffic|String|2043859876683.9001|The total amount of network traffic. |
|TrafficPercent|String|30.64191989360235|The proportion of the network traffic consumed by the accelerated domain name. |
|MaxBps|Float|22139626|The peak bandwidth value. |
|MaxBpsTime|String|1457111400|The time when the bandwidth reached the peak value. |
|TotalAccess|Long|107784230|The number of visits to the accelerated domain name. |
|DomainCount|Long|68|The total number of accelerated domain names under your Alibaba Cloud account. |
|DomainOnlineCount|Long|68|The total number of accelerated domain names that are in the **Enabled** state under your Alibaba Cloud account. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeTopDomainsByFlow
&StartTime=2019-12-22T08:00:00Z
&EndTime=2019-12-23T08:00:00Z
&Limit=5
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeTopDomainsByFlowResponse>
  <DomainCount>4</DomainCount>
  <DomainOnlineCount>4</DomainOnlineCount>
  <RequestId>6796A2B4-15A7-4142-85C0-5A93406034B5</RequestId>
  <TopDomains>
        <TopDomain>
              <MaxBps>26.752000000000002</MaxBps>
              <Rank>3</Rank>
              <TrafficPercent>0.000910078753253719</TrafficPercent>
              <TotalTraffic>2003</TotalTraffic>
              <TotalAccess>2</TotalAccess>
              <DomainName>test.test.com</DomainName>
              <MaxBpsTime>2019-12-22T20:50:00Z</MaxBpsTime>
        </TopDomain>
  </TopDomains>
  <EndTime>2019-12-23T08:00:00Z</EndTime>
  <StartTime>2019-12-22T08:00:00Z</StartTime>
</DescribeTopDomainsByFlowResponse>
```

`JSON` format

```
{
	"DomainCount": 4,
	"DomainOnlineCount": 4,
	"RequestId": "6796A2B4-15A7-4142-85C0-5A93406034B5",
	"TopDomains": {
		"TopDomain": [
			{
				"MaxBps": "26.752000000000002",
				"Rank": 3,
				"TrafficPercent": "0.000910078753253719",
				"TotalTraffic": 2003,
				"TotalAccess": 2,
				"DomainName": "test.test.com",
				"MaxBpsTime": "2019-12-22T20:50:00Z"
			}
		]
	},
	"EndTime": "2019-12-23T08:00:00Z",
	"StartTime": "2019-12-22T08:00:00Z"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is not supported.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

