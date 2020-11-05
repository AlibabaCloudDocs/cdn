# DescribeDomainSrcBpsData

Queries the bandwidth values of back-to-origin requests. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   The unit of bandwidth values is bit/s.
-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   You can specify one or more domain names. Separate multiple domain names with commas \(,\).
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainSrcBpsData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainSrcBpsData|The operation that you want to perform. Set the value to **DescribeDomainSrcBpsData**. |
|DomainName|String|No|www.yourdomain.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

By default, this operation queries the bandwidth values of back-to-origin requests for all accelerated domain names. |
|StartTime|String|No|2019-12-10T20:00:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-10T20:30:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

-   If the time span between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time span between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   If the time span between StartTime and EndTime is 31 days or longer, the valid value is **86400**. Default value: **86400**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The time interval between the entries returned. Unit: seconds. |
|DomainName|String|yourdomain.com|The accelerated domain name. |
|StartTime|String|2019-12-10T20:00:00Z|The beginning of the time range that was queried. |
|EndTime|String|2019-12-10T20:30:00Z|The end of the time range that was queried. |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |
|SrcBpsDataPerInterval|Array of DataModule| |The bandwidth values collected at each interval. |
|DataModule| | | |
|HttpsValue|String|10|The bandwidth values of HTTPS requests. |
|TimeStamp|String|2019-12-10T20:00:00Z|The timestamp of the data. |
|Value|String|500|The bandwidth value. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainSrcBpsData
&DomainName=test.com
&StartTime=2019-12-10T20:00:00Z
&EndTime=2019-12-10T20:30:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainSrcBpsDataResponse>
  <SrcBpsDataPerInterval>
        <DataModule>
              <TimeStamp>2019-12-10T20:00:00Z</TimeStamp>
              <Value>31.709333333333337</Value>
              <HttpsValue>0</HttpsValue>
        </DataModule>
        <DataModule>
              <TimeStamp>2019-12-10T20:05:00Z</TimeStamp>
              <Value>31.709333333333337</Value>
              <HttpsValue>0</HttpsValue>
        </DataModule>
        <DataModule>
              <TimeStamp>2019-12-10T20:10:00Z</TimeStamp>
              <Value>31.709333333333337</Value>
              <HttpsValue>0</HttpsValue>
        </DataModule>
        <DataModule>
              <TimeStamp>2019-12-10T20:15:00Z</TimeStamp>
              <Value>31.709333333333337</Value>
              <HttpsValue>0</HttpsValue>
        </DataModule>
        <DataModule>
              <TimeStamp>2019-12-10T20:20:00Z</TimeStamp>
              <Value>31.709333333333337</Value>
              <HttpsValue>0</HttpsValue>
        </DataModule>
        <DataModule>
              <TimeStamp>2019-12-10T20:25:00Z</TimeStamp>
              <Value>43.32533333333333</Value>
              <HttpsValue>0</HttpsValue>
        </DataModule>
  </SrcBpsDataPerInterval>
  <DataInterval>300</DataInterval>
  <RequestId>28B4EBA6-0AF4-407A-AAC9-6BC5F8D8158B</RequestId>
  <EndTime>2019-12-10T20:30:00Z</EndTime>
  <StartTime>2019-12-10T20:00:00Z</StartTime>
</DescribeDomainSrcBpsDataResponse>
```

`JSON` format

```
{
    "SrcBpsDataPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2019-12-10T20:00:00Z",
                "Value": "31.709333333333337",
                "HttpsValue": 0
            },
            {
                "TimeStamp": "2019-12-10T20:05:00Z",
                "Value": "31.709333333333337",
                "HttpsValue": 0
            },
            {
                "TimeStamp": "2019-12-10T20:10:00Z",
                "Value": "31.709333333333337",
                "HttpsValue": 0
            },
            {
                "TimeStamp": "2019-12-10T20:15:00Z",
                "Value": "31.709333333333337",
                "HttpsValue": 0
            },
            {
                "TimeStamp": "2019-12-10T20:20:00Z",
                "Value": "31.709333333333337",
                "HttpsValue": 0
            },
            {
                "TimeStamp": "2019-12-10T20:25:00Z",
                "Value": "43.32533333333333",
                "HttpsValue": 0
            }
        ]
    },
    "DataInterval": 300,
    "RequestId": "28B4EBA6-0AF4-407A-AAC9-6BC5F8D8158B",
    "EndTime": "2019-12-10T20:30:00Z",
    "StartTime": "2019-12-10T20:00:00Z"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|MissingParameter|StartTime and EndTime can not be single.|The error message returned because both the StartTime and EndTime parameters must be set.|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|The error message returned because the end time must be later than the start time.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is not supported.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

