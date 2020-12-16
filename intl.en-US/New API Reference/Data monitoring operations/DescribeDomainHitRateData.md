# DescribeDomainHitRateData

Queries the byte hit ratios of an accelerated domain name. Hit ratios are measured in percentage. You can query data collected within the last 90 days.

**Note:**

-   If you do not set **StartTime** or **EndTime**, data collected within the last 24 hours is queried. If you set both **StartTime** and **EndTime**, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainHitRateData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainHitRateData|The operation that you want to perform. Set the value to **DescribeDomainHitRateData**. |
|DomainName|String|No|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

By default, all accelerated domain names are queried. |
|StartTime|String|No|2019-12-30T08:00:00Z|The start of the time range to query.

Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-30T08:10:00Z|The end of the time range to query.

The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC.

**Note:** The end of the time range to query. The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

-   If the time range between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time range between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   If the time range between StartTime and EndTime is 31 days or longer, the valid value is **86400**. Default value: **86400**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainName|String|example.com|The accelerated domain name. |
|DataInterval|String|300|The time interval between the returned entries, in seconds. |
|StartTime|String|2019-12-30T08:00:00Z|The beginning of the time range that was queried. |
|EndTime|String|2019-12-30T08:10:00Z|The end of the time range that was queried. |
|HitRateInterval|Array of DataModule| |The byte hit ratio at each data sampling interval. The byte hit ratio is measured in percentage. |
|DataModule| | | |
|TimeStamp|String|2019-12-30T08:00:00Z|The timestamp of the returned data. |
|Value|String|100.0|The further details of the hit ratio. |
|HttpsValue|String|50.0|The byte hit ratio of the HTTPS request. |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeDomainHitRateData
&DomainName=example.com
&StartTime=2019-12-30T08:00:00Z
&EndTime=2019-12-30T08:10:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainHitRateDataResponse>
  <DomainName>example.com</DomainName>
  <DataInterval>300</DataInterval>
  <RequestId>0A521165-99B6-41EF-B166-5B8B8068E1CF</RequestId>
  <EndTime>2019-12-30T08:10:00Z</EndTime>
  <StartTime>2019-12-30T08:00:00Z</StartTime>
  <HitRateInterval>
        <DataModule>
              <TimeStamp>2019-12-30T08:00:00Z</TimeStamp>
              <Value>74.82824427480917</Value>
              <HttpsValue>0</HttpsValue>
        </DataModule>
        <DataModule>
              <TimeStamp>2019-12-30T08:05:00Z</TimeStamp>
              <Value>62.83283497081019</Value>
              <HttpsValue>100</HttpsValue>
        </DataModule>
  </HitRateInterval>
</DescribeDomainHitRateDataResponse>
```

`JSON` format

```
{    
    "DomainName":"example.com",
    "DataInterval": 300,
    "RequestId": "0A521165-99B6-41EF-B166-5B8B8068E1CF",
    "EndTime": "2019-12-30T08:10:00Z",
    "StartTime": "2019-12-30T08:00:00Z",
    "HitRateInterval": {
        "DataModule": [
            {
                "TimeStamp": "2019-12-30T08:00:00Z",
                "Value": "74.82824427480917",
                "HttpsValue": 0
            },
            {
                "TimeStamp": "2019-12-30T08:05:00Z",
                "Value": "62.83283497081019",
                "HttpsValue": 100
            }
        ]
    }
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

