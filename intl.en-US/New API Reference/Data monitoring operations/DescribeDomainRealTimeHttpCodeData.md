# DescribeDomainRealTimeHttpCodeData

Queries the total number and proportions of HTTP status codes returned from an accelerated domain name. The data is collected every minute.

**Note:**

-   You can query data collected within the last seven days. The time range that is specified by the **StartTime** and **EndTime** parameters cannot exceed 24 hours in each call.
-   If you do not set **StartTime** or **EndTime**, data collected within the last one hour is queried. If you set both **StartTime** and **EndTime**, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeHttpCodeData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeDomainRealTimeHttpCodeData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeHttpCodeData**. |
|DomainName|String|Yes|example1.com,example2.com|The accelerated domain name. You can specify one or more accelerated domain names. Separate multiple accelerated domain names with commas \(,\).

 **Note:** You can specify at most 500 accelerated domain names in each call. |
|StartTime|String|No|2019-11-30T05:39:00Z|The beginning of the time range to query.

 The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC. |
|EndTime|String|No|2019-11-30T05:40:00Z|The end of the time range to query.

 The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC.

 **Note:** The end time must be later than the start time. |
|IspNameEn|String|No|unicom|The name of the Internet service provider \(ISP\). You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query ISP names. |
|LocationNameEn|String|No|beijing|The name of the region. If you do not set this parameter, all regions are queried. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query the most recent region list. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|60|The time interval between the data entries. Unit: seconds. |
|DomainName|String|example1.com,example2.com|The accelerated domain name. |
|EndTime|String|2019-11-29T05:42:00Z|The end of the time range that was query. |
|RealTimeHttpCodeData|Array of UsageData| |The proportions of HTTP status codes collected at each time interval. |
|UsageData| | | |
|TimeStamp|String|2019-11-29T05:39:00Z|The timestamp of the data entry. |
|Value|Array of RealTimeCodeProportionData| |The proportions of each HTTP status code. |
|RealTimeCodeProportionData| | | |
|Code|String|500|The HTTP status code. |
|Count|String|100|The total number of HTTP status codes returned. |
|Proportion|String|28.4496124031008|The proportion of the HTTP status code. |
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|The ID of the request. |
|StartTime|String|2019-11-29T05:39:00Z|The beginning of the time range that was queried. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeDomainRealTimeHttpCodeData
&DomainName=example1.com,example2.com
&StartTime=2019-11-29T05:39:00Z
&EndTime=2019-11-29T05:42:00Z
&<common request parameters>
```

Sample responses

`XML` format

```
<DescribeDomainRealTimeHttpCodeDataResponse>
  <DataInterval>60</DataInterval>
  <RequestId>99E690FC-86A3-4533-8F61-CF9E319141A4</RequestId>
  <DomainName>example1.com,example2.com</DomainName>
  <EndTime>2019-11-29T05:42:00Z</EndTime>
  <StartTime>2019-11-29T05:39:00Z</StartTime>
  <RealTimeHttpCodeData>
        <UsageData>
              <TimeStamp>2019-11-29T05:39:00Z</TimeStamp>
              <Value>
                    <RealTimeCodeProportionData>
                          <Count>2</Count>
                          <Proportion>100</Proportion>
                          <Code>200</Code>
                    </RealTimeCodeProportionData>
              </Value>
        </UsageData>
        <UsageData>
              <TimeStamp>2019-11-29T05:40:00Z</TimeStamp>
              <Value>
                    <RealTimeCodeProportionData>
                          <Count>1</Count>
                          <Proportion>50</Proportion>
                          <Code>200</Code>
                    </RealTimeCodeProportionData>
                    <RealTimeCodeProportionData>
                          <Count>1</Count>
                          <Proportion>50</Proportion>
                          <Code>304</Code>
                    </RealTimeCodeProportionData>
              </Value>
        </UsageData>
        <UsageData>
              <TimeStamp>2019-11-29T05:41:00Z</TimeStamp>
              <Value>
                    <RealTimeCodeProportionData>
                          <Count>11</Count>
                          <Proportion>91.66666666666666</Proportion>
                          <Code>200</Code>
                    </RealTimeCodeProportionData>
                    <RealTimeCodeProportionData>
                          <Count>1</Count>
                          <Proportion>8.333333333333332</Proportion>
                          <Code>206</Code>
                    </RealTimeCodeProportionData>
              </Value>
        </UsageData>
  </RealTimeHttpCodeData>
</DescribeDomainRealTimeHttpCodeDataResponse>
```

`JSON` format

```
{
	"DataInterval": 60,
	"RequestId": "99E690FC-86A3-4533-8F61-CF9E319141A4",
	"DomainName": "example1.com,example2.com",
	"EndTime": "2019-11-29T05:42:00Z",
	"StartTime": "2019-11-29T05:39:00Z",
	"RealTimeHttpCodeData": {
		"UsageData": [
			{
				"TimeStamp": "2019-11-29T05:39:00Z",
				"Value": {
					"RealTimeCodeProportionData": [
						{
							"Count": 2,
							"Proportion": 100,
							"Code": "200"
						}
					]
				}
			},
			{
				"TimeStamp": "2019-11-29T05:40:00Z",
				"Value": {
					"RealTimeCodeProportionData": [
						{
							"Count": 1,
							"Proportion": 50,
							"Code": "200"
						},
						{
							"Count": 1,
							"Proportion": 50,
							"Code": "304"
						}
					]
				}
			},
			{
				"TimeStamp": "2019-11-29T05:41:00Z",
				"Value": {
					"RealTimeCodeProportionData": [
						{
							"Count": 11,
							"Proportion": "91.66666666666666",
							"Code": "200"
						},
						{
							"Count": 1,
							"Proportion": "8.333333333333332",
							"Code": "206"
						}
					]
				}
			}
		]
	}
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

