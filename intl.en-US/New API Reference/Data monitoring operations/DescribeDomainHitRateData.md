# DescribeDomainHitRateData {#reference3739 .reference}

You can call the DescribeDomainHitRateData to query the byte hit rate. The byte hit rate is measured in percentage.

-   If neither the StartTime nor EndTime parameter is set, the data within the last 24 hours is queried.
-   If you set both the StartTime and EndTime parameters, the data within the specified time range is queried.

**Note:** 

-   You can specify one or more domain names. Separate these domain name with commas \(,\).
-   The maximum time range that you can specify is the last 90 days.

## Debugging {#section_a3l_tb1_t9n .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainHitRateData) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_ofp_zu1_gd5 .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeDomainHitRateData.|
|DomainName|String|No|The domain names that you want to query. Separate multiple domain names with commas \(,\).|
|StartTime|String|No|The beginning of the time range where the data is queried. -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.
-   The minimum time granularity is five minutes. If you do not set this parameter, the data within the last 24 hours is queried.

 |
|Interval|String|No| -   The time granularity for query. Unit: seconds. Valid values:
-   Less than 3 days: 300 \(default\), 3600, and 86400
-   3 to 31 days \(excluding 31 days\): 3600 \(default\) and 86400
-   No less than 31 days: 86400
-   If you do not set this parameter or the specified value is invalid, the default value is used.

 |
|EndTime|String|No|The end of the time range where the data is queried. -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.
-   The minimum time granularity is five minutes.

 |

## Response parameters {#section_v3s_u50_cwr .section}

|Parameter|Type|Description|
|---------|----|-----------|
|DomainName|String|The domain name information.|
|DataInterval|String|The data sampling interval. Unit: seconds.|
|StartTime|DateTime|The beginning of the time range where the data was queried.|
|EndTime|DateTime|The end of the time range where the data was queried.|
|HitRateInterval|DataModule\[\]|The byte hit rate at each data sampling interval. The byte hit rate is measured in percentage.|

DataModule

|Parameter|Type|Description|
|---------|----|-----------|
|TimeStamp|String|The timestamp of the data.|
|Value|String|The detailed byte hit rate data.|
|HttpsValue|String|The byte hit rate of HTTPS requests.|

## Examples {#section_ol8_1q4_dv2 .section}

Sample request

``` {#codeblock_lr5_wa4_z2b}
http://cdn.aliyuncs.com?Action=DescribeDomainHitRateData&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_08i_bah_6se .language-json}
{
    "DomainName": "example.com",
    "DataInterval": "300",
    "RequestId": "5ADA5190-EE5B-4EF2-BE00-DC441B8D81DD",
    "StartTime": "2015-12-10T20:00:00Z",
    "EndTime": "2015-12-10T21:00:00Z",
    "HitRateInterval": {
        "DataModule": [
            {
                "TimeStamp": "2015-12-10T21:00:00Z",
                "Value": "100.0",
                "HttpsValue": "50.0"
            },
            {
                "TimeStamp": "2015-12-10T20:35:00Z",
                "Value": "100.0",
                "HttpsValue": "50.0"
            },
            {
                "TimeStamp": "2015-12-10T20:50:00Z",
                "Value": "99.99932881437826",
                "HttpsValue": "50.0"
            }
        ]
    }
}
```

## Error codes {#section_6ty_iu2_3hx .section}

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
|MissingParameter|StartTime and EndTime can not be single.|400|The error message returned because you must specify both the StartTime and EndTime parameters.|
|InvalidStartTime.Malformed|Specified start time is malformed.|400|The error message returned because the format of the StartTime parameter is invalid.|
|InvalidEndTime.Malformed|Specified end time is malformed.|400|The error message returned because the format of the EndTime parameter is invalid.|
|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|400|The error message returned because the EndTime is earlier than the StartTime.|
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|The error message returned because the time range specified by the EndTime and StartTime parameters exceeds 90 days.|

