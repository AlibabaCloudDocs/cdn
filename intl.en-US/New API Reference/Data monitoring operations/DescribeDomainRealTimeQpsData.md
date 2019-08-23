# DescribeDomainRealTimeQpsData {#reference1786 .reference}

You can call the DescribeDomainRealTimeQpsData operation to query the number of queries per second with a time granularity of one minute for a specified domain name.

**Note:** 

-   You can query data within the last seven days. The time range specified by StartTime and EndTime parameters cannot exceed 24 hours.
-   If neither the StartTime nor EndTime parameter is set, the data within the last hour is queried.

## Debugging {#section_h17_6zt_pi1 .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainRealTimeQpsData) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_9p5_7xj_9t4 .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeDomainRealTimeQpsData.|
|DomainName|String|Yes|The domain name.|
|StartTime|String|Yes|The beginning of the time range where the data is queried. -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.
-   Example: 2016-10-20T04:00:00Z.
-   If you do not set this parameter, the data within the hour before the EndTime is queried.

 |
|EndTime|String|Yes|The end of the time range where the data is queried. -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.
-   Example: 2016-10-20T04:00:00Z.
-   If you do not set this parameter, the data within the hour after the StartTime is queried.

 |
|IspNameEn|String |Yes|The Internet service provider \(ISP\) of the domain in English. You can call the DescribeCdnRegionAndIsp operation to query the ISP names. If you do not set this parameter, all ISPs are queried.|
|LocationNameEn|String|Yes|The English name of the region. You can call the DescribeCdnRegionAndIsp operation to query the region names. If you do not set this parameter, all regions are queried.|

## Response parameters {#section_a56_6bx_dtg .section}

|Parameter|Type|Description|
|---------|----|-----------|
|RequestId|String|The ID of the request.|
|TimeStamp|String|The timestamp of the data. -   The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC.
-   Example: 2016-10-20T04:00:00Z.

 |
|Qps|Float|The number of queries per second.|

## Examples {#section_vtj_n5h_qvw .section}

Sample request

``` {#codeblock_vin_73w_txx}
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeQpsData&DomainName=example.com&EndTime=2018-01-02T11%3A05%3A37Z&IspNameEn=telecom&LocationNameEn=beijing<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_4jo_say_bp1 .language-json}
{
   "Data":{
      "QpsModel":[
         {
            "TimeStamp":"2018-01-02T11:26:00Z",
            "Qps":1851.25
         },
         {
            "TimeStamp":"2018-01-02T11:25:00Z",
            "Qps":8967.7
         }
      ]
   },
   "RequestId":"32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D"
}
			
```

## Error codes {#section_6en_8gg_hme .section}

|Error code|Error message|HTTP status code|Description|
|----------|-------------|----------------|-----------|
|InvalidTime.Malformed|Specified StartTime or EndTime is malformed.|400|The error message returned because the format of the time parameters is invalid.|
|InvalidDomainName.Malformed|Specified DomainName is malformed.|400|The error message returned because no domain name is specified or the specified domain name does not exist.|

