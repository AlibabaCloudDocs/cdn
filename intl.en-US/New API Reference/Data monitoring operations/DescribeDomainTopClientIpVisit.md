# DescribeDomainTopClientIpVisit

Queries client IP addresses that are ranked by the number of requests or the amount of network traffic within a specific time range for accelerated domain names. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   Data is collected at an interval of one hour.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTopClientIpVisit&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainTopClientIpVisit|The operation that you want to perform. Set the value to **DescribeDomainTopClientIpVisit**. |
|DomainName|String|No|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

 By default, all accelerated domain names are queried. |
|LocationNameEn|String|No|beijing|The name of the region. You can specify multiple regions and separate them with commas \(,\).

 You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query regions. |
|StartTime|String|No|2019-09-30T16:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-10-01T16:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |
|SortBy|String|No|traf|The method that is used to sort the client IP addresses. Valid values:

 -   **traf**: specifies that the client IP addresses are sorted by network traffic. This is the default value.
-   **acc**: specifies that the client IP addresses are sorted by the number of requests. |
|Limit|String|No|20|The maximum number of entries to return. Valid values: 1 to 100.

 Default value: 20. The default value 20 specifies that the top 20 data entries are returned. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|ClientIpList|Array of ClientIp| |A list of client IP addresses returned. |
|Acc|Long|256|The total number of requests. |
|ClientIp|String|1.1.xxx|The client IP address returned. Only IPv4 addressed are supported. |
|Rank|Integer|2|The ranking of the client IP address returned. |
|Traffic|Long|1024|The total amount of network traffic consumed by the IP address. Unit: bytes. |
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

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is not supported.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

