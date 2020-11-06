# DescribeDomainRealTimeSrcHttpCodeData

Queries the total number and proportions of HTTP status codes returned from an accelerated domain name to back-to-origin requests. The data is collected at an interval of one minute. You can query data collected within the last seven days.

**When you call this operation, note that:**

-   The time range specified by the StartTime and EndTime parameters cannot exceed 24 hours.
-   If you do not set StartTime or EndTime, data collected within the last one hour is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   You can specify one or more accelerated domain names. Separate multiple domain names with commas \(,\).
-   The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeSrcHttpCodeData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainRealTimeSrcHttpCodeData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeSrcHttpCodeData**. |
|DomainName|String|Yes|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|StartTime|String|No|2019-11-30T04:40:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-11-30T05:40:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |
|IspNameEn|String|No|unicom|The name of the Internet Service Provider \(ISP\). You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query ISPs. If you do not set this parameter, all ISPs are queried. |
|LocationNameEn|String|No|beijing|The name of the region. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query regions. If you do not set this parameter, all regions are queried. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|60|The time interval between the entries returned. Unit: seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|EndTime|String|2019-11-30T05:40:00Z|The end of the time range that was queried. |
|RealTimeSrcHttpCodeData|Array of UsageData| |The proportions of HTTP status codes at each time interval. |
|UsageData| | | |
|TimeStamp|String|2015-11-30T05:40:00Z|The timestamp of the data. |
|Value|Array of RealTimeSrcCodeProportionData| |The proportions of HTTP status codes. |
|RealTimeSrcCodeProportionData| | | |
|Code|String|200|The HTTP status code. |
|Count|String|100|The total number of HTTP status codes returned. |
|Proportion|String|0.62015503875969|The proportion of the HTTP status code. |
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|The ID of the request. |
|StartTime|String|2019-11-30T05:33:00Z|The beginning of the time range that was queried. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeSrcHttpCodeData
&DomainName=example1.com,example2.com
&StartTime=2019-11-30T05:39:00Z
&EndTime=2019-11-30T05:40:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainRealTimeSrcHttpCodeDataResesponse>
	  <RealTimeSrcHttpCodeData>
		    <UsageData>
			      <TimeStamp>2019-11-30T05:40:00Z</TimeStamp>
			      <Value>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>66.046511627907</Proportion>
					          <Code>200</Code>
				        </RealTimeSrcCodeProportionData>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>4.72868217054264</Proportion>
					          <Code>206</Code>
				        </RealTimeSrcCodeProportionData>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>0.155038759689922</Proportion>
					          <Code>302</Code>
				        </RealTimeSrcCodeProportionData>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>0.62015503875969</Proportion>
					          <Code>304</Code>
				        </RealTimeSrcCodeProportionData>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>28.4496124031008</Proportion>
					          <Code>500</Code>
				        </RealTimeSrcCodeProportionData>
			      </Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2019-11-30T05:39:00Z</TimeStamp>
			      <Value>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>66.046511627907</Proportion>
					          <Code>200</Code>
				        </RealTimeSrcCodeProportionData>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>4.72868217054264</Proportion>
					          <Code>206</Code>
				        </RealTimeSrcCodeProportionData>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>0.155038759689922</Proportion>
					          <Code>302</Code>
				        </RealTimeSrcCodeProportionData>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>0.62015503875969</Proportion>
					          <Code>304</Code>
				        </RealTimeSrcCodeProportionData>
				        <RealTimeSrcCodeProportionData>
					          <Proportion>28.4496124031008</Proportion>
					          <Code>500</Code>
				        </RealTimeSrcCodeProportionData>
			      </Value>
		    </UsageData>
	  </RealTimeSrcHttpCodeData>
	  <DataInterval>60</DataInterval>
	  <RequestId>BC858082-736F-4A25-867B-E5B67C85ACF7</RequestId>
	  <DomainName>example1.com,example2.com</DomainName>
	  <EndTime>2019-11-30T05:40:00Z</EndTime>
	  <StartTime>2019-11-30T05:33:00Z</StartTime>
</DescribeDomainRealTimeSrcHttpCodeDataResesponse>
```

`JSON` format

```
{
    "RealTimeSrcHttpCodeData": {
        "UsageData": [
            {
                "TimeStamp": "2019-11-30T05:40:00Z",
                "Value": {
                    "RealTimeSrcCodeProportionData": [
                        {
                            "Proportion": "66.046511627907",
                            "Code": "200"
                        },
                        {
                            "Proportion": "4.72868217054264",
                            "Code": "206"
                        },
                        {
                            "Proportion": "0.155038759689922",
                            "Code": "302"
                        },
                        {
                            "Proportion": "0.62015503875969",
                            "Code": "304"
                        },
                        {
                            "Proportion": "28.4496124031008",
                            "Code": "500"
                        }
                    ]
                }
            },
            {
                "TimeStamp": "2019-11-30T05:39:00Z",
                "Value": {
                    "RealTimeSrcCodeProportionData": [
                        {
                            "Proportion": "66.046511627907",
                            "Code": "200"
                        },
                        {
                            "Proportion": "4.72868217054264",
                            "Code": "206"
                        },
                        {
                            "Proportion": "0.155038759689922",
                            "Code": "302"
                        },
                        {
                            "Proportion": "0.62015503875969",
                            "Code": "304"
                        },
                        {
                            "Proportion": "28.4496124031008",
                            "Code": "500"
                        }
                    ]
                }
            }
        ]
    },
    "DataInterval": "60",
    "RequestId": "BC858082-736F-4A25-867B-E5B67C85ACF7",
    "DomainName": "example1.com,example2.com",
    "EndTime": "2019-11-30T05:40:00Z",
    "StartTime": "2019-11-30T05:33:00Z"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

