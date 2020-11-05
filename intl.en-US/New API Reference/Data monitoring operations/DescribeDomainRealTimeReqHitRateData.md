# DescribeDomainRealTimeReqHitRateData

Queries the request hit ratios of accelerated domain names. The data is collected at an interval of one minute. You can only query the data collected within the last seven days.

**When you call this operation, note that:**

-   The time range specified by the StartTime and EndTime parameters cannot exceed 24 hours.
-   If you do not set StartTime or EndTime, data collected within the last one hour is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   The network traffic destined for different domain names may be redirected to the same origin. Therefore, the byte hit ratios may be inaccurate. The accuracy of query results is based on the actual configurations.
-   The maximum number of times that each user can call this operation per second is 10.

**Note:** By default, requests in the Go programming language use the POST request method. You must manually change the request method to GET by declaring: request.Method="GET".

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeReqHitRateData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainRealTimeReqHitRateData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeReqHitRateData**. |
|DomainName|String|Yes|test.test.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|StartTime|String|No|2018-01-02T11:23:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2018-01-02T11:26:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Data|Array of ReqHitRateDataModel| |The response parameters. |
|ReqHitRateDataModel| | | |
|ReqHitRate|Float|0.8956940476262277|The request hit ratio. |
|TimeStamp|String|2018-01-02T11:26:00Z|The timestamp. The time follows the ISO 8601 standard in the yyyy-MM-ddThh:mm:ssZ format. The time is displayed in UTC. |
|RequestId|String|70A26B11-3673-479C-AEA8-E03FC5D3496D|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeReqHitRateData
&DomainName=www.domainname.com
&StartTime=2018-01-02T11:23:00Z
&EndTime=2018-01-02T11:26:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainRealTimeReqHitRateDataResponse>
      <Data>
            <ReqHitRateDataModel>
                  <TimeStamp>2018-01-02T11:26:00Z</TimeStamp>
                  <ReqHitRate>0.8956940476262277</ReqHitRate>
            </ReqHitRateDataModel>
            <ReqHitRateDataModel>
                  <TimeStamp>2018-01-02T11:25:00Z</TimeStamp>
                  <ReqHitRate>0.8429129920796812</ReqHitRate>
            </ReqHitRateDataModel>
      </Data>
      <RequestId>70A26B11-3673-479C-AEA8-E03FC5D3496D</RequestId>
</DescribeDomainRealTimeReqHitRateDataResponse>
```

`JSON` format

```
{
    "Data": {
        "ReqHitRateDataModel": [{
            "TimeStamp": "2018-01-02T11:26:00Z",
            "ReqHitRate": 0.8956940476262277
        }, {
            "TimeStamp": "2018-01-02T11:25:00Z",
            "ReqHitRate": 0.8429129920796812
        }]
    },
    "RequestId": "70A26B11-3673-479C-AEA8-E03FC5D3496D"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidTime.Malformed|Specified StartTime or EndTime is malformed.|The error message returned because the format of the specified start time or end time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

