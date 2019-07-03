# DescribeDomainUvData {#reference6082 .reference}

调用DescribeDomainUvData获取加速域名最小1小时粒度的 UV页面独立访问统计。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   只支持一个域名或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#section_054_kqv_tgs .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainUvData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_mhk_7tp_0f3 .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainUvData。|
|DomainName|String|是|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。|
|StartTime|String|否|获取数据起始时间点。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为1小时， 不写默认读取过去24小时数据。

 |
|EndTime|String|否| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回参数 {#section_mdc_mwg_e4u .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，以秒为单位，固定值1小时。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|UvDataInterval|UsageData\[\]|每个时间间隔的页面独立访问次数。|

UsageData

|名称|类型|描述|
|--|--|--|
|TimeStamp|String|时间片起始时刻。|
|Value|String|详细使用数据。|

## 示例 {#section_3xc_52m_v53 .section}

请求示例

``` {#codeblock_kat_4za_0qw}
http://cdn.aliyuncs.com?Action=DescribeDomainUvData&DomainName=example.com
&StartTime=2015-11-29T00:00:00Z
&EndTime=2015-11-30T00:00:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_mf9_7rm_vwt .language-json}
{
    "DataInterval": "3600",
    "RequestId": "E9D3257A-1B7C-414C-90C1-8D07AC47BCAC",
    "DomainName": "example.com",
    "EndTime": "2015-11-30T00:00:00Z",
    "StartTime": "2015-11-29T00:00:00Z",
    "UvDataInterval": {
        "UsageData": [
            {
                "TimeStamp": "2015-11-29T20:00:00Z",
                "Value": "318"
            },
            {
                "TimeStamp": "2015-11-29T18:00:00Z",
                "Value": "318"
            },
            {
                "TimeStamp": "2015-11-29T03:00:00Z",
                "Value": "329"
            },
            {
                "TimeStamp": "2015-11-29T21:00:00Z",
                "Value": "316"
            },
            {
                "TimeStamp": "2015-11-29T07:00:00Z",
                "Value": "319"
            },
            {
                "TimeStamp": "2015-11-29T00:00:00Z",
                "Value": "326"
            },
            {
                "TimeStamp": "2015-11-29T11:00:00Z",
                "Value": "321"
            },
            {
                "TimeStamp": "2015-11-29T10:00:00Z",
                "Value": "313"
            },
            {
                "TimeStamp": "2015-11-29T08:00:00Z",
                "Value": "331"
            },
            {
                "TimeStamp": "2015-11-29T01:00:00Z",
                "Value": "324"
            },
            {
                "TimeStamp": "2015-11-29T04:00:00Z",
                "Value": "330"
            },
            {
                "TimeStamp": "2015-11-29T14:00:00Z",
                "Value": "335"
            },
            {
                "TimeStamp": "2015-11-29T12:00:00Z",
                "Value": "318"
            },
            {
                "TimeStamp": "2015-11-29T23:00:00Z",
                "Value": "310"
            },
            {
                "TimeStamp": "2015-11-29T17:00:00Z",
                "Value": "309"
            },
            {
                "TimeStamp": "2015-11-29T22:00:00Z",
                "Value": "320"
            },
            {
                "TimeStamp": "2015-11-29T16:00:00Z",
                "Value": "309"
            },
            {
                "TimeStamp": "2015-11-29T02:00:00Z",
                "Value": "317"
            },
            {
                "TimeStamp": "2015-11-29T06:00:00Z",
                "Value": "309"
            },
            {
                "TimeStamp": "2015-11-29T19:00:00Z",
                "Value": "308"
            },
            {
                "TimeStamp": "2015-11-29T13:00:00Z",
                "Value": "347"
            },
            {
                "TimeStamp": "2015-11-29T15:00:00Z",
                "Value": "341"
            },
            {
                "TimeStamp": "2015-11-29T05:00:00Z",
                "Value": "347"
            },
            {
                "TimeStamp": "2015-11-29T09:00:00Z",
                "Value": "312"
            }
        ]
    }
}
			
```

## 错误码 {#section_qgr_b3w_36b .section}

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
|InvalidStartTime.Malformed|Specified start time is malformed.|400|StartTime格式错误。|
|InvalidEndTime.Malformed|Specified end time is malformed.|400|EndTime格式错误。|
|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|400|EndTime小于StartTime。|
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|EndTime和StartTime差值超过90天。|
|InvalidDomainName.ValueNotSupported|The specified value of parameter DomainName only support one or empty value.|400|DomainName只支持一个值或者不填。|

CDN所有API错误码，详情请参见[CDN错误码](https://error-center.aliyun.com/status/product/Cdn)。

