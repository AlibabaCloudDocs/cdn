# DescribeDomainBpsData

Queries the network bandwidth data of one or more accelerated domain name. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   The unit of bandwidth is bit/s.
-   If you do not set StartTime or EndTime, monitoring data within the last 24 hours is queried. If you set both StartTime and EndTime, monitoring data within the specified time range is queried.
-   You can specify one or more domain names. Separate multiple domain names with commas \(,\).
-   The maximum number of times that each user can call this operation per second is 150.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainBpsData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainBpsData|The operation that you want to perform. Set the value to **DescribeDomainBpsData**. |
|DomainName|String|No|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

 By default, this operation queries the number of queries per second for all accelerated domain names. |
|StartTime|String|No|2020-05-14T09:50:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2020-05-14T10:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

 -   If the time span between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time span between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   No less than 31 days: **86400**. Default value:**86400**. |
|IspNameEn|String|No|telecom|The name of the Internet service provider \(ISP\) for your Content Delivery Network \(CDN\) service. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query the ISP name.

 If you do not set this parameter, all ISPs are queried. |
|LocationNameEn|String|No|beijing|The name of the region. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query regions.

 If you do not set this parameter, all regions are queried. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|BpsDataPerInterval|Array of DataModule| |The bandwidth values collected at each interval. |
|DataModule| | | |
|DomesticValue|String|11286111|The bandwidth values in mainland China. When the bandwidth data is queried by ISP, no value is returned. |
|HttpsDomesticValue|String|11286111|The bandwidth values for HTTPS requests redirected to L1 nodes in mainland China. When the bandwidth data is queried by ISP, no value is returned. |
|HttpsOverseasValue|String|2000|The bandwidth values for HTTPS requests redirected to L1 nodes in regions outside mainland China. When the bandwidth data is queried by ISP, no value is returned. |
|HttpsValue|String|11288111|The bandwidth values for HTTPS requests redirected to L1 nodes. Unit: bit/s. |
|OverseasValue|String|2000|The bandwidth values in regions outside mainland China. When the bandwidth data is queried by ISP, no value is returned. Unit: bit/s. |
|TimeStamp|String|2015-12-10T20:00:00Z|The timestamp of the data returned. |
|Value|String|11288111|The bandwidth value. Unit: bit/s. |
|DataInterval|String|300|The time interval between the entries returned. Unit: seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|EndTime|String|2015-12-10T20:00Z|The end of the time range that was queried. |
|IspNameEn|String|unicom|The name of the Internet service provider \(ISP\) for your Dynamic Route for Content Delivery Network \(DCDN\) service. |
|LocationNameEn|String|beijing|The name of the region. |
|RequestId|String|3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F|The ID of the request. |
|StartTime|String|2020-05-14T09:50:00Z|The beginning of the time range that was queried. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainBpsData
&DomainName=example.com
&StartTime=2020-05-14T09:50:00Z
&EndTime=2020-05-14T10:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainBpsDataResponse>
	  <BpsDataPerInterval>
		    <DataModule>
			      <DomesticValue>11286111</DomesticValue>
			      <HttpsDomesticValue>11288111</HttpsDomesticValue>
			      <HttpsOverseasValue>2000</HttpsOverseasValue>
			      <HttpsValue>11288111</HttpsValue>
			      <OverseasValue>2000</OverseasValue>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>11288111</Value>
		    </DataModule>
	  </BpsDataPerInterval>
	  <DataInterval>300</DataInterval>
	  <DomainName>test.com</DomainName>
	  <EndTime>2015-12-10T21:00Z</EndTime>
	  <IspNameEn>unicom</IspNameEn>
	  <LocationNameEn>beijing</LocationNameEn>
	  <RequestId>3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F</RequestId>
	  <StartTime>2015-12-10T20:00Z</StartTime>	
</DescribeDomainBpsDataResponse>
```

`JSON` format

```
{
	"RequestId": "0AD87822-E8CE-436B-B434-C13F53B5B2D4",
	"EndTime": "2020-05-14T10:00:00Z",
	"DataInterval": 300,
	"StartTime": "2020-05-14T09:50:00Z",
	"BpsDataPerInterval": {
		"DataModule": [
			{
				"OverseasValue": 0,
				"HttpsValue": 0,
				"Value": "83.48266666666667",
				"HttpsDomesticValue": 0,
				"TimeStamp": "2020-05-14T09:50:00Z",
				"HttpsOverseasValue": 0,
				"DomesticValue": "83.48266666666667"
			},
			{
				"OverseasValue": 0,
				"HttpsValue": 0,
				"Value": 83.424,
				"HttpsDomesticValue": 0,
				"TimeStamp": "2020-05-14T09:55:00Z",
				"HttpsOverseasValue": 0,
				"DomesticValue": 83.424
			}
		]
	}
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is not supported.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

