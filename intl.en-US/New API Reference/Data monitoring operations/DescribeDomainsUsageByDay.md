# DescribeDomainsUsageByDay

You can call this operation to query the monitoring data of an accelerated domain name. The data was collected at an interval of one day. You can query data within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data within the last 24 hours is queried. If you set both StartTime and EndTime, data within the specified time range is queried.
-   You can query the monitoring data of a specific accelerated domain name or all accelerated domain names under your account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainsUsageByDay&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeDomainsUsageByDay|The operation that you want to perform. Set the value to **DescribeDomainsUsageByDay**. |
|DomainName|String|No|www.yourdomain.com|The accelerated domain name. You can specify only one domain name.

 If you do not specified an accelerated domain name, all accelerated domain names under your account are queried. |
|StartTime|String|No|2019-12-22T08:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-23T09:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|C88EF8ED-72F0-45EA-9E86-95114E224FC5|The ID of the request. |
|DomainName|String|test.com|The accelerated domain name. |
|DataInterval|String|86400|The time interval between the data entries. Unit: second. |
|StartTime|String|2019-12-22T08:00:00Z|The beginning of the time range that was queried. |
|EndTime|String|2019-12-23T09:00:00Z|The end of the time range that was queried. |
|UsageByDays|Array| |The monitoring data collected at each time interval. |
|UsageByDay| | | |
|BytesHitRate|String|97.46250599529726|The cache hit ratio that is calculated based on response bytes. |
|TimeStamp|String|2019-12-22|The timestamp of the data returned. |
|Qps|String|7.466354166666667|The number of queries per second. |
|RequestHitRate|String|70.24770071912111|The cache hit ratio that is calculated based on requests. |
|MaxBps|String|306747.76|The peak bandwidth. |
|MaxBpsTime|String|2019-12-23 10:55:00|The time when the bandwidth reached the peak value. |
|MaxSrcBps|String|72584.072|The peak bandwidth of back-to-origin requests. |
|TotalAccess|String|645093|The total number of back-to-origin requests. |
|MaxSrcBpsTime|String|2019-12-23 11:45:00|The time when the bandwidth of back-to-origin requests reached the peak value. |
|TotalTraffic|String|564300099309|The total amount of network traffic. |
|UsageTotal|Struct| |The summarized monitoring data. |
|BytesHitRate|String|97.03110726801242|The cache hit ratio that is calculated based on response bytes. |
|RequestHitRate|String|69.92610837438424|The cache hit ratio that is calculated based on requests. |
|MaxBps|String|1.0747912780000001E8|The peak bandwidth. |
|MaxBpsTime|String|2019-12-23 10:55:00|The time when the bandwidth reached the peak value. |
|MaxSrcBps|String|72584.072|The peak bandwidth of back-to-origin requests. |
|TotalAccess|String|1319500|The total number of back-to-origin requests. |
|MaxSrcBpsTime|String|2019-12-23 11:45:00|The time when the bandwidth of back-to-origin requests reached the peak value. |
|TotalTraffic|String|1117711832100|The total amount of network traffic. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainsUsageByDay
&DomainName=test.com
&StartTime=2019-12-22T08:00:00Z
&EndTime=2019-12-23T09:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainsUsageByDayResponse>
  <UsageTotal>
        <RequestHitRate>0.46869615163699024</RequestHitRate>
        <MaxSrcBpsTime>2019-12-23 11:45:00</MaxSrcBpsTime>
        <MaxSrcBps>72584.072</MaxSrcBps>
        <MaxBps>306747.76</MaxBps>
        <TotalTraffic>220090843</TotalTraffic>
        <TotalAccess>1741</TotalAccess>
        <MaxBpsTime>2019-12-23 10:55:00</MaxBpsTime>
        <BytesHitRate>0.9338625414779297</BytesHitRate>
  </UsageTotal>
  <UsageByDays>
        <UsageByDay>
              <TimeStamp>2019-12-23</TimeStamp>
              <RequestHitRate>0.46869615163699024</RequestHitRate>
              <MaxSrcBpsTime>2019-12-23 11:45:00</MaxSrcBpsTime>
              <MaxSrcBps>72584.072</MaxSrcBps>
              <MaxBps>306747.76</MaxBps>
              <TotalTraffic>220090843</TotalTraffic>
              <TotalAccess>1741</TotalAccess>
              <MaxBpsTime>2019-12-23 10:55:00</MaxBpsTime>
              <Qps>0.020150462962962964</Qps>
              <BytesHitRate>0.9338625398107486</BytesHitRate>
        </UsageByDay>
  </UsageByDays>
  <RequestId>0DE5531F-A7C2-4788-A35A-38883193B2D8</RequestId>
  <EndTime>2019-12-23T09:00:00Z</EndTime>
  <StartTime>2019-12-22T08:00:00Z</StartTime>
  <DomainName>test.com</DomainName>
  <DataInterval>86400</DataInterval>
</DescribeDomainsUsageByDayResponse>
```

`JSON` format

```
{
	"UsageTotal": {
		"RequestHitRate": "0.46869615163699024",
		"MaxSrcBpsTime": "2019-12-23 11:45:00",
		"MaxSrcBps": 72584.072,
		"MaxBps": 306747.76,
		"TotalTraffic": 220090843,
		"TotalAccess": 1741,
		"MaxBpsTime": "2019-12-23 10:55:00",
		"BytesHitRate": "0.9338625414779297"
	},
	"UsageByDays": {
		"UsageByDay": [
			{
				"TimeStamp": "2019-12-23",
				"RequestHitRate": "0.46869615163699024",
				"MaxSrcBpsTime": "2019-12-23 11:45:00",
				"MaxSrcBps": 72584.072,
				"MaxBps": 306747.76,
				"TotalTraffic": 220090843,
				"TotalAccess": 1741,
				"MaxBpsTime": "2019-12-23 10:55:00",
				"Qps": "0.020150462962962964",
				"BytesHitRate": "0.9338625398107486"
			}
		]
	},
	"RequestId": "0DE5531F-A7C2-4788-A35A-38883193B2D8",
	"EndTime": "2019-12-23T09:00:00Z",
	"StartTime": "2019-12-22T08:00:00Z",
    "DomainName":"test.com",
    "DataInterval":86400
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the specified end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid.|
|404|InvalidDomain.NotFound|The domain provided does not exist in our records.|The error message returned because the specified domain name does not exist or is not under the current account. Check whether the specified name is correctly entered, whether it is under the current account, and whether it is expired.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

