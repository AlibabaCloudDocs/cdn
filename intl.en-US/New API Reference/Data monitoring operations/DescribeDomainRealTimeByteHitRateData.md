# DescribeDomainRealTimeByteHitRateData

Queries byte hit ratios of an accelerated domain name. The data is collected at an interval of one minute. You can query data collected within the last seven days.

**When you call this operation, note that:**

-   The time range specified by the StartTime and EndTime parameters cannot exceed 24 hours.
-   If you do not set StartTime or EndTime, data collected within the last one hour is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   The network traffic destined for different domain names may be redirected to the same origin server. Therefore, the cache hit ratios may be inaccurate. The accuracy of query results is based on the actual configurations.
-   The maximum number of times that each user can call this operation per second is 600.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeByteHitRateData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeDomainRealTimeByteHitRateData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeByteHitRateData**. |
|DomainName|String|Yes|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|StartTime|String|No|2020-05-15T09:13:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2020-05-15T09:15:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end of the time range to query. The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Data|Array of ByteHitRateDataModel| |The response parameters. |
|ByteHitRateDataModel| | | |
|ByteHitRate|Float|0.8956940476262277|The cache hit ratio that is calculated based on response bytes. The cache hit ratio is measured in percentage. |
|TimeStamp|String|2019-11-30T05:40:00Z|The timestamp of the data returned. The time follows the ISO 8601 standard in the yyyy-MM-ddThh:mm:ssZ format. The time is displayed in UTC. |
|RequestId|String|70A26B11-3673-479C-AEA8-E03FC5D3496D|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeByteHitRateData
&DomainName=example.com
&StartTime=2020-05-15T09:13:00Z
&EndTime=2020-05-15T09:15:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainRealTimeByteHitRateDataResponse>
  <RequestId>95C90452-100B-4226-A63D-2D570CE2A971</RequestId>
  <Data>
        <ByteHitRateDataModel>
              <ByteHitRate>0.8956940476262277</ByteHitRate>
              <TimeStamp>2020-05-15T09:13:00Z</TimeStamp>
        </ByteHitRateDataModel>
        <ByteHitRateDataModel>
              <ByteHitRate>0.8429129920796812</ByteHitRate>
              <TimeStamp>2020-05-15T09:14:00Z</TimeStamp>
        </ByteHitRateDataModel>
  </Data>
</DescribeDomainRealTimeByteHitRateDataResponse>
```

`JSON` format

```
{
	"RequestId": "95C90452-100B-4226-A63D-2D570CE2A971",
	"Data": {
		"ByteHitRateDataModel": [
			{
				"ByteHitRate": 0.8956940476262277,
				"TimeStamp": "2020-05-15T09:13:00Z"
			},
			{
				"ByteHitRate": 0.8429129920796812,
				"TimeStamp": "2020-05-15T09:14:00Z"
			}
		]
	}
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidTime.Malformed|Specified StartTime or EndTime is malformed.|The error message returned because the format of the specified start time or end time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

