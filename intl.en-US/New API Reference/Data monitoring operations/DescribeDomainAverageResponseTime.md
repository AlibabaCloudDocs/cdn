# DescribeDomainAverageResponseTime

Queries the average response time of one or more accelerated domain names. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainAverageResponseTime&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainAverageResponseTime|The operation that you want to perform. Set the value to **DescribeDomainAverageResponseTime**. |
|TimeMerge|String|No|1|Specifies whether to automatically set the interval. If you set **TimeMerge** to **1**, the value of the Interval parameter is automatically assigned based on the StartTime and EndTime parameters. You can set either this parameter or the Interval parameter. |
|DomainType|String|No|domaintype|The query type. When you set the value to dynamic, this operation queries the average response time of dynamic resources and static resources. If you do not set this parameter, this operation queries the average response time of only static resources. By default, this parameter is not set. |
|DomainName|String|No|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

By default, all accelerated domain names are queried. |
|StartTime|String|No|2019-11-30T05:33:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-11-30T05:40:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

-   If the time span between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time span between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   If the time span between StartTime and EndTime is 31 days or longer, the valid value is **86400**. Default value: **86400**. |
|IspNameEn|String|No|unicom|The name of the Internet service provider \(ISP\) for your Content Delivery Network \(CDN\) service. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query ISPs. If you do not set this parameter, all ISPs are queried. |
|LocationNameEn|String|No|beijing|The name of the region. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query the most recent region list. If you do not set this parameter, all regions are queried. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|AvgRTPerInterval|Array of DataModule| |The average response time collected at each time interval. |
|DataModule| | | |
|TimeStamp|String|2015-12-10T20:00:00Z|The timestamp of the data returned. |
|Value|String|3|The average response time. |
|DataInterval|String|300|The time interval between the data entries returned. |
|DomainName|String|example.com|The accelerated domain name. |
|StartTime|String|2019-11-30T05:33:00Z|The beginning of the time range that was queried. |
|EndTime|String|2019-11-30T05:40:00Z|The end of the time range that was queried. |
|RequestId|String|3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainAverageResponseTime
&DomainName=example.com
&StartTime=2019-11-30T05:33:00Z
&EndTime=2019-11-30T05:40:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainAverageResponseTimeResponse>
      <DomainName>example.com</DomainName>
      <RequestId>3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F</RequestId>
      <StartTime>2019-11-30T05:33:00Z</StartTime>
      <EndTime>2019-11-30T05:40:00Z</EndTime>
      <DataInterval>300</DataInterval>
      <AvgRTPerInterval>
            <DataModule>
                  <TimeStamp>2019-11-30T05:33:00Z</TimeStamp>
                  <Value>3</Value>
            </DataModule>
            <DataModule>
                  <TimeStamp>2019-11-30T05:38:00Z</TimeStamp>
                  <Value>3</Value>
            </DataModule>
      </AvgRTPerInterval>
</DescribeDomainAverageResponseTimeResponse>
```

`JSON` format

```
{
    "DomainName": "example.com",
    "RequestId": "3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F",
    "StartTime": "2019-11-30T05:40:00Z",
    "EndTime": "2019-11-30T05:33:00Z",
    "DataInterval": "300",
    "AvgRTPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2019-11-30T05:33:00Z",
                "Value": "3"
            },
            {
                "TimeStamp": "2019-11-30T05:38:00Z",
                "Value": "3"
            }
        ]
    }
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the specified end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

