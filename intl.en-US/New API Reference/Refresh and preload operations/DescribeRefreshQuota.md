# DescribeRefreshQuota {#reference1270 .reference}

You can call the DescribeRefreshQuota operation to query the limits of the URLs and directories that can be refreshed or preloaded. The limits include the daily maximum number and the remaining number of the day.

**Note:** You can call the RefreshObjectCaches operation to refresh content and call the PushObjectCache operation to preload content.

## Debugging {#section_d1i_7pl_5au .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeRefreshQuota) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_o0i_gyr_18p .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeRefreshQuota.|

## Response parameters {#section_6ln_5bx_pxm .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestId|String|The ID of the request.|
|UrlQuota|String|The maximum number of URLs that can be refreshed each day.|
|DirQuota|String|The maximum number of directories that can be refreshed each day.|
|UrlRemain|String|The remaining number of URLs that can be refreshed for the day.|
|DirRemain|String|The remaining number of directories that can be refreshed for the day.|
|PreloadQuota|String|The maximum number of URLs that can be preloaded each day.|
|PreloadRemain|String|The remaining number of URLs that can be preloaded for the day.|

## Examples {#section_um3_web_d8x .section}

Sample request

``` {#codeblock_z4x_e2q_s17}
http://cdn.aliyuncs.com?Action=DescribeRefreshQuota
&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_hyl_pwx_p08 .language-json}
{
    "DirQuota": "100",
    "DirRemain": "99",
    "RequestId": "42E0554B-80F4-4921-AED6-ACFB22CAAAD0",
    "UrlQuota": "2000",
    "UrlRemain": "1996",
    "PreloadQuota": "500",
    "PreloadRemain": "400"
}
```

## Error codes {#section_qox_6sx_qoq .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|Throttling|Request was denied due to request throttling.|503|The error message returned because the request was denied due to throttling.|
|OperationDenied|Your account does not open CDN service yet.|403|The error message returned because CDN has not been activated for your account.|
|OperationDenied|Your CDN service is suspended.|403|The error message returned because CDN has been suspended for your account.|

