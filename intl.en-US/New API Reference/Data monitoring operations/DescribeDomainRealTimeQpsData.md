# DescribeDomainRealTimeQpsData

Queries the number of queries per second for one or more accelerated domain names. The data is collected every minute.

**Note:**

-   You can query data collected within the last seven days. The time range specified by the **StartTime** and **EndTime** parameters cannot exceed 24 hours in each call.
-   If you do not set **StartTime** or **EndTime**, data collected within the last one hour is queried. If you set both **StartTime** and **EndTime**, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 600.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeQpsData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeDomainRealTimeQpsData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeQpsData**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify one or more accelerated domain names. Separate multiple accelerated domain names with commas \(,\).

 **Note:** You can specify at most 500 accelerated domain names in each call. |
|IspNameEn|String|No|telecom|The name of the Internet service provider \(ISP\) for your Alibaba Cloud Content Delivery Network \(CDN\) service.

 If you do not set this parameter, all ISPs are queried. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query ISP names. |
|LocationNameEn|String|No|beijing|The name of the region.

 If you do not set this parameter, all regions are queried. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query the most recent region list. |
|StartTime|String|No|2019-12-02T11:25:00Z|The beginning of the time range to query.

 The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC. |
|EndTime|String|No|2019-12-02T11:26:00Z|The end of the time range to query.

 The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC.

 **Note:** The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Data|Array of QpsModel| |The detailed information about queries per second of the specified domain name. |
|QpsModel| | | |
|Qps|Float|1851.25|The number of queries per second. |
|TimeStamp|String|2019-12-02T11:25:00Z|The timestamp of the data entry. The time follows the ISO 8601 standard in the yyyy-MM-ddThh:mmZ format. The time is displayed in UTC. |
|RequestId|String|32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D|The ID of the request. |

## Examples

Sample requests

```
http(s):///cdn.aliyuncs.com/? Action=DescribeDomainRealTimeQpsData
&DomainName=example.com
&StartTime=2019-12-02T11:25:00Z
&EndTime=2019-12-02T11:26:00Z
&IspNameEn=telecom
&LocationNameEn=beijing
&<common request parameters>
```

Sample responses

`XML` format

```
<DescribeDomainRealTimeQpsDataResponse>
	  <Data>
		    <QpsModel>
			      <TimeStamp>2019-12-02T11:26:00Z</TimeStamp>
			      <Qps>1851.25</Qps>
		    </QpsModel>
		    <QpsModel>
			      <TimeStamp>2019-12-02T11:25:00Z</TimeStamp>
			      <Qps>8967.7</Qps>
		    </QpsModel>
	  </Data>
	  <RequestId>32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D</RequestId>
</DescribeDomainRealTimeQpsDataResponse>
```

`JSON` format

```
{
	"Data": {
		"QpsModel": [{
			"TimeStamp": "2019-12-02T11:26:00Z",
			"Qps": 1851.25
		}, {
			"TimeStamp": "2019-12-02T11:25:00Z",
			"Qps": 8967.7
		}]
	},
	"RequestId": "32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidTime.Malformed|Specified StartTime or EndTime is malformed.|The error message returned because the format of the specified start time or end time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

