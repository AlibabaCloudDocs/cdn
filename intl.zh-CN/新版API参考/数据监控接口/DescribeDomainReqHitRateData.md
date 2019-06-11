# DescribeDomainReqHitRateData {#reference3687 .reference}

调用DescribeDomainReqHitRateData获取加速域名的请求命中率（命中请求百分比）。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   支持批量域名查询，多个域名用半角逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#section_q9s_7uv_0d6 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainReqHitRateData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_vi0_519_33c .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainReqHitRateData。|
|DomainName|String|否|需要查询的加速域名。如果不写，则默认全部域名。|
|StartTime|String|否|获取数据起始时间点。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟， 不写默认读取过去24小时数据。

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

## 返回参数 {#section_67p_4wk_l4f .section}

|名称|类型|描述|
|--|--|--|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，以秒为单位。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|ReqHitRateInterval|DataModule\[\]|每个时间间隔的请求命中百分占比。|

DataModule

|名称|类型|描述|
|--|--|--|
|TimeStamp|String|时间片起始时刻。|
|Value|String|详细使用数据。|
|HttpsValue|String|https请求命中率。|

## 示例 {#section_yv9_q4t_zp5 .section}

请求示例

``` {#codeblock_bgp_shf_aj1}
http://cdn.aliyuncs.com?Action=DescribeDomainReqHitRateData&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_g8z_rtg_mdq .language-json}
{
    "DomainName": "example.com",
    "DataInterval": "300",
    "RequestId": "5ADA5190-EE5B-4EF2-BE00-DC441B8D81DD",
    "StartTime": "2015-12-10T20:00Z",
    "EndTime": "2015-12-10T21:00Z",
    "ReqHitRateInterval": {
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
            }
        ]
    }
}
```

## 错误码 {#section_zc2_mzo_mz5 .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain, operation is not permitted.|403|非法域名, 无法操作。|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|InvalidDomain.Offline|The domain provided is offline.|404|域名已下线。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中，请稍后再试。|
|InvalidDomain.Configure\_failed|Failed to configure the provided domain.|500|域名配置失败。|
|MissingParameter|StartTime and EndTime can not be single.|400|StartTime和EndTime不能单独设置。|
|InvalidStartTime.Malformed|Specified start time is malformed.|400|StartTime格式错误|
|InvalidEndTime.Malformed|Specified end time is malformed.|400|EndTime格式错误。|
|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|400|EndTime小于StartTime。|
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|EndTime和StartTime差值超过90天。|

