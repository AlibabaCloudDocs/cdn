# DescribeDomainTopUrlVisit

Queries top 100 frequently requested URLs of an accelerated domain name in a specified time range.

**Note:**

-   If you do not set StartTime or EndTime, data within the last 24 hours is queried. If you set both StartTime and EndTime, data within the specified time range is queried.
-   You can query data collected within the last 90 days.
-   You can specify only one accelerated domain name or all accelerated domain names of your Alibaba Cloud account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTopUrlVisit&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainTopUrlVisit|The operation that you want to perform. Set the value to **DescribeDomainTopUrlVisit**. |
|DomainName|String|Yes|example.com|The accelerated domain name for which you want to query data. If you do not set this parameter, frequently requested URLs of all accelerated domain names of your Alibaba Cloud account are queried. |
|StartTime|String|No|2019-10-04T00:00:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

If you want to query data within a specific day, we recommend that you set the value in the yyyy-MM-ddT16:00:00Z format. |
|EndTime|String|No|2019-10-04T16:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

**Note:** The end time must be later than the start time. The difference between the end time and the start time cannot exceed seven days. |
|SortBy|String|No|pv|The method that is used to sort the returned URLs.**** Valid values:

-   **traf**: by network traffic.
-   **pv**: by the number of page views. This is the default value. |

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
|DomainName|String|example.com|The accelerated domain name for which the data was returned. |
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|The ID of the request. |
|StartTime|String|2019-10-03T16:00:00Z|The beginning of the time range that was queried. |
|Url200List|Array of UrlList| |A list of URLs for which 2xx status codes were returned. |
|UrlList| | | |
|Flow|String|460486880|The network traffic consumed by visits to the URL, in bytes. |
|FlowProportion|Float|0.35|The proportion of network traffic consumed to access the URL. |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8|The complete URL. |
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
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8|The complete URL. |
|VisitData|String|1884|The number of visits to the URL. |
|VisitProportion|Float|0.35|The proportion of visits to the URL. |
|Url500List|Array of UrlList| |A list of URLs for which 5xx status codes were returned. |
|UrlList| | | |
|Flow|String|460486880|The network traffic consumed by visits to the URL, in bytes. |
|FlowProportion|Float|0.35|The proportion of network traffic consumed to access the URL. |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8|The complete URL. |
|VisitData|String|161673|The number of visits to the URL. |
|VisitProportion|Float|0.35|The proportion of visits to the URL. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeDomainTopUrlVisit
&DomainName=example.com
&StartTime=2019-10-04T00:00:00Z
&EndTime=2019-10-04T16:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainTopUrlVisitResponse>
  <Url300List>
</Url300List>
  <AllUrlList>
        <UrlList>
              <Flow>9304</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>2</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
        <UrlList>
              <Flow>3986</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
        <UrlList>
              <Flow>784</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
  </AllUrlList>
  <Url400List>
        <UrlList>
              <Flow>3986</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
        <UrlList>
              <Flow>784</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
  </Url400List>
  <RequestId>8E7A2ABF-1BB0-4E46-AE3E-58DB3151080C</RequestId>
  <DomainName>example.com</DomainName>
  <Url200List>
        <UrlList>
              <Flow>9304</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>2</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
  </Url200List>
  <StartTime>2019-10-04T00:00:00Z</StartTime>
  <Url500List>
</Url500List>
</DescribeDomainTopUrlVisitResponse>
```

`JSON` format

```
{
    "Url300List": {
        "UrlList": []
    },
    "AllUrlList": {
        "UrlList": [
            {
                "Flow": 9304,
                "VisitProportion": 0,
                "VisitData": 2,
                "UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
                "FlowProportion": 0
            },
            {
                "Flow": 3986,
                "VisitProportion": 0,
                "VisitData": 1,
                "UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
                "FlowProportion": 0
            },
            {
                "Flow": 784,
                "VisitProportion": 0,
                "VisitData": 1,
                "UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
                "FlowProportion": 0
            }
        ]
    },
    "Url400List": {
        "UrlList": [
            {
                "Flow": 3986,
                "VisitProportion": 0,
                "VisitData": 1,
                "UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
                "FlowProportion": 0
            },
            {
                "Flow": 784,
                "VisitProportion": 0,
                "VisitData": 1,
                "UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
                "FlowProportion": 0
            }
        ]
    },
    "RequestId": "8E7A2ABF-1BB0-4E46-AE3E-58DB3151080C",
    "DomainName": "example.com",
    "Url200List": {
        "UrlList": [
            {
                "Flow": 9304,
                "VisitProportion": 0,
                "VisitData": 2,
                "UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
                "FlowProportion": 0
            }
        ]
    },
    "StartTime": "2019-10-04T00:00:00Z",
    "Url500List": {
        "UrlList": []
    }
}
```

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

