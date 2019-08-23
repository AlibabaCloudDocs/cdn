# DescribeTopDomainsByFlow {#reference3734 .reference}

You can call the DescribeTopDomainsByFlow operation to query the CDN domain names ranked by network traffic.

-   If you do not specify the StartTime or EndTime parameters, the data within the last 24 hours is queried.
-   If you specify both the StartTime and EndTime parameters, the data within the specified time range is queried.

**Note:** You can query the data of up to the last 90 days.

## Debugging {#section_wf9_nst_gwa .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeTopDomainsByFlow) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_7vd_871_ike .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeTopDomainsByFlow.|
|StartTime|String|No|The beginning of the time range where the data is queried. -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.
-   The minimum data sampling interval is 5 minutes. If you do not specify this parameter, the data within the last month is queried.

 |
|EndTime|String|No| -   The end of the time range where the data is queried. The end time must be later than the start time.
-   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.

 |
|Limit|String|No|The maximum number of domain names to return. Valid values: 1 to 100. Default value: 20.|

## Response parameters {#section_6n6_9qe_78c .section}

|Parameter|Type|Description|
|---------|----|-----------|
|RequestId|String|The ID of the request.|
|StartTime|String|The beginning of the time range where the data was queried.|
|EndTime|String|The end of the time range where the data was queried.|
|TopDomains|TopDomain\[\]|The CDN domain names returned.|
|DomainCount|Long|The total number of CDN domain names under your account.|
|DomainOnlineCount|Long|The total number of CDN domains that are in the Enabled state under your account.|

Parameters in TopDomain

|Parameter|Type|Description|
|---------|----|-----------|
|DomainName|String|The name of the CDN domain.|
|Rank|Long|The ranking of the CDN domain.|
|TotalTraffic|Double|The total network traffic.|
|TrafficPercent|Double|The proportion of the network traffic.|
|MaxBps|Long|The peak bandwidth.|
|MaxBpsTime|Long|The time when the bandwidth peaked.|
|TotalAccess|Long|The number of visits.|

## Examples {#section_hjq_zt1_bn6 .section}

Sample request

``` {#codeblock_60a_392_own}
http://cdn.aliyuncs.com?Action=DescribeTopDomainsByFlow
&StartTime=2016-03-01T04:00:00Z
&EndTime=2016-03-14T07:34:00Z
&Limit=5
&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_y2c_1bq_i5e .language-json}
{
  "DomainCount": 68,
  "DomainOnlineCount": 68,
  "RequestId": "4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70",
  "EndTime": "2016-03-14T07:34:00Z",
  "TopDomains": {
    "TopDomain": [
      {
        "MaxBps": 22139626,
        "Rank": 1,
        "TrafficPercent": 30.64191989360235,
        "TotalTraffic": 2043859876683.9001,
        "TotalAccess": 107784230,
        "DomainName": "example1.com",
        "MaxBpsTime": 1457111400
      },
      {
        "MaxBps": 1008772351,
        "Rank": 2,
        "TrafficPercent": 25.936032624725815,
        "TotalTraffic": 1729970466149.2002,
        "TotalAccess": 3843128,
        "DomainName": "example2.com",
        "MaxBpsTime": 1457505600
      },
      {
        "MaxBps": 16046911,
        "Rank": 3,
        "TrafficPercent": 21.686305274906182,
        "TotalTraffic": 1446507574551.6,
        "TotalAccess": 547567,
        "DomainName": "example3.com",
        "MaxBpsTime": 1456897200
      },
      {
        "MaxBps": 15990893,
        "Rank": 4,
        "TrafficPercent": 21.261081185428147,
        "TotalTraffic": 1418144519687.5,
        "TotalAccess": 548380,
        "DomainName": "example4.com",
        "MaxBpsTime": 1457567700
      },
      {
        "MaxBps": 473599,
        "Rank": 5,
        "TrafficPercent": 0.4308743788055894,
        "TotalTraffic": 28739937242.500004,
        "TotalAccess": 152150,
        "DomainName": "example5.cn",
        "MaxBpsTime": 1457845800
      }
    ]
  },
  "StartTime": "2016-03-01T04:00:00Z"
}
```

## Error codes {#section_i3a_d2d_bjn .section}

|Error code|Error message|HTTP status code|Description|
|----------|-------------|----------------|-----------|
|InvalidStartTime.Malformed|Specified StartTime is malformed.|400|The error message returned because the specified StartTime parameter is invalid.|
|InvalidEndTime.Malformed|Specified EndTime is malformed.|400|The error message returned because the specified EndTime parameter is invalid.|
|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|400|The error message returned because the time range specified by the EndTime and StartTime parameters exceeds the maximum value of 90 days.|
|InvalidDomain.NotFound|The domain provided does not exist in our records.|404|The error message returned because the specified domain does not exist or does not belong to you.|
|InvalidEndTime.Mismatch|Specified EndTime does not math the specified StartTime.|400|The error message returned because the specified EndTime parameter is earlier than the specified StartTime parameter.|

