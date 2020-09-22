# DescribeDomainTopClientIpVisit

Queries client IP addresses that are ranked by the number of requests or the network traffic usage within a specific time range. You can query data that has been collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, the data that has been collected in the last 24 hours is returned. If you set both StartTime and EndTime, the data that has been collected in the specified time range is returned.
-   The minimum time interval between the entries that are returned is one hour.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTopClientIpVisit&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainTopClientIpVisit|The operation that you want to perform. Set the value to **DescribeDomainTopClientIpVisit**. |
|DomainName|String|No|example.com|The accelerated domain name to which the client requests have been sent. You can specify multiple accelerated domain names and separate them with commas \(,\).

By default, all accelerated domain names are used to query data usage. |
|LocationNameEn|String|No|beijing|The English name of the region. You can specify multiple regions and separate them with commas \(,\).

To query region names, call the [DescribeCdnRegionAndIsp](~~91077~~) operation. If you do not set this parameter, the data for all regions is returned. If you set this parameter, the data for the specified region is returned. |
|StartTime|String|No|2019-09-30T16:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-10-01T16:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end of the time range to query. The end time must be later than the start time. |
|SortBy|String|No|traf|The method that is used to sort the returned client IP addresses. Valid values: Valid values:

-   **traf**: specifies that the returned data is sorted by network traffic. This is the default value.
-   **acc**: specifies that the returned data is sorted by the number of visits. |
|Limit|String|No|20|The maximum number of entries to return. Valid values: 1 to 100.

Default value: 20. The default value 20 specifies that the top 20 data entries are returned. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|ClientIpList|Array| |The list of returned client IP addresses. |
|Acc|Long|256|The total number of requests. |
|ClientIp|String|1.1.xxx|The returned client IP address. Only an IPv4 address is displayed. |
|Rank|Integer|2|The ranking of the returned client IP address. |
|Traffic|Long|1024|The total network traffic for the returned IP address. A client has used this IP address to connect to Alibaba Cloud Content Delivery Network \(CDN\). Unit: bytes. |
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainTopClientIpVisit
&DomainName=example.com
&StartTime=2019-09-30T16:00:00Z
&EndTime=2019-10-01T16:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainTopClientIpVisitResponse>
  <RequestId>64D28B53-5902-409B-94F6-FD46680144FE</RequestId>
  <ClientIpList>
        <Rank>1</Rank>
        <ClientIp>1.1.xx</ClientIp>
        <Traffic>1024</Traffic>
        <Acc>128</Acc>
  </ClientIpList>
  <ClientIpList>
        <Rank>2</Rank>
        <ClientIp>2.2.xx</ClientIp>
        <Traffic>2048</Traffic>
        <Acc>256</Acc>
  </ClientIpList>
</DescribeDomainTopClientIpVisitResponse>
```

`JSON` format

```
{
        "RequestId": "64D28B53-5902-409B-94F6-FD46680144FE",
    "ClientIpList": [
        {
            "Rank": 1,
            "ClientIp": "1.1.xx",
            "Traffic": 1024,
            "Acc": 128
        },
        {
            "Rank": 2,
            "ClientIp": "2.2.xx",
            "Traffic": 2048,
            "Acc": 256
        }
    ]
}
```

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is not supported.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

