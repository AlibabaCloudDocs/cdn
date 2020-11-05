# DescribeDomainRealTimeSrcBpsData

Queries the bandwidth data of back-to-origin requests. The data is collected at an interval of one minute. You can query data collected within the last seven days.

**When you call this operation, note that:**

-   The time range specified by the StartTime and EndTime parameters cannot exceed 24 hours.
-   If you do not set StartTime or EndTime, data collected within the last one hour is queried.
-   You can specify one or more accelerated domain names. Separate multiple domain names with commas \(,\).
-   The unit of bandwidth is bit/s.
-   The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeSrcBpsData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainRealTimeSrcBpsData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeSrcBpsData**. |
|DomainName|String|Yes|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|StartTime|String|No|2019-12-10T20:00:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-10T20:01:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The time interval between the entries returned. Unit: seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|EndTime|String|2019-12-10T20:01:00Z|The end of the time range that was queried. |
|RealTimeSrcBpsDataPerInterval|Array of DataModule| |The back-to-origin bandwidth collected at each interval. |
|DataModule| | | |
|TimeStamp|String|2019-12-10T20:01:00Z|The timestamp of the data returned. |
|Value|String|0|The bandwidth values. |
|RequestId|String|7CBCD6AD-B016-42E5-AE0B-B3731DE8F755|The ID of the request. |
|StartTime|String|2019-12-10T20:00:00Z|The beginning of the time range that was queried. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeSrcBpsData
&DomainName=example.com
&StartTime=2019-12-10T20:00:00Z
&EndTime=2019-12-10T20:01:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainRealTimeSrcBpsDataResponse>
      <DomainName>example.com</DomainName>
      <DataInterval>60</DataInterval>
      <RealTimeSrcBpsDataPerInterval>
            <DataModule>
                  <TimeStamp>2019-12-10T20:00:00Z</TimeStamp>
                  <Value>821</Value>
            </DataModule>
            <DataModule>
                  <TimeStamp>2019-12-10T20:01:00Z</TimeStamp>
                  <Value>0</Value>
            </DataModule>
      </RealTimeSrcBpsDataPerInterval>
      <RequestId>7CBCD6AD-B016-42E5-AE0B-B3731DE8F755</RequestId>
      <StartTime>2019-12-10T20:00:00Z</StartTime>
      <EndTime>2019-12-10T20:01:00Z</EndTime>
</DescribeDomainRealTimeSrcBpsDataResponse>
```

`JSON` format

```
{
    "DomainName": "example.com",
    "DataInterval": "60",
    "RealTimeSrcBpsDataPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2019-12-10T20:00:00Z",
                "Value": "821"
            },
            {
                "TimeStamp": "2019-12-10T20:01:00Z",
                "Value": "0"
            }
        ]
    },
    "RequestId": "7CBCD6AD-B016-42E5-AE0B-B3731DE8F755",
    "StartTime": "2019-12-10T20:00:00Z",
    "EndTime": "2019-12-10T20:01:00Z"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

