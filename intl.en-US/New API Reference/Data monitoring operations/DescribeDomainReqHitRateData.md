# DescribeDomainReqHitRateData

Queries the request hit ratios of one or more accelerated domain names. Hit ratios are measured in percentage. You can query data collected within the last 90 days.

**Note:**

-   If you do not set **StartTime** or **EndTime**, data collected within the last 24 hours is queried. If you set both **StartTime** and **EndTime**, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainReqHitRateData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainReqHitRateData|The operation that you want to perform. Set the value to **DescribeDomainReqHitRateData**. |
|DomainName|String|No|www.yourdomain.com|The accelerated domain name. You can specify one or more domain names. Separate multiple domain names with commas \(,\).

By default, this operation queries the request hit ratios of all accelerated domain names. |
|StartTime|String|No|2017-12-21T08:00:00Z|The beginning of the time range to query.

Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2017-12-22T08:00:00Z|The end of the time range to query.

The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC.

**Note:** The end of the time range to query. The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries, in seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

-   If the time range between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time range between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   If the time range between StartTime and EndTime is 31 days or longer, the valid value is **86400**. Default value: **86400**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainName|String|test.com|The accelerated domain name. |
|DataInterval|String|300|The time interval between the data entries, in seconds. |
|StartTime|String|2017-12-21T08:00:00Z|The start of the time range that was query. |
|EndTime|String|2017-12-22T08:00:00Z|The end of the time range that was query. |
|ReqHitRateInterval|Array of DataModule| |The request hit ratio at each time interval. The hit ratio is measured in percentage. |
|DataModule| | | |
|TimeStamp|String|2017-12-22T08:00:00:00Z|The timestamp of the data returned. |
|Value|String|100.0|The request hit ratio. |
|HttpsValue|String|50.0|The hit ratio of HTTPS requests. |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeDomainReqHitRateData
&DomainName=test.com
&StartTime=2017-12-21T08:00:00Z
&EndTime=2017-12-22T08:00:00Z
&<common request parameters>
```

Sample responses

`XML` format

```
<DescribeDomainReqHitRateDataResponse>
      <DomainName>example.com</DomainName>
      <DataInterval>300</DataInterval>
      <RequestId>5ADA5190-EE5B-4EF2-BE00-DC441B8D81DD</RequestId>
      <StartTime>2017-12-21T08:00:00Z</StartTime>
      <EndTime>2017-12-22T08:00:00Z</EndTime>
      <ReqHitRateInterval>
            <DataModule>
                  <TimeStamp>2015-12-10T21:00:00Z</TimeStamp>
                  <Value>100.0</Value>
                  <HttpsValue>50.0</HttpsValue>
            </DataModule>
            <DataModule>
                  <TimeStamp>2015-12-10T20:35:00Z</TimeStamp>
                  <Value>100.0</Value>
                  <HttpsValue>50.0</HttpsValue>
            </DataModule>
      </ReqHitRateInterval>
</DescribeDomainReqHitRateDataResponse>
```

`JSON` format

```
{
    "DomainName": "example.com",
    "DataInterval": "300",
    "RequestId": "5ADA5190-EE5B-4EF2-BE00-DC441B8D81DD",
    "StartTime": "2017-12-21T08:00:00Z",
    "EndTime": "2017-12-22T08:00:00Z",
    "ReqHitRateInterval": {
        "DataModule": [
            {
                "TimeStamp": "2015-12-10T21:00:00Z",
                "Value": "100.0",
                "HttpsValue": "50.0"
            },
            {
                "TimeStamp": "2015-12-10T20:35:00Z",
                "Value": "100.0",
                "HttpsValue": "50.0"
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
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid. Rectify the start time and try again.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

