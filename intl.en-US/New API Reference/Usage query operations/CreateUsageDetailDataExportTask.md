# CreateUsageDetailDataExportTask {#reference2433 .reference}

You can call the CreateUsageDetailDataExportTask operation to create a task to export 5-minute usage details for one or more CDN domains under your account and generate an Excel file for downloading.

**Note:** This operation has been available from July 20, 2018 and can be used to create a task that queries data of up to one year. The maximum time range that can be queried for an export task is one month.

## Debugging {#section_4no_gtg_doo .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=CreateUsageDetailDataExportTask) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_14v_4vp_nk9 .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to CreateUsageDetailDataExportTask.|
|StartTime|String|Yes|The beginning of the time range where the data is queried. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.|
|EndTime|String|Yes|The end of the time range where the data is queried. The end time must be later than the start time. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.|
|Group|String|No|The domain name group. If you specify this parameter, you do not need to specify the DomainNames parameter.|
|DomainNames|String|No| -   The names of the CDN domains of which the data is queried. If you do not specify a domain name group, the data of the CDN domains specified by this parameter is exported.
-   If you do not specify this parameter or the Group parameter, the data of all CDN domains under your account is exported.

 |
|Type|String|Yes|The type of usage data. Valid values: flow and vas.|
|TaskName|String|No|The name of the task to be created.|

## Response parameters {#section_ej9_sw8_rb0 .section}

|Parameter|Type|Description|
|---------|----|-----------|
|RequestId|String|The ID of the request.|
|StartTime|String|The beginning of the time range where the data was queried.|
|End time.|String|The end of the time range where the data was queried.|
|TaskId|String|The ID of the task.|

## Examples {#section_4mj_0kg_5qt .section}

Sample request

``` {#codeblock_jd3_uj3_e1x}
http://cdn.aliyuncs.com?Action=CreateUsageDetailDataExportTask&Type=flow
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<Common request parameters>          
```

Sample success response

`JSON` format

``` {#codeblock_7qe_wb3_bf2}
{
  "RequestId": "ED61C6C3-8241-4187-AAA7-5157AE175CEC",
  "StartTime": "2018-12-10T20:00:00Z",
  "EndTime": "2018-12-10T21:00:00Z",
  "TaskId": "123456"
}
```

## Error codes {#section_s7i_ww6_gkg .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|Throttling|Request was denied due to request throttling.|503|The error message returned because the request was denied due to throttling.|
|IllegalOperation|Illegal domain, operation is not permitted.|403|The error message returned because the specified domain name is invalid.|
|OperationDenied|Your account does not open Cdn service yet.|403|The error message returned because CDN has not been activated for your account.|
|OperationDenied|Your Cdn service is suspended.|403|The error message returned because CDN has been suspended for your account.|
|InvalidParameter|Invalid Parameter.|400|The error message returned because the parameters are invalid.|
|InvalidParameterProduct|Invalid Parameter Product.|400|The error message returned because the specified Product parameter is invalid.|
|InvalidParameterDimension|Invalid Parameter Dimension.|400|The error message returned because the specified Dimension parameter is invalid.|
|InvalidParameterBillType|Invalid Parameter BillType.|400|The error message returned because the specified BillType parameter is invalid.|
|InvalidParameterAliuid|Invalid Parameter Aliuid.|400|The error message returned because the specified Aliuid parameter is invalid.|
|InvalidParameterStartTime|Invalid Parameter StartTime.|400|The error message returned because the specified StartTime parameter is invalid.|
|InvalidParameterEndTime|Invalid Parameter EndTime.|400|The error message returned because the specified EndTime parameter is invalid.|
|InvalidTimeRange|StartTime and EndTime range should less than 1 month.|400|The error message returned because the duration specified by the StartTime and EndTime parameters exceeds the maximum value of 31 days.|
|InvalidParameterOperator|Invalid Parameter Operator.|400|The error message returned because the specified Operator parameter is invalid.|

