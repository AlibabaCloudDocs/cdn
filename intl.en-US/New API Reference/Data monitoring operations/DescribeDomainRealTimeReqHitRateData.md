# DescribeDomainRealTimeReqHitRateData {#reference1612 .reference}

You can call the DescribeDomainRealTimeReqHitRateData operation to query the request hit rate with a time granularity of one minute.

**Note:** 

-   You can query the data within the last seven days. The time range specified by the StartTime and EndTime parameters cannot exceed 24 hours.
-   If neither the StartTime nor EndTime parameter is set, the data within the last hour is queried.
-   The network traffic destined for different domain names may be redirected to the same origin. Therefore, the obtained request hit rates may be inaccurate. The accuracy of query results depends on the actual configurations.

## Debugging {#section_jcp_2qe_dyh .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainRealTimeReqHitRateData) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_0as_nfw_ec6 .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeDomainRealTimeReqHitRateData.|
|DomainName|String|Yes|The domain name.|
|StartTime|String|Yes|The beginning of the time range where the data is queried. -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.
-   Example: 2016-10-20T04:00:00Z.

 |
|EndTime|String|Yes|The end of the time range where the data is queried. The end time must be later than the start time. -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.
-   Example: 2016-10-20T04:00:00Z.

 |

## Response parameters {#section_znz_pgg_aev .section}

|Parameter|Type|Description|
|---------|----|-----------|
|RequestId|String|The ID of the request.|
|TimeStamp|String|The time stamp of data. -   The time follows the ISO 8601 standard in the yyyy-MM-ddThh:mmZ format. The time is displayed in UTC.
-   Example: 2016-10-20T04:00:00Z.

 |
|ReqHitRate|Float|The request hit rate.|

## Examples {#section_2fu_d9u_671 .section}

Sample request

``` {#codeblock_m9p_v9t_yli}
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeReqHitRateData&DomainName=example.com&EndTime=2018-01-02T11%3A05%3A37Z<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_xrf_vh6_9vn .language-json}
{
   "Data":{
      "ReqHitRateModel":[
         {
            "TimeStamp":"2018-01-02T11:26:00Z",
            "ReqHitRate":0.8956940476262277
         },
         {
            "TimeStamp":"2018-01-02T11:25:00Z",
            "ReqHitRate":0.8429129920796812
         }
      ]
   },
   "RequestId":"70A26B11-3673-479C-AEA8-E03FC5D3496D"
}
```

## Error codes {#section_wfm_ior_p0r .section}

|Error code|Error message|HTTP status code|Description|
|----------|-------------|----------------|-----------|
|InvalidTime.Malformed|Specified time is malformed.|400|The error message returned because the time parameters are invalid.|
|InvalidDomainName.Malformed|Specified DomainName is malformed.|400|The error message returned because the domain name is not specified or the specified domain name does not exist.|

