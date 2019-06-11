# DescribeDomainRealTimeSrcTrafficData {#reference3452 .reference}

调用DescribeDomainRealTimeSrcTrafficData获取加速域名的1分钟回源流量监控数据，单位：bit。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   支持批量域名查询，多个域名可用半角逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#section_vos_faf_kc1 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainRealTimeSrcTrafficData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_ixh_d8n_zd4 .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainRealTimeSrcTrafficData。|
|DomainName|String|否| -   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（,）分隔。

 |
|StartTime|String|否|获取数据起始时间点。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   不写默认读取过去 1 小时数据。

 |
|EndTime|String|否| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回参数 {#section_7ly_4kv_48d .section}

|名称|类型|描述|
|--|--|--|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，以秒为单位。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|RealTimeSrcTrafficDataPerInterval|UsageData\[\]|每个时间间隔的回源流量数据。|

UsageData

|名称|类型|描述|
|--|--|--|
|TimeStamp|String|时间片起始时刻。|
|Value|String|详细使用数据。|

## 示例 {#section_az3_r68_g2c .section}

请求示例

``` {#codeblock_1c8_w4h_0v8}
http://cdn.aliyuncs.com?Action=DescribeDomainRealTimeSrcTrafficData&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T20:01:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_jcb_qgz_exb .language-json}
{
    "DomainName": "example.com",
    "DataInterval": "60",
    "RealTimeSrcTrafficDataPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2015-12-10T20:00:00Z",
                "Value": "0"
            },
            {
                "TimeStamp": "2015-12-10T20:01:00Z",
                "Value": "0"
            }
        ]
    },
    "RequestId": "A666D44F-19D6-490E-97CF-1A64AB962C57",
    "StartTime": "2015-12-10T20:00:00Z",
    "EndTime": "2015-12-10T20:01:00Z"
}
			
```

## 错误码 {#section_93m_id6_kjw .section}

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

