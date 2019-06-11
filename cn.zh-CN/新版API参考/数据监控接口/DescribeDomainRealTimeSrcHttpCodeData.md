# DescribeDomainRealTimeSrcHttpCodeData {#reference6100 .reference}

调用DescribeDomainRealTimeSrcHttpCodeData获取加速域名回源1分钟粒度的HTTP返回码占比数据。

不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。

**说明：** 

-   单次查询StartTime和EndTime跨度不能超过24小时。
-   如果StartTime和EndTime均未指定，默认返回当前时间起一小时内的数据。
-   支持批量域名查询，多个域名用半角逗号（,）分隔。
-   最多可获取最近 7 天的数据。

## 请求参数 {#section_izv_cmm_1q5 .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainRealTimeSrcHttpCodeData|
|DomainName|String|是|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。|
|StartTime|String|否|获取数据起始时间点。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   不写默认读取过去1小时数据。

 |
|EndTime|String|否| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回参数 {#section_ofe_9so_nsj .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，以秒为单位，固定值60。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|RealTimeSrcHttpCodeData|UsageData\[\]|每个时间间隔的HTTP返回码占比数据。|

UsageData

|名称|类型|描述|
|--|--|--|
|TimeStamp|String|时间片起始时刻。|
|Value|RealTimeSrcCodeProportionData\[\]|各返回码占比使用数据list。|

CodeProportionData

|名称|类型|描述|
|--|--|--|
|Code|String|http返回码。|
|Proportion|String|占比使用数据。|

## 示例 {#section_th2_6hl_fuy .section}

请求示例

``` {#codeblock_m7f_nst_mfh}
http://cdn.aliyuncs.com?Action=DescribeDomainRealTimeSrcHttpCodeData&DomainName=example1.com,example2.com
&StartTime=2015-11-30T05:39:00Z
&EndTime=2015-11-30T05:40:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

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

## 错误码 {#section_fgq_dtx_dgb .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain, operation is not permitted.|403|非法域名，无法操作。|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|InvalidDomain.Offline|The domain provided is offline.|404|域名已下线。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中，请稍后再试。|
|InvalidDomain.Configure\_failed|Failed to configure the provided domain.|500|域名配置失败。|
|MissingParameter|StartTime and EndTime can not be single.|400|StartTime和EndTime不能单独设置。|
|InvalidStartTime.Malformed|Specified start time is malformed.|400|StartTime格式错误。|
|InvalidEndTime.Malformed|Specified end time is malformed.|400|EndTime格式错误。|
|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|400|EndTime小于StartTime。|
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|EndTime和StartTime差值超过90天。|

