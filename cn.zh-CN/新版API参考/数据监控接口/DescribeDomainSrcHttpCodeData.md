# DescribeDomainSrcHttpCodeData {#reference6592 .reference}

调用DescribeDomainSrcHttpCodeData获取加速域名最小5分钟粒度的回源HTTP返回码占比数据。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   只支持一个域名或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#section_gth_1zb_mkm .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainSrcHttpCodeData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_pb0_i6q_qef .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数取值：DescribeDomainSrcHttpCodeData。|
|DomainName|String|是|需要查询的加速域名，支持批量，多个域名用`,`分隔。|
|StartTime|String|否|获取数据起始时间点。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。
-   不写默认读取过去24小时数据。

 |
|EndTime|String|否| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Interval|String|否| -   查询数据的时间粒度，支持300、 3600和86400秒。
-   3天以内（不包含3天整）支持300、 3600、 86400。
-   3-31天（不包含31天整）支持3600和86400。
-   31天以上支持86400。
-   不传和传的值不支持时，使用默认值。

 |

## 返回参数 {#section_adg_0tp_ert .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，以秒为单位，固定值300S。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|HttpCodeData|UsageData\[\]|每个时间间隔的HTTP返回码占比数据。|

UsageData

|名称|类型|描述|
|--|--|--|
|TimeStamp|String|时间片起始时刻。|
|Value|CodeProportionData\[\]|各返回码占比使用数据list。|

CodeProportionData

|名称|类型|描述|
|--|--|--|
|Code|String|http返回码。|
|Proportion|String|占比使用数据。|
|Count|String|总数。|

## 示例 {#section_d5t_mng_taw .section}

请求示例

``` {#codeblock_tcf_m5o_f29}
http://cdn.aliyuncs.com?Action=DescribeDomainSrcHttpCodeData&DomainName="example1.com,example2.com"
&StartTime=2015-11-30T05:33:00Z
&EndTime=2015-11-30T05:40:00Z
&<公共请求参数>           
```

正常返回示例

`JSON`格式

``` {#codeblock_s65_qg5_7de .language-json}
{
    "HttpCodeData": {
        "UsageData": [
            {
                "TimeStamp": "2015-11-30T05:40:00Z",
                "Value": {
                    "CodeProportionData": [
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
                "TimeStamp": "2015-11-30T05:35:00Z",
                "Value": {
                    "CodeProportionData": [
                        {
                            "Proportion": "64.7822765469824",
                            "Code": "200"
                        },
                        {
                            "Proportion": "3.74331550802139",
                            "Code": "206"
                        },
                        {
                            "Proportion": "0.152788388082506",
                            "Code": "302"
                        },
                        {
                            "Proportion": "1.90985485103132",
                            "Code": "304"
                        },
                        {
                            "Proportion": "29.4117647058824",
                            "Code": "500"
                        }
                    ]
                }
            },
            {
                "TimeStamp": "2015-11-30T05:30:00Z",
                "Value": {
                    "CodeProportionData": [
                        {
                            "Proportion": "67.1458998935037",
                            "Code": "200"
                        },
                        {
                            "Proportion": "12.6730564430245",
                            "Code": "206"
                        },
                        {
                            "Proportion": "0.053248136315229",
                            "Code": "302"
                        },
                        {
                            "Proportion": "0.958466453674121",
                            "Code": "304"
                        },
                        {
                            "Proportion": "19.1693290734824",
                            "Code": "500"
                        }
                    ]
                }
            }
        ]
    },
    "DataInterval": "300",
    "RequestId": "BC858082-736F-4A25-867B-E5B67C85ACF7",
    "DomainName": "example1.com,example2.com",
    "EndTime": "2015-11-30T05:40:00Z",
    "StartTime": "2015-11-30T05:33:00Z"
}            
```

## 错误码 {#section_yb8_yf8_wki .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain, operation is not permitted.|403|非法域名，无法操作。|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于您。|
|InvalidDomain.Offline|The domain provided is offline.|404|域名已下线。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中，请稍后再试。|
|InvalidDomain.Configure\_failed|Failed to configure the provided domain.|500|域名配置失败。|
|MissingParameter|StartTime and EndTime can not be single.|400|StartTime和EndTime不能单独设置。|
|InvalidStartTime.Malformed|Specified start time is malformed.|400|StartTime格式错误。|
|InvalidEndTime.Malformed|Specified end time is malformed.|400|EndTime格式错误。|
|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|400|EndTime小于StartTime。|
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|EndTime和StartTime差值超过90天。|

