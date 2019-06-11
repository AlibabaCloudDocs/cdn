# DescribeDomainPvData {#reference6100 .reference}

调用DescribeDomainPvData获取加速域名最小1小时粒度的 PV页面访问统计。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#section_2td_1t0_d2x .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainPvData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_7kd_m3z_jur .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainPvData。|
|DomainName|String|是|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。|
|StartTime|String|否|获取数据起始时间点。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为1小时， 不写默认读取过去24小时数据。

 |
|EndTime|String|否| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回参数 {#section_vnq_d43_a7t .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，固定值1小时或1天。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|PvDataInterval|UsageData\[\]|每个时间间隔的页面访问次数。|

UsageData

|名称|类型|描述|
|--|--|--|
|TimeStamp|String|时间片起始时刻。|
|Value|String|详细使用数据。|

## 示例 {#section_fxa_zpi_sun .section}

请求示例

``` {#codeblock_xop_6gs_lao}
http://cdn.aliyuncs.com?Action=DescribeDomainPvData&DomainName=example.com &StartTime=2015-11-28T00:00:00Z &EndTime=2015-11-29T00:00:00Z &<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_wzn_oqk_hn6 .language-json}
{
    "DataInterval": "3600",
    "RequestId": "BCD7D917-76F1-442F-BB75-C810DE34C761",
    "DomainName": "example.com",
    "EndTime": "2015-11-29T00:00:00Z",
    "PvDataInterval": {
        "UsageData": [
            {
                "TimeStamp": "2015-11-28T03:00:00Z",
                "Value": "9292"
            },
            {
                "TimeStamp": "2015-11-28T23:00:00Z",
                "Value": "9239"
            },
            {
                "TimeStamp": "2015-11-28T07:00:00Z",
                "Value": "9464"
            },
            {
                "TimeStamp": "2015-11-28T12:00:00Z",
                "Value": "9379"
            },
            {
                "TimeStamp": "2015-11-28T22:00:00Z",
                "Value": "9243"
            },
            {
                "TimeStamp": "2015-11-28T10:00:00Z",
                "Value": "10063"
            },
            {
                "TimeStamp": "2015-11-28T15:00:00Z",
                "Value": "9068"
            },
            {
                "TimeStamp": "2015-11-28T14:00:00Z",
                "Value": "9353"
            },
            {
                "TimeStamp": "2015-11-28T04:00:00Z",
                "Value": "9513"
            },
            {
                "TimeStamp": "2015-11-28T02:00:00Z",
                "Value": "9377"
            },
            {
                "TimeStamp": "2015-11-28T08:00:00Z",
                "Value": "9579"
            },
            {
                "TimeStamp": "2015-11-28T20:00:00Z",
                "Value": "9109"
            },
            {
                "TimeStamp": "2015-11-28T09:00:00Z",
                "Value": "10631"
            },
            {
                "TimeStamp": "2015-11-28T06:00:00Z",
                "Value": "9587"
            },
            {
                "TimeStamp": "2015-11-28T01:00:00Z",
                "Value": "9108"
            },
            {
                "TimeStamp": "2015-11-28T16:00:00Z",
                "Value": "9454"
            },
            {
                "TimeStamp": "2015-11-28T21:00:00Z",
                "Value": "9285"
            },
            {
                "TimeStamp": "2015-11-28T19:00:00Z",
                "Value": "9059"
            },
            {
                "TimeStamp": "2015-11-28T00:00:00Z",
                "Value": "9470"
            },
            {
                "TimeStamp": "2015-11-28T05:00:00Z",
                "Value": "11830"
            },
            {
                "TimeStamp": "2015-11-28T13:00:00Z",
                "Value": "9992"
            },
            {
                "TimeStamp": "2015-11-28T17:00:00Z",
                "Value": "9529"
            },
            {
                "TimeStamp": "2015-11-28T18:00:00Z",
                "Value": "9203"
            },
            {
                "TimeStamp": "2015-11-28T11:00:00Z",
                "Value": "9604"
            }
        ]
    },
    "StartTime": "2015-11-28T00:00:00Z"
}
```

## 错误码 {#section_nkw_im1_ber .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain, operation is not permitted.|403|非法域名, 无法操作。|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|InvalidDomain.Offline|The domain provided is offline.|404|域名已下线。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中, 请稍后再试。|
|InvalidDomain.Configure\_failed|Failed to configure the provided domain.|500|域名配置失败。|
|MissingParameter|StartTime and EndTime can not be single.|400|StartTime和EndTime不能单独设置。|
|InvalidStartTime.Malformed|Specified StartTime is malformed.|400|StartTime格式错误。|
|InvalidEndTime.Malformed|Specified EndTime is malformed.|400|EndTime格式错误。|
|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|400|EndTime小于StartTime。|
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|EndTime和StartTime差值超过90天。|
|InvalidDomainName.ValueNotSupported|The specified value of parameter DomainName only support one or empty value.|400|DomainName只支持一个值或者不填。|

