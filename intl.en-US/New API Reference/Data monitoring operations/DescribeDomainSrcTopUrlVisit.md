# DescribeDomainSrcTopUrlVisit

Queries frequently requested URLs of one or more accelerated domain names.

**Note:** The data is collected at an interval of five minutes.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainSrcTopUrlVisit&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainSrcTopUrlVisit|The operation that you want to perform. Set the value to **DescribeDomainSrcTopUrlVisit**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify multiple accelerated domain names and separate them with commas \(,\). |
|StartTime|String|No|2018-10-03T16:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 **Note:** If you do not set the StartTime parameter, the data within the previous day is queried. |
|EndTime|String|No|2018-10-03T20:00:00Z|The end of the time range to query. The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC.

 **Note:** The end time must be later than the start time. The difference between the end time and the start time cannot exceed seven days. |
|SortBy|String|No|pv|The method that is used to sort the URLs.**** Valid values:

 -   **traf**: by network traffic.
-   **pv**: by the number of page views \(PVs\). This is the default value. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|AllUrlList|Array of UrlList| |A list of frequently requested URLs. |
|UrlList| | | |
|Flow|String|460486880|The network traffic consumed by visits to the URL, in bytes. |
|FlowProportion|Float|0.35|The proportion of network traffic consumed to access the URL. |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|The complete URL. |
|VisitData|String|161673|The number of visits to the URL. |
|VisitProportion|Float|0.35|The proportion of visits to the URL. |
|DomainName|String|example.com|The accelerated domain name. |
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|The ID of the request. |
|StartTime|String|2018-10-03T16:00:00Z|The beginning of the time range that was queried. |
|Url200List|Array of UrlList| |A list of URLs for which 2xx status codes were returned. |
|UrlList| | | |
|Flow|String|460486880|The network traffic consumed by visits to the URL, in bytes. |
|FlowProportion|Float|0.35|The proportion of network traffic consumed to access the URL. |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|The complete URL. |
|VisitData|String|161673|The number of visits to the URL. |
|VisitProportion|Float|0.35|The proportion of visits to the URL. |
|Url300List|Array of UrlList| |A list of URLs for which 3xx status codes were returned. |
|UrlList| | | |
|Flow|String|460486880|The network traffic consumed by visits to the URL, in bytes. |
|FlowProportion|Float|0.35|The proportion of network traffic consumed to access the URL. |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|The complete URL. |
|VisitData|String|161673|The number of visits to the URL. |
|VisitProportion|Float|0.35|The proportion of visits to the URL. |
|Url400List|Array of UrlList| |A list of URLs for which 4xx status codes were returned. |
|UrlList| | | |
|Flow|String|460486880|The network traffic consumed by visits to the URL, in bytes. |
|FlowProportion|Float|0.35|The proportion of network traffic consumed to access the URL. |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|The complete URL. |
|VisitData|String|161673|The number of visits to the URL. |
|VisitProportion|Float|0.35|The proportion of visits to the URL. |
|Url500List|Array of UrlList| |A list of URLs for which 5xx status codes were returned. |
|UrlList| | | |
|Flow|String|460486880|The network traffic consumed to visit the URL, in bytes. |
|FlowProportion|Float|0.35|The proportion of network traffic consumed to access the URL. |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|The complete URL. |
|VisitData|String|161673|The number of visits to the URL. |
|VisitProportion|Float|0.35|The proportion of visits to the URL. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeDomainSrcTopUrlVisit
&DomainName=example.com
&StartTime=2018-10-03T16:00:00Z
&EndTime=2018-10-03T20:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainSrcTopUrlVisitResponse>
  <AllUrlList>
        <UrlList>
              <VisitData>161673</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>37</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/ZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </AllUrlList>
  <Url300List>
        <UrlList>
              <VisitData>161673</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>3</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </Url300List>
  <Url400List>
        <UrlList>
              <VisitData>1884</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUhb,,/HNJSMPP360.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SEEwODgm,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </Url400List>
  <RequestId>64D28B53-5902-409B-94F6-FD46680144FE</RequestId>
  <DomainName>example.com</DomainName>
  <Url200List>
        <UrlList>
              <VisitData>161673</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcG,,/HNJSMPP360.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>3</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KDMlPTIwMTQ,,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </Url200List>
  <StartTime>2018-10-03T16:00:00Z</StartTime>
  <Url500List>
        <UrlList>
              <VisitData>161673</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>3</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </Url500List>
</DescribeDomainSrcTopUrlVisitResponse>
```

`JSON` format

```
{
    "AllUrlList": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "37",
                "UrlDetail": "http://example.com/nn_live/nn_x64/ZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }                      
        ]
    },
    "Url300List": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "3",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    },
    "Url400List": {
        "UrlList": [
            {
                "VisitData": "1884",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUhb,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "1",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SEEwODgm,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }           
        ]
    },
    "RequestId": "64D28B53-5902-409B-94F6-FD46680144FE",
    "DomainName": "example.com",
    "Url200List": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcG,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "3",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KDMlPTIwMTQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    },
    "StartTime": "2018-10-03T16:00:00Z",
    "Url500List": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },           
            {
                "VisitData": "3",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    }
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

