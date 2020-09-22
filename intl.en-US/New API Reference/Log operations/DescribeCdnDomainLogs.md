# DescribeCdnDomainLogs

Queries the address where you can download the raw access log data of a specific domain name.

**When you call this operation, note that:**

-   If you do not specify the StartTime or EndTime parameter, data collected within the last 24 hours is queried. If you specify both the StartTime and EndTime parameters, data collected within the specified time range is queried.
-   You can download log data that was collected within the last one month.
-   The log data was collected at an interval of one hour.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainLogs&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeCdnDomainLogs|The operation that you want to perform. Set the value to **DescribeCdnDomainLogs**. |
|DomainName|String|Yes|www.yourdomain.com|The accelerated domain name. You can specify only one domain name. |
|PageSize|Long|No|300|The number of entries to return on each page. Valid values: **1** to **1000**. Maximum value: **1000**. Default value: **300**. |
|PageNumber|Long|No|2|The number of the page to return. Valid values: integers larger than **1**. |
|StartTime|String|No|2017-12-21T08:00:00Z|The beginning of the time range to query.

 Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2017-12-22T08:00:00Z|The end of the time range to query. The end time must be later than the start time. The time period between the start time and end time cannot exceed one year.

 Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainLogDetails|Array| |The detailed log information, which is indicated by the DomainLogDetail parameter. Data type: array. |
|DomainLogDetail| | | |
|DomainName|String|example.com|The accelerated domain name. |
|LogCount|Long|10|The total number of entries returned on the current page. |
|LogInfos|Array| |The detailed log information, which is indicated by the LogInfoDetail parameter. Data type: array. |
|LogInfoDetail| | | |
|EndTime|String|2015-05-23T14:00:00Z|The end of the time range that was queried. |
|LogName|String|gc.ggter.com\_2015\_05\_23\_2100\_2200.gz|The name of the log file. |
|LogPath|String|cdnlog.cn-hangzhou.xxx|The path of the log file. |
|LogSize|Long|258|The size of the log file. |
|StartTime|String|2015-05-23T13:00:00Z|The beginning of the time range that was queried. |
|PageInfos|Array| |The detailed log information, which is indicated by the PageInfoDetail parameter. Data type: array. |
|PageInfoDetail| | | |
|PageIndex|Long|1|The page number of the returned page. |
|PageSize|Long|1|The number of entries returned per page. |
|Total|Long|3|The total number of entries returned. |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?Action=DescribeCdnDomainLogs
&DomainName=www.yourdomain.com
&StartTime=2017-12-21T08:00:00Z
&EndTime=2017-12-22T08:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DomainLogModel>
    <DomainName>example.com</DomainName>
    <PageNumber>1</PageNumber>
    <TotalCount>3</TotalCount>
    <PageSize>100</PageSize>
    <DomainLogDetails>
        <DomainLogDetail>
            <EndTime>2015-05-23T04:00:00Z</EndTime>
            <LogName>gc.ggter.com_2015_05_23_1100_1200.gz</LogName>
            <LogPath>test.cn-hangzhou.oss.aliyun-inc.com/gc.xxx.com/2015_05_23/gc.ggter.com_2015_05_23_1100_1200.gz? OSSAccessKeyId=3xmgf7JheOfOxxxx&amp;Expires=1432539994&amp;Signature=7Ly4ccKN3afzAGYyWDbxBcOcnxxxx</LogPath>
            <LogSize>257</LogSize>
            <StartTime>2015-05-23T03:00:00Z</StartTime>
        </DomainLogDetail>
        <DomainLogDetail>
            <EndTime>2015-05-23T08:00:00Z</EndTime>
            <LogName>gc.ggter.com_2015_05_23_1500_1600.gz</LogName>
            <LogPath>test.cn-hangzhou.oss.aliyun-inc.com/gc.xxx.com/2015_05_23/gc.ggter.com_2015_05_23_1500_1600.gz? OSSAccessKeyId=3xmgf7JheOfOxxxx&amp;Expires=1432539994&amp;Signature=dMv7VqPqZHXVbKPmorGIvylC6xxxx</LogPath>
            <LogSize>194</LogSize>
            <StartTime>2015-05-23T07:00:00Z</StartTime>
        </DomainLogDetail>
        <DomainLogDetail>
            <EndTime>2015-05-23T14:00:00Z</EndTime>
            <LogName>gc.ggter.com_2015_05_23_2100_2200.gz</LogName>
            <LogPath>test.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015_05_23/gc.ggter.com_2015_05_23_2100_2200.gz? OSSAccessKeyId=3xmgf7JheOfOxxxx&amp;Expires=1432539994&amp;Signature=FpSQCbgNcxCBYIxKVoKC8mGxxxx</LogPath>
            <LogSize>258</LogSize>
            <StartTime>2015-05-23T13:00:00Z</StartTime>
        </DomainLogDetail>
    </DomainLogDetails>
</DomainLogModel>
<RequestId>1805F349-0A2B-41D9-B4AD-33632AFC27F1</RequestId>
```

`JSON` format

```
{
    "DomainLogModel": {
        "DomainName": "example.com",
        "PageNumber": 1,
        "TotalCount": 3,
        "PageSize": 100,
        "DomainLogDetails": {
            "DomainLogDetail": [
                {
                    "EndTime": "2015-05-23T04:00:00Z",
                    "LogName": "gc.ggter.com_2015_05_23_1100_1200.gz",
                    "LogPath": "test.cn-hangzhou.oss.aliyun-inc.com/gc.xxx.com/2015_05_23/gc.ggter.com_2015_05_23_1100_1200.gz? OSSAccessKeyId=3xmgf7JheOfOxxxx&Expires=1432539994&Signature=7Ly4ccKN3afzAGYyWDbxBcOcnxxxx",
                    "LogSize": 257,
                    "StartTime": "2015-05-23T03:00:00Z"
                },
                {
                    "EndTime": "2015-05-23T08:00:00Z",
                    "LogName": "gc.ggter.com_2015_05_23_1500_1600.gz",
                    "LogPath": "test.cn-hangzhou.oss.aliyun-inc.com/gc.xxx.com/2015_05_23/gc.ggter.com_2015_05_23_1500_1600.gz? OSSAccessKeyId=3xmgf7JheOfOxxxx&Expires=1432539994&Signature=dMv7VqPqZHXVbKPmorGIvylC6xxxx",
                    "LogSize": 194,
                    "StartTime": "2015-05-23T07:00:00Z"
                },
                {
                    "EndTime": "2015-05-23T14:00:00Z",
                    "LogName": "gc.ggter.com_2015_05_23_2100_2200.gz",
                    "LogPath": "test.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015_05_23/gc.ggter.com_2015_05_23_2100_2200.gz? OSSAccessKeyId=3xmgf7JheOfOxxxx&Expires=1432539994&Signature=FpSQCbgNcxCBYIxKVoKC8mGxxxx",
                    "LogSize": 258,
                    "StartTime": "2015-05-23T13:00:00Z"
                }
            ]
        }
    },
    "RequestId": "1805F349-0A2B-41D9-B4AD-33632AFC27F1"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

