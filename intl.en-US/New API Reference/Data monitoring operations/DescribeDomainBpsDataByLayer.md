# DescribeDomainBpsDataByLayer

Queries the bandwidth information about accelerated domain names.

The maximum number of times that each user can call this operation per second is 20.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainBpsDataByLayer&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainBpsDataByLayer|The operation that you want to perform. Set the value to **DescribeDomainBpsDataByLayer**. |
|DomainName|String|No|example.com|The accelerated domain names that you want to query. Separate multiple domain names with commas \(,\).

 By default, this operation queries the bandwidth information about all accelerated domain names. |
|StartTime|String|No|2020-05-06T07:10:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2020-05-06T07:20:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the StartTime and EndTime parameters. Valid values:

 -   Less than 3 days: **300**, **3600**, and **86400**. If you do not specify a value, it is set to **300**.
-   3 to less than 31 days: **3600** and **86400**. If you do not specify a value, it is set to **3600**.
-   31 days and longer: **86400**. If you do not specify a value, it is set to **86400**. |
|IspNameEn|String|No|unicom|The name of the Internet service provider \(ISP\) for your Content Delivery Network \(CDN\) service. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query the ISP name. If you do not set this parameter, all ISPs are queried. |
|LocationNameEn|String|No|beijing|The name of the region. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query regions. If you do not set this parameter, all regions are queried. |
|Layer|String|No|IPv4|The layers at which you want to query the bandwidth information.

 -   Network layer: **IPv4** and **IPv6**.
-   Application layer: **HTTP**, **HTTPS**, and **QUIC**.
-   **all**: The default value. Both the network and application layers are included. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|BpsDataInterval|Array of DataModule| |The number of bytes per second at each time interval. |
|DataModule| | | |
|TimeStamp|String|2020-05-06T07:10:00Z|The timestamp of the data returned. |
|TrafficValue|String|2838|The total amount of network traffic. Unit: bytes. |
|Value|String|75.68|The peak bandwidth value. Unit: bit/s. |
|DataInterval|String|300|The time interval between the data entries. Unit: seconds. |
|RequestId|String|C565B910-BC3B-467B-9046-2A48566EA967|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeDomainBpsDataByLayer
&DomainName=example.com
&StartTime=2020-05-06T07:10:00Z
&EndTime=2020-05-06T07:20:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainBpsDataByLayerResponse>
  <RequestId>C565B910-BC3B-467B-9046-2A48566EA967</RequestId>
  <DataInterval>300</DataInterval>
  <BpsDataInterval>
        <DataModule>
              <Value>75.68</Value>
              <TrafficValue>2838</TrafficValue>
              <TimeStamp>2020-05-06T07:10:00Z</TimeStamp>
        </DataModule>
        <DataModule>
              <Value>99138.85333333333</Value>
              <TrafficValue>3717707</TrafficValue>
              <TimeStamp>2020-05-06T07:15:00Z</TimeStamp>
        </DataModule>
  </BpsDataInterval>
</DescribeDomainBpsDataByLayerResponse>
```

`JSON` format

```
{
	"RequestId": "C565B910-BC3B-467B-9046-2A48566EA967",
	"DataInterval": 300,
	"BpsDataInterval": {
		"DataModule": [
			{
				"Value": 75.68,
				"TrafficValue": 2838,
				"TimeStamp": "2020-05-06T07:10:00Z"
			},
			{
				"Value": "99138.85333333333",
				"TrafficValue": 3717707,
				"TimeStamp": "2020-05-06T07:15:00Z"
			}
		]
	}
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

