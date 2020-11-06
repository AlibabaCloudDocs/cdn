# DescribeDomainPathData

Queries the traffic and visits metrics collected at an interval of five minutes for one or all directories of an accelerated domain name.

Limits:

-   This operation is available to only selected users.
-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data within the specified time range is queired.
-   You can specify only one domain name in each query.
-   You can query data collected within the last 90 days.
-   The paths must be specific. Fuzzy match is not supported.
-   The maximum number of times that each user can call this operation per second is 6,000.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainPathData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainPathData|The operation that you want to perform. Set the value to **DescribeDomainPathData**. |
|DomainName|String|Yes|test.test.com|The accelerated domain name. |
|PageNumber|Integer|No|1|The number of the page to return. Pages start from page **1**. |
|PageSize|Integer|No|20|The number of entries to return on each page. Maximum value: **1000**. |
|Path|String|No|/path/|The paths that you want to query. Separate multiple paths with forward slashes \(/\). If you do not set this parameter, all paths are queried. If you set the value to a directory, it must end with a forward slash \(/\). |
|StartTime|String|No|2016-10-20T04:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. Example: 2016-10-20T04:00:00Z. |
|EndTime|String|No|2016-10-20T04:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. The end time must be later than the start time. The maximum time range that can be specified is 30 days. Example: 2016-10-20T04:00:00Z. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The time interval between the data entries. Unit: seconds. |
|DomainName|String|test.test.com|The accelerated domain name. |
|EndTime|String|2017-09-30T17:00:00Z|The end of the time range that was queried. |
|PageNumber|Integer|1|The page number of the returned page. Pages start from page **1**. |
|PageSize|Integer|20|The number of entries returned per page. |
|PathDataPerInterval|Array of UsageData| |A list of bandwidth values collected at each time interval. |
|UsageData| | | |
|Acc|Integer|10|The number of visits to the path. |
|Path|String|/path/|The file path. |
|Time|String|2017-09-30T16:00:00Z|The time when the data was collected. |
|Traffic|Integer|346|The amount of traffic consumed for visiting the path. |
|StartTime|String|2017-09-30T17:00:00Z|The beginning of the time range that was queried. |
|TotalCount|Integer|2|The total number of entries returned. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?Action=DescribeDomainPathData&DomainName=<DomainName>&PageNumber=1&PageSize=20
```

Sample success responses

`XML` format

```
<DescribeDomainPathDataResponse>
  <DataInterval>300</DataInterval>
  <EndTime>2017-09-30T17:00:00Z</EndTime>
  <PageNumber>1</PageNumber>
  <PageSize>20</PageSize>
  <PathDataPerInterval>
        <UsageData>
              <Acc>10</Acc>
              <Path>/path/</Path>
              <Time>2017-09-30T16:00:00Z</Time>
              <Traffic>346</Traffic>
        </UsageData>
        <UsageData>
              <Acc>12</Acc>
              <Path>/path/</Path>
              <Time>2017-09-30T16:05:00Z</Time>
              <Traffic>400</Traffic>
        </UsageData>
  </PathDataPerInterval>
  <StartTime>2017-09-30T16:00:00Z</StartTime>
  <TotalCount>2</TotalCount>
</DescribeDomainPathDataResponse>
```

`JSON` format

```
{
    "DataInterval": 300,
    "EndTime": "2017-09-30T17:00:00Z",
    "PageNumber": 1,
    "PageSize": 20,
    "PathDataPerInterval": {
        "UsageData": [
            {
                "Acc": 10,
                "Path": "/path/",
                "Time": "2017-09-30T16:00:00Z",
                "Traffic": 346
            },
            {
                "Acc": 12,
                "Path": "/path/",
                "Time": "2017-09-30T16:05:00Z",
                "Traffic": 400
            }
        ]
    },
    "StartTime": "2017-09-30T16:00:00Z",
    "TotalCount": 2
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

