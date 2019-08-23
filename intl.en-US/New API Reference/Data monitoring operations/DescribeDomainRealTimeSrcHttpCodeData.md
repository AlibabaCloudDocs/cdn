# DescribeDomainRealTimeSrcHttpCodeData {#reference6100 .reference}

You can call the DescribeDomainRealTimeSrcHttpCodeData operation to query the proportions of HTTP status codes based on back-to-origin statistics with a time granularity of one minute.

If you set both the StartTime and EndTime parameters, the data within the specified time range is queried.

**Note:** 

-   For each query, the time range specified by the StartTime and EndTime parameters cannot exceed 24 hours.
-   If neither the StartTime nor EndTime parameter is set, the data within the last hour is queried.
-   You can specify one or more domain names and separate them with commas \(,\).
-   The maximum time range that you can specify is the last seven days.

## Request parameters {#section_izv_cmm_1q5 .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeDomainRealTimeSrcHttpCodeData.|
|DomainName|String|Yes|The domain names that you want to query. Separate multiple domain names with commas \(,\).|
|StartTime|String|No|The beginning of the time range where the data is queried. -   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.
-   If you do not set this parameter, the data within the last hour is queried.

 |
|EndTime|String|No| -   The end of the time range where the data is queried. The end time must be later than the start time.
-   Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format.
-   The time must be in UTC.

 |

## Response parameters {#section_ofe_9so_nsj .section}

|Parameter|Type|Description|
|---------|----|-----------|
|RequestId|String|The ID of the request.|
|DomainName|String|The domain name information.|
|DataInterval|String|The data sampling interval, which is set to 60 seconds.|
|StartTime|DateTime|The beginning of the time range where the data was queried.|
|EndTime|DateTime|The end of the time range where the data was queried.|
|RealTimeSrcHttpCodeData|UsageData\[\]|The proportions of HTTP status codes at each sampling interval.|

UsageData

|Parameter|Type|Description|
|---------|----|-----------|
|TimeStamp|String|The timestamp of the data.|
|Value|RealTimeSrcCodeProportionData\[\]|The list of the proportions of HTTP status codes.|

CodeProportionData

|Parameter|Type|Description|
|---------|----|-----------|
|Code|String|The HTTP status code.|
|Proportion|String|The proportion of the HTTP status code.|

## Examples {#section_th2_6hl_fuy .section}

Sample request

``` {#codeblock_m7f_nst_mfh}
http://cdn.aliyuncs.com?Action=DescribeDomainRealTimeSrcHttpCodeData&DomainName=example1.com,example2.com
&StartTime=2015-11-30T05:39:00Z
&EndTime=2015-11-30T05:40:00Z
&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_qao_5y6_64s}
{
    "RealTimeSrcHttpCodeData": {
        "UsageData": [
            {
                "TimeStamp": "2015-11-30T05:40:00Z",
                "Value": {
                    "RealTimeSrcCodeProportionData": [
                        {
                            "Proportion": "66.046511627907",
                            "Code": "200"
                        },
                        {
                            "Proportion": "4.72868217054264",
                            "Code": "206"
                        },
                        {
                            "Proportion": "0.155038759689922",
                            "Code": "302"
                        },
                        {
                            "Proportion": "0.62015503875969",
                            "Code": "304"
                        },
                        {
                            "Proportion": "28.4496124031008",
                            "Code": "500"
                        }
                    ]
                }
            },
            {
                "TimeStamp": "2015-11-30T05:39:00Z",
                "Value": {
                    "RealTimeSrcCodeProportionData": [
                        {
                            "Proportion": "66.046511627907",
                            "Code": "200"
                        },
                        {
                            "Proportion": "4.72868217054264",
                            "Code": "206"
                        },
                        {
                            "Proportion": "0.155038759689922",
                            "Code": "302"
                        },
                        {
                            "Proportion": "0.62015503875969",
                            "Code": "304"
                        },
                        {
                            "Proportion": "28.4496124031008",
                            "Code": "500"
                        }
                    ]
                }
            }
        ]
    },
    "DataInterval": "60",
    "RequestId": "BC858082-736F-4A25-867B-E5B67C85ACF7",
    "DomainName": "example1.com,example2.com",
    "EndTime": "2015-11-30T05:40:00Z",
    "StartTime": "2015-11-30T05:33:00Z"
}
```

## Error codes {#section_fgq_dtx_dgb .section}

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
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|The error message returned because the time range specified by the EndTime and StartTime parameters exceeds 90 days.|

