# DescribeDomainISPData {#reference4167 .reference}

You can call the DescribeDomainISPData operation to query the proportions of Internet service providers \(ISPs\) with a time granularity of one day.

-   If you do not set the StartTime and EndTime parameters, the data within the last 24 hours is queried.
-   If you set both the StartTime and EndTime parameters, the data within the specified time range is queried.

**Note:** 

-   You can specify only one domain name. If you do not specify a domain name, all domain names under your account are queried.
-   The maximum time range that you can specify is the last 90 days.

## Debugging {#section_bk2_sdh_iqa .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainISPData) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_dnw_t42_tzn .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to DescribeDomainISPData.|
|DomainName|String|No|The domain name that you want to query. You can specify only one domain name. If you do not specify a domain name, all domain names under your account are queried.|
|StartTime|String|No| -   The beginning of the time range where the data is queried.
-   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.
-   If you do not set this parameter, the data within the last 24 hours is queried.

 |
|EndTime|String|No| -   The end of the time range where the data is queried. The end time must be later than the start time.
-   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 |

## Response parameters {#section_cky_xl8_fb8 .section}

|Parameter|Type|Description|
|---------|----|-----------|
|DomainName|String|The domain name information.|
|DataInterval|String|The data sampling interval, which is set to one day.|
|StartTime|DateTime|The beginning of the time range where the data was queried.|
|EndTime|DateTime|The end of the time range where the data was queried.|
|ISPDataInterval|UsageData\[\]|The proportions of ISPs retrieved at each data sampling interval.|

UsageData

|Parameter|Type|Description|
|---------|----|-----------|
|Value|ISPProportionData\[\]|The list of proportions of ISPs.|

ISPProportionData

|Parameter|Type|Description|
|---------|----|-----------|
|ISP|String|The ISP information.|
|Proportion|String|The proportion of the ISP.|
|IspEname|String|The English name of the ISP.|
|AvgObjectSize|String|The average size of responses. Unit: bytes.|
|AvgResponseTime|String|The average response time. Unit: seconds.|
|Bps|String|The bandwidth.|
|ByteHitRate|String|The byte hit rate.|
|Qps|String|The number of queries per second.|
|ReqErrRate|String|The request error rate.|
|ReqHitRate|String|The request hit rate.|
|AvgResponseRate|String|The average response rate. Unit: byte/ms.|
|TotalBytes|String|The total network traffic.|
|BytesProportion|String|The proportion of the network traffic.|
|TotalQuery|String|The total number of requests.|

## Examples {#section_wgl_8es_kas .section}

Sample request

``` {#codeblock_z4l_30t_6sw}
http://cdn.aliyuncs.com?Action=DescribeDomainISPData
&DomainName=example.com
&StartTime=2015-12-05T00:00:00Z
&EndTime=2015-12-07T00:00:00Z
&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_ld0_b4p_6ov .language-json}
{
  "Value": {
    "ISPProportionData": [
      {
        "ByteHitRate": "100.0",
        "TotalQuery": "1",
        "Bps": "1311.4601296296296",
        "Proportion": "0.004509176173513099",
        "AvgResponseRate": "88.92594866772144",
        "IspEname": "alibaba",
        "AvgObjectSize": "7081884.7",
        "ISP": "Alibaba",
        "ReqErrRate": "0.0",
        "Qps": "2.3148148148148147E-5",
        "AvgResponseTime": "79638.0",
        "ReqHitRate": "100.0",
        "TotalBytes": "7081884",
        "BytesProportion": "0.012220518530445479"
      },
      {
        "ByteHitRate": "100.0",
        "TotalQuery": "3",
        "Bps": "444.455",
        "Proportion": "0.013527528520539298",
        "AvgResponseRate": "154.3345765545624",
        "IspEname": "overseas",
        "AvgObjectSize": "800019.0",
        "ISP": "Overseas ISP",
        "ReqErrRate": "0.0",
        "Qps": "6.944444444444444E-5",
        "AvgResponseTime": "5183.666666666667",
        "ReqHitRate": "100.0",
        "TotalBytes": "2400057",
        "BytesProportion": "0.004141544558417533"
      },
      {
        "ByteHitRate": "100.0",
        "TotalQuery": "82",
        "Bps": "45838.64816666667",
        "Proportion": "0.3697524462280741",
        "AvgResponseRate": "1025.5028528460102",
        "IspEname": "drpeng",
        "AvgObjectSize": "3018642.684146342",
        "ISP": "Dr. Peng",
        "ReqErrRate": "0.0",
        "Qps": "0.0018981481481481482",
        "AvgResponseTime": "2943.5731707317073",
        "ReqHitRate": "100.0",
        "TotalBytes": "247528700",
        "BytesProportion": "0.42713616424581613"
      },
      {
        "ByteHitRate": "99.99999999999999",
        "TotalQuery": "114",
        "Bps": "65933.51396296297",
        "Proportion": "0.5140460837804933",
        "AvgResponseRate": "484.6396117340071",
        "IspEname": "cernet",
        "AvgObjectSize": "3123166.4508771934",
        "ISP": "Education network",
        "ReqErrRate": "0.0",
        "Qps": "0.002638888888888889",
        "AvgResponseTime": "6444.30701754386",
        "ReqHitRate": "100.0",
        "TotalBytes": "356040975",
        "BytesProportion": "0.6143852267848392"
      },
      {
        "ByteHitRate": "100.0",
        "TotalQuery": "207",
        "Bps": "81128.73735185186",
        "Proportion": "0.9333994679172115",
        "AvgResponseRate": "752.2096624205244",
        "IspEname": "tietong",
        "AvgObjectSize": "2116401.843961353",
        "ISP": "Railcom",
        "ReqErrRate": "0.0",
        "Qps": "0.004791666666666666",
        "AvgResponseTime": "2813.5797101449275",
        "ReqHitRate": "100.0",
        "TotalBytes": "438095181",
        "BytesProportion": "0.7559781771177001"
      },
      {
        "ByteHitRate": "100.00000000000001",
        "TotalQuery": "256",
        "Bps": "129137.37100000001",
        "Proportion": "1.1543491004193533",
        "AvgResponseRate": "321.5924922592767",
        "IspEname": "other",
        "AvgObjectSize": "2723991.4195312504",
        "ISP": "other",
        "ReqErrRate": "0.0",
        "Qps": "0.005925925925925926",
        "AvgResponseTime": "8470.3203125",
        "ReqHitRate": "100.0",
        "TotalBytes": "697341803",
        "BytesProportion": "1.2033348171432345"
      },
      {
        "ByteHitRate": "99.14745652563326",
        "TotalQuery": "2866",
        "Bps": "879955.1972037038",
        "Proportion": "12.923298913288543",
        "AvgResponseRate": "1004.5513789924338",
        "IspEname": "mobile",
        "AvgObjectSize": "1657975.598360084",
        "ISP": "mobile",
        "ReqErrRate": "0.0",
        "Qps": "0.06634259259259259",
        "AvgResponseTime": "1650.463712491277",
        "ReqHitRate": "97.3831123517097",
        "TotalBytes": "4751758064",
        "BytesProportion": "8.19964599032574"
      },
      {
        "ByteHitRate": "99.99981717005271",
        "TotalQuery": "6534",
        "Bps": "3194660.60262963",
        "Proportion": "29.46295711773459",
        "AvgResponseRate": "1171.525957981939",
        "IspEname": "unicom",
        "AvgObjectSize": "2640215.374074074",
        "ISP": "unicom",
        "ReqErrRate": "0.0",
        "Qps": "0.15125",
        "AvgResponseTime": "2253.6550352004897",
        "ReqHitRate": "99.96939087848179",
        "TotalBytes": "17251167254",
        "BytesProportion": "29.768658772680293"
      },
      {
        "ByteHitRate": "99.99968869093071",
        "TotalQuery": "12114",
        "Bps": "6333214.260796296",
        "Proportion": "54.62416016593768",
        "AvgResponseRate": "984.184264638081",
        "IspEname": "telecom",
        "AvgObjectSize": "2823126.71357933",
        "ISP": "telecommunications",
        "ReqErrRate": "0.0",
        "Qps": "0.28041666666666665",
        "AvgResponseTime": "2868.494056463596",
        "ReqHitRate": "99.97523526498266",
        "TotalBytes": "34199357008",
        "BytesProportion": "59.01449878861353"
      }
    ]
  },
  "DataInterval": "86400",
  "RequestId": "DE81639B-DAC1-4C76-AB72-F34B836837D5",
  "DomainName": "example1.com",
  "EndTime": "2016-03-14T00:00:00Z",
  "StartTime": "2016-03-13T00:00:00Z"
}            
```

## Error codes {#section_il3_dwb_5ir .section}

|Error code|Error message|HTTP status code|Description|
|----------|-------------|----------------|-----------|
|Throttling|Request was denied due to request throttling.|503|The error message returned because the request is denied due to network traffic throttling.|
|IllegalOperation|Illegal domain, operation is not permitted.|403|The error message returned because the domain name is invalid.|
|OperationDenied|Your account does not open CDN service yet.|403|The error message returned because the CDN service is not activated.|
|OperationDenied|Your CDN service is suspended.|403|The error message returned because the CDN service is suspended.|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|The error message returned because the domain name does not exist or does not belong to you.|
|InvalidDomain.Offline|The domain provided is offline.|404|The error message returned because the domain name is disabled.|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|The error message returned because the domain name is being configured. Please try again later.|
|InvalidDomain.Configure\_failed|Failed to configure the provided domain.|500|The error message returned because the domain name configuration fails.|
|MissingParameter|StartTime and EndTime can not be single.|400|The error message returned because you must set both the StartTime and EndTime parameters.|
|InvalidStartTime.Malformed|Specified start time is malformed.|400|The error message returned because the format of the StartTime parameter is invalid.|
|InvalidEndTime.Malformed|Specified end time is malformed.|400|The error message returned because the format of the EndTime parameter is invalid.|
|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|400|The error message returned because the EndTime is earlier than the StartTime.|
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|The error message returned because the time range specified by the StartTime and EndTime parameters exceeds 90 days.|

