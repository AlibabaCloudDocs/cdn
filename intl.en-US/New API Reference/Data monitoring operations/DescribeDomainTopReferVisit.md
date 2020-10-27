# DescribeDomainTopReferVisit

Queries and sorts frequently requested web pages on a specified day. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   Data is collected at an interval of five minutes.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTopReferVisit&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|DescribeDomainTopReferVisit|The operation that you want to perform. Set the value to **DescribeDomainTopReferVisit**. |
|DomainName|String|Yes|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|StartTime|String|No|2019-12-21T12:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-22T12:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |
|SortBy|String|No|pv|The method that is used to sort the returned client IP addresses. Valid values: Valid values:

 -   **traf**: by network traffic.
-   **pv**: by the number of page views. This is the default value. |
|Percent|String|No|0.5|The percentage of network traffic or PVs of the web page. Valid values: 0 to 1. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|95994621-8382-464B-8762-C708E73568D1|The ID of the request. |
|DomainName|String|example.com|The accelerated domain name. |
|StartTime|String|2019-12-21T12:00:00Z|The beginning of the time range that was queried. |
|TopReferList|Array of ReferList| |A list of the most frequently requested web pages. |
|ReferList| | | |
|ReferDetail|String|live-xxx.com|The URLs to the most frequently requested web pages. |
|VisitData|String|3|The number of visits to the web page. |
|Flow|String|200|The amount of network traffic consumed for visiting the web page. Unit: bytes. |
|FlowProportion|Float|0.5|The proportion of the network traffic that has been consumed for visiting the web page. |
|VisitProportion|Float|0.5|The proportion of visits to the web page. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainTopReferVisit
&DomainName=example.com
&StartTime=2019-12-21T12:00:00Z
&EndTime=2019-12-22T12:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainTopReferVisitResponse>
  <TopReferList>
        <ReferList>
              <Flow>1557043</Flow>
              <VisitProportion>0.9078341013824884</VisitProportion>
              <VisitData>591</VisitData>
              <ReferDetail>-</ReferDetail>
              <FlowProportion>0.07801388057582173</FlowProportion>
        </ReferList>
        <ReferList>
              <Flow>18397394</Flow>
              <VisitProportion>0.08602150537634409</VisitProportion>
              <VisitData>56</VisitData>
              <ReferDetail>live-xxx.com</ReferDetail>
              <FlowProportion>0.9217806434519402</FlowProportion>
        </ReferList>
        <ReferList>
              <Flow>4101</Flow>
              <VisitProportion>0.006144393241167435</VisitProportion>
              <VisitData>4</VisitData>
              <ReferDetail>live-xxx.com</ReferDetail>
              <FlowProportion>0.00020547597223804668</FlowProportion>
        </ReferList>
  </TopReferList>
  <RequestId>BA64068A-D73C-4613-8AAB-E9374F78FB95</RequestId>
  <DomainName>example.com</DomainName>
  <StartTime>2019-12-21T12:00:00Z</StartTime>
</DescribeDomainTopReferVisitResponse>
```

`JSON` format

```
{
	"TopReferList": {
		"ReferList": [
			{
				"Flow": 1557043,
				"VisitProportion": "0.9078341013824884",
				"VisitData": 591,
				"ReferDetail": "-",
				"FlowProportion": "0.07801388057582173"
			},
			{
				"Flow": 18397394,
				"VisitProportion": "0.08602150537634409",
				"VisitData": 56,
				"ReferDetail": "live-xxx.com",
				"FlowProportion": "0.9217806434519402"
			},
			{
				"Flow": 4101,
				"VisitProportion": "0.006144393241167435",
				"VisitData": 4,
				"ReferDetail": "live-xxx.com",
				"FlowProportion": "0.00020547597223804668"
			}
		]
	},
	"RequestId": "BA64068A-D73C-4613-8AAB-E9374F78FB95",
	"DomainName": "example.com",
	"StartTime": "2019-12-21T12:00:00Z"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

