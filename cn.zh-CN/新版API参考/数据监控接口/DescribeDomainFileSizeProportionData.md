# DescribeDomainFileSizeProportionData {#reference8618 .reference}

调用DescribeDomainFileSizeProportionData获取加速域名最小1小时粒度的文件大小占比统计。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   只支持一个域名或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#section_n6g_ex3_xt0 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainFileSizeProportionData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_g4d_9f7_wl0 .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainFileSizeProportionData。|
|DomainName|String|是|需要查询的加速域名，只支持一个域名。|
|StartTime|String|否|获取数据起始时间点。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为1小时。
-   不写默认读取过去24小时数据。

 |
|EndTime|String|否| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回参数 {#section_e8p_63u_be5 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，固定值1小时或1天。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|FileSizeProportionDataInterval|UsageData\[\]|每个时间间隔的每秒访问数据。|

UsageData

|名称|类型|描述|
|--|--|--|
|TimeStamp|String|时间片起始时刻。|
|Value|FileSizeProportionData\[\]|各文件大小占比数据list。|

FileSizeProportionData

|名称|类型|描述|
|--|--|--|
|FileSize|String|文件大小类型。|
|Proportion|String|占比使用数据。|

## 示例 {#section_xs2_1wn_w2t .section}

请求示例

``` {#codeblock_ttn_pp9_ers}
http://cdn.aliyuncs.com?Action=DescribeDomainFileSizeProportionData&DomainName=example.com
&StartTime=2015-11-30T01:33:00Z
&EndTime=2015-11-30T05:40:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_vqh_39o_zvn .language-json}
{
    "DataInterval": "3600",
    "RequestId": "23ACE7E2-2302-42E3-98F8-E5E697FD86C3",
    "FileSizeProportionDataInterval": {
        "UsageData": [
            {
                "Value": {
                    "FileSizeProportionData": [
                        {
                            "FileSize": "<1M",
                            "Proportion": "7.91"
                        },
                        {
                            "FileSize": "<20K",
                            "Proportion": "0.137"
                        },
                        {
                            "FileSize": "<5K",
                            "Proportion": "64.544"
                        },
                        {
                            "FileSize": ">1M",
                            "Proportion": "21.334"
                        },
                        {
                            "FileSize": "<10K",
                            "Proportion": "0.01"
                        },
                        {
                            "FileSize": "<50K",
                            "Proportion": "0.02"
                        },
                        {
                            "FileSize": "<100K",
                            "Proportion": "6.046"
                        }
                    ]
                },
                "TimeStamp": "2015-11-30T03:00:00Z"
            },
            {
                "Value": {
                    "FileSizeProportionData": [
                        {
                            "FileSize": "<1M",
                            "Proportion": "4.564"
                        },
                        {
                            "FileSize": "<20K",
                            "Proportion": "0.645"
                        },
                        {
                            "FileSize": "<5K",
                            "Proportion": "69.746"
                        },
                        {
                            "FileSize": ">1M",
                            "Proportion": "18.534"
                        },
                        {
                            "FileSize": "<10K",
                            "Proportion": "0.01"
                        },
                        {
                            "FileSize": "<50K",
                            "Proportion": "0.068"
                        },
                        {
                            "FileSize": "<100K",
                            "Proportion": "6.432"
                        }
                    ]
                },
                "TimeStamp": "2015-11-30T04:00:00Z"
            },
            {
                "Value": {
                    "FileSizeProportionData": [
                        {
                            "FileSize": "<1M",
                            "Proportion": "16.066"
                        },
                        {
                            "FileSize": "<20K",
                            "Proportion": "0.07"
                        },
                        {
                            "FileSize": "<5K",
                            "Proportion": "52.842"
                        },
                        {
                            "FileSize": ">1M",
                            "Proportion": "26.43"
                        },
                        {
                            "FileSize": "<10K",
                            "Proportion": "0.018"
                        },
                        {
                            "FileSize": "<50K",
                            "Proportion": "0.026"
                        },
                        {
                            "FileSize": "<100K",
                            "Proportion": "4.547"
                        }
                    ]
                },
                "TimeStamp": "2015-11-30T02:00:00Z"
            },
            {
                "Value": {
                    "FileSizeProportionData": [
                        {
                            "FileSize": "<1M",
                            "Proportion": "4.521"
                        },
                        {
                            "FileSize": "<20K",
                            "Proportion": "1.551"
                        },
                        {
                            "FileSize": "<5K",
                            "Proportion": "68.254"
                        },
                        {
                            "FileSize": ">1M",
                            "Proportion": "18.625"
                        },
                        {
                            "FileSize": "<10K",
                            "Proportion": "0.631"
                        },
                        {
                            "FileSize": "<50K",
                            "Proportion": "0.026"
                        },
                        {
                            "FileSize": "<100K",
                            "Proportion": "6.392"
                        }
                    ]
                },
                "TimeStamp": "2015-11-30T05:00:00Z"
            }
        ]
    },
    "DomainName": "example.com",
    "EndTime": "2015-11-30T05:40:00Z",
    "StartTime": "2015-11-30T01:33:00Z"
}
```

## 错误码 {#section_fa4_ta8_jcv .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain, operation is not permitted.|403|无效域名。|
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
|InvalidDomainName.ValueNotSupported|The specified value of parameter DomainName only support one or empty value.|400|DomainName只支持一个值或者不填。|

