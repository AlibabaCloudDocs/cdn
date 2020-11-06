# DescribeDomainQpsDataByLayer

Queries the number of queries per second at a specific layer for an accelerated domain name. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   You can specify one or more accelerated domain names. Separate multiple domain names with commas \(,\).
-   The maximum number of times that each user can call this operation per second is 20.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainQpsDataByLayer&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainQpsDataByLayer|The operation that you want to perform. Set the value to **DescribeDomainQpsDataByLayer**. |
|DomainName|String|No|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

 By default, this operation queries the number of queries per second for all accelerated domain names. |
|StartTime|String|No|2019-11-30T05:33:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-11-30T05:40:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

 -   If the time span between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time span between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   No less than 31 days: **86400**. Default value:**86400**. |
|IspNameEn|String|No|unicom|The name of the Internet service provider \(ISP\) for your Content Delivery Network \(CDN\) service. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query ISPs. If you do not set this parameter, all ISPs are queried. |
|LocationNameEn|String|No|beijing|The name of the region. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query regions. If you do not set this parameter, all regions are queried. |
|Layer|String|No|all|The layers at which you want to query the number of queries per second. Valid values:

 -   **Network layer**: **IPv4** and **IPv6**.
-   **Application layer**: **http**, **https**, and **quic**.
-   **all**: This is the default value. Both the network and application layers are included. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The time interval between the entries returned. Unit: seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|EndTime|String|2019-11-30T05:40:00Z|The end of the time range that was queried. |
|Layer|String|all|The layer at which the data was collected. |
|QpsDataInterval|Array of DataModule| |The number of queries per second at each time interval. |
|DataModule| | | |
|AccDomesticValue|String|12|The number of requests in mainland China. |
|AccOverseasValue|String|44|The number of requests outside mainland China. |
|AccValue|String|56|The number of requests in all regions. |
|DomesticValue|String|0.12|The number of queries per second in mainland China. |
|OverseasValue|String|0.44|The number of queries per second outside mainland China. |
|TimeStamp|String|2015-12-10T21:00:00Z|The timestamp of the data. |
|Value|String|0.56|The total number of queries per second in all regions. |
|RequestId|String|BEA5625F-8FCF-48F4-851B-CA63946DA664|The ID of the request. |
|StartTime|String|2019-11-30T05:33:00Z|The beginning of the time range that was queried. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainQpsDataByLayer
&DomainName=example.com
&StartTime=2019-11-30T05:33:00Z
&EndTime=2019-11-30T05:40:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainQpsDataByLayerResponse>
	  <QpsDataInterval>
		    <AccDomesticValue>12</AccDomesticValue>
		    <AccOverseasValue>44</AccOverseasValue>
		    <TimeStamp>2015-12-10T21:00:00Z</TimeStamp>
		    <Value>0.56</Value>
		    <AccValue>56</AccValue>
		    <DomesticValue>0.12</DomesticValue>
		    <OverseasValue>0.44</OverseasValue>
	  </QpsDataInterval>
	  <Layer>all</Layer>
	  <DomainName>example.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <RequestId>BEA5625F-8FCF-48F4-851B-CA63946DA664</RequestId>
	  <StartTime>2019-11-30T05:33:00Z</StartTime>
	  <EndTime>2019-11-30T05:40:00Z</EndTime>
</DescribeDomainQpsDataByLayerResponse>
```

`JSON` format

```
{
    "QpsDataInterval": {
                "AccDomesticValue":"12",
                "AccOverseasValue":"44",
                "TimeStamp": "2015-12-10T21:00:00Z",
                "Value": "0.56",
                "AccValue": "56" ,
                "DomesticValue":"0.12",
                "OverseasValue":"0.44"
            },
    "Layer": "all",
    "DomainName": "example.com",
    "DataInterval": "300",
    "RequestId": "BEA5625F-8FCF-48F4-851B-CA63946DA664",
    "StartTime": "2019-11-30T05:33:00Z",
    "EndTime": "2019-11-30T05:40:00Z"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

