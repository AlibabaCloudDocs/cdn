# DescribeCdnDomainLogs {#reference3345 .reference}

You can call the DescribeCdnDomainLogs operation to query the raw access log information for a specific CDN domain, including log path.

-   If you do not specify the StartTime or EndTime parameters, the log data within the last 24 hours is queried.
-   If you specify both the StartTime and EndTime parameters, the log data within the specified time range is queried.

**Note:** Log data can be retained for a maximum of one year.

## Debugging {#section_vjf_owz_5xn .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnDomainLogs) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_30m_b02_2vn .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeCdnDomainLogs.|
|DomainName|String|Yes|The name of the CDN domain to query log data for. You can specify only one domain name.|
|StartTime|String|No| The beginning of the time range where the log data is queried.

 -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.

 |
|EndTime|String|No| The end of the time range where the log data is queried. The end time must be later than the start time.

 -   The maximum time range that can be queried is one year.
-   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.

 |
|PageSize|Long|No| The maximum number of entries to return on each page. Valid values: 1 to 1000.

 -   Default value: 300.
-   Maximum value: 1000.

 |
|PageNumber|Long|No|The number of the page to return. Pages start from page 1.|

## Response parameters {#section_a7q_lno_237 .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|DomainLogDetails|DomainLogDetail|The detailed log information.|
|RequestID|String|The ID of the request.|

Parameters in DomainLogDetail

|Parameter|Type|Description|
|:--------|:---|:----------|
|LogCount|Long|The total number of entries returned on this page.|
|DomainName|String|The domain name.|
|PageInfos|PageInfoDetail|The detailed page information.|
|LogInfos|LogInfoDetail|The detailed log information.|

Parameters in PageInfoDetail

|Parameter|Type|Description|
|:--------|:---|:----------|
|PageIndex|Long|The number of the page returned.|
|PageSize|Long|The maximum number of entries that can be returned on each page.|
|Total|Long|The total number of entries returned.|

Parameters in LogInfoDetail

|Parameter|Type|Description|
|:--------|:---|:----------|
|LogName|String |The name of the log.|
|LogPath|String|The path of the log to download.|
|StartTime|String|The beginning of the time range where the log data was queried.|
|End time.|String|The end of the time range where the log data was queried.|
|LogSize|Long|The size of the log.|

## Examples {#section_5jq_67n_9xh .section}

Sample request

``` {#codeblock_2qf_jfp_98b}
https://cdn.aliyuncs.com?Action=DescribeCdnDomainLogs&DomainName=test1.example.com&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_1wo_yk3_5jz}
{
    "RequestId": "077D0284-F041-4A41-A932-B48377FDAA25",
    "DomainLogDetails": {
        "DomainLogDetail": [
            {
                "LogInfos": {
                    "LogInfoDetail": [
                        {
                            "LogName": "example1.com_2018_03_25_180000_190000.gz",
                            "LogPath": "cdnlog2.aliyuncs.com/test1.example.com/2018_03_25/example1.com_2018_03_25_180000_190000.gz? xxx",
                            "EndTime": "2018-05-31T04:00:00Z",
                            "StartTime": "2018-05-31T03:00:00Z",
                            "LogSize": 2645401
                        },
                        {
                            "LogName": "example1.com_2018_03_25_190000_200000.gz",
                            "LogPath": "cdnlog2.aliyuncs.com/test1.example.com/2018_03_25/example1.com_2018_03_25_190000_200000.gz? xxx",
                            "EndTime": "2018-05-31T06:00:00Z",
                            "StartTime": "2018-05-31T05:00:00Z",
                            "LogSize": 2653965
                        }
                    ]
                },
                "LogCount": 20,
                "PageInfos": {
                    "PageIndex": 1,
                    "PageSize": 20,
                    "Total": 20
                },
                "DomainName": "test1.example.com"
            }
        ]
    }
}
```

