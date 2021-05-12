# DescribeDomainTrafficData

Queries the monitoring data of network traffic for one or more accelerated domain names. The network traffic is measured in bytes. You can query data within the last 90 days.

**Note:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   The maximum number of times that you can call this operation with each Alibaba Cloud account per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTrafficData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeDomainTrafficData|The operation that you want to perform. Set the value to **DescribeDomainTrafficData**. |
|DomainName|String|No|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

 By default, this operation queries the monitoring data of network traffic for all your accelerated domain names. |
|StartTime|String|No|2015-12-10T20:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2015-12-10T21:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end of the time range to query. The end time must be later than the start time. |
|LocationNameEn|String|No|beijing|The name of the region. You can call the [DDescribeCdnRegionAndIsp](~~91077~~) operation to query the most recent region list.

 If you do not set this parameter, monitoring data in all regions are queried. |
|IspNameEn|String|No|unicom|The name of the Internet service provider \(ISP\) for your Content Delivery Network \(CDN\) service. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query the ISP name.

 If you do not set this parameter, data of all ISPs are queried. |
|Interval|String|No|300|The data collection interval. Unit: second. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

 -   If the time range between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time range between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   If the time range between StartTime and EndTime is 31 days or longer, the valid value is **86400**. Default value: **86400**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The time interval between the data entries returned. Unit: seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|EndTime|String|2015-12-10T21:00:00Z|The end of the time range that was query. |
|RequestId|String|B955107D-E658-4E77-B913-E0AC3D31693E|The ID of the request. |
|StartTime|String|2015-12-10T20:00:00Z|The beginning of the time range that was queried. |
|TrafficDataPerInterval|Array of DataModule| |The monitoring data of network traffic that was collected at each interval. |
|DataModule| | | |
|DomesticValue|String|0|The amount of network traffic in mainland China. |
|HttpsDomesticValue|String|0|The amount of HTTPS network traffic on L1 CDN nodes in mainland China. |
|HttpsOverseasValue|String|0|The amount of HTTPS network traffic on L1 CDN nodes outside mainland China. |
|HttpsValue|String|423304182|The total amount of HTTPS network traffic on L1 CDN nodes. |
|OverseasValue|String|0|The amount of network traffic outside mainland China. |
|TimeStamp|String|example.com|The timestamp of the data returned. |
|Value|String|423304182|The total amount of network traffic. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/?Action=DescribeDomainTrafficData
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainTrafficDataResponse>
	  <DomainName>example.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <TrafficDataPerInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>423304182</Value>
			      <DomesticValue>0</DomesticValue>
			      <OverseasValue>0</OverseasValue>
			      <HttpsValue>423304182</HttpsValue>
			      <HttpsDomesticValue>0</HttpsDomesticValue>
			      <HttpsOverseasValue>0</HttpsOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:05:00Z</TimeStamp>
			      <Value>454680793</Value>
			      <DomesticValue>0</DomesticValue>
			      <OverseasValue>0</OverseasValue>
			      <HttpsValue>423304182</HttpsValue>
			      <HttpsDomesticValue>0</HttpsDomesticValue>
			      <HttpsOverseasValue>0</HttpsOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:10:00Z</TimeStamp>
			      <Value>501718342</Value>
			      <DomesticValue>0</DomesticValue>
			      <OverseasValue>0</OverseasValue>
			      <HttpsValue>423304182</HttpsValue>
			      <HttpsDomesticValue>0</HttpsDomesticValue>
			      <HttpsOverseasValue>0</HttpsOverseasValue>
		    </DataModule>
	  </TrafficDataPerInterval>
	  <RequestId>B955107D-E658-4E77-B913-E0AC3D31693E</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T21:00:00Z</EndTime>
</DescribeDomainTrafficDataResponse>
```

`JSON` format

```
{
    "DomainName": "example.com",
    "DataInterval": "300",
    "TrafficDataPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2015-12-10T20:00:00Z",
                "Value": "423304182",
                "DomesticValue": "0",
                "OverseasValue": "0",
                "HttpsValue": "423304182",
                "HttpsDomesticValue": "0",
                "HttpsOverseasValue": "0"
            },
            {
                "TimeStamp": "2015-12-10T20:05:00Z",
                "Value": "454680793",
                "DomesticValue": "0",
                "OverseasValue": "0",
                "HttpsValue": "423304182",
                "HttpsDomesticValue": "0",
                "HttpsOverseasValue": "0"
            },
            {
                "TimeStamp": "2015-12-10T20:10:00Z",
                "Value": "501718342",
                "DomesticValue": "0",
                "OverseasValue": "0",
                "HttpsValue": "423304182",
                "HttpsDomesticValue": "0",
                "HttpsOverseasValue": "0"
            }
        ]
    },
    "RequestId": "B955107D-E658-4E77-B913-E0AC3D31693E",
    "StartTime": "2015-12-10T20:00:00Z",
    "EndTime": "2015-12-10T21:00:00Z"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

