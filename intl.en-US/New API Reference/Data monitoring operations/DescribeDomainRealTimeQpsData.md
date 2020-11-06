# DescribeDomainRealTimeQpsData

Queries the number of queries per second for accelerated domain names. The data is collected at an interval of one minute. You can query data collected within the last seven days.

**When you call this operation, note that:**

-   The time range specified by the StartTime and EndTime parameters cannot exceed 24 hours.
-   If you do not set StartTime or EndTime, data collected within the last one hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 600.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeQpsData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainRealTimeQpsData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeQpsData**. |
|DomainName|String|Yes|test.test.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|IspNameEn|String|No|telecom|The name of the Internet Service Provider \(ISP\). You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query ISPs. If you do not set this parameter, all ISPs are queried. |
|LocationNameEn|String|No|beijing|The name of the region. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query regions. If you do not set this parameter, all regions are queried. |
|StartTime|String|No|2019-12-02T11:25:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-02T11:26:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Data|Array of QpsModel| |The response parameters. |
|QpsModel| | | |
|Qps|Float|1851.25|The number of queries per second. |
|TimeStamp|String|2019-12-02T11:25:00Z|The timestamp. The time follows the ISO 8601 standard in the yyyy-MM-ddThh:mm:ssZ format. The time is displayed in Coordinated Universal Time \(UTC\). |
|RequestId|String|32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeQpsData
&DomainName=example.com
&StartTime=2019-12-02T11:25:00Z
&EndTime=2019-12-02T11:26:00Z
&IspNameEn=telecom
&LocationNameEn=beijing
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainRealTimeQpsDataResponse>
      <Data>
            <QpsModel>
                  <TimeStamp>2019-12-02T11:26:00Z</TimeStamp>
                  <Qps>1851.25</Qps>
            </QpsModel>
            <QpsModel>
                  <TimeStamp>2019-12-02T11:25:00Z</TimeStamp>
                  <Qps>8967.7</Qps>
            </QpsModel>
      </Data>
      <RequestId>32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D</RequestId>
</DescribeDomainRealTimeQpsDataResponse>
```

`JSON` format

```
{
    "Data": {
        "QpsModel": [{
            "TimeStamp": "2019-12-02T11:26:00Z",
            "Qps": 1851.25
        }, {
            "TimeStamp": "2019-12-02T11:25:00Z",
            "Qps": 8967.7
        }]
    },
    "RequestId": "32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidTime.Malformed|Specified StartTime or EndTime is malformed.|The error message returned because the format of the specified start time or end time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

