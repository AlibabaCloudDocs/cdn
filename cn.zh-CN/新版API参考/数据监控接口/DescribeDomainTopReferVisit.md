# DescribeDomainTopReferVisit {#reference3872 .reference}

调用DescribeDomainTopReferVisit获取加速域名某天的热门页面引用次数排名。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   只支持一个域名或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#section_867_65g_kge .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainTopReferVisit)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_b14_t1s_d49 .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainTopReferVisit。|
|DomainName|String|是|域名支持多选，默认返回所有加速域名合并后数据。 可输入需要查询的加速域名 ，多个域名用逗号`,`分隔。|
|StartTime|String|否|获取数据起始时间。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。
-   不写默认读取过去24小时数据。

 |
|EndTime|String|否|结束时间，需大于起始时间。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|SortBy|String|否|排序方式。支持traf和pv，默认值：pv。|

## 返回参数 {#section_vt5_k5u_82f .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|DomainName|String|加速域名信息。|
|StartTime|String|查询指定日期。|
|TopReferList|ReferList\[\]|全部热门ReferUrllist。|

ReferList

|名称|类型|描述|
|--|--|--|
|ReferDetail|String|完整的ReferUrl地址。|
|VisitData|String|访问次数。|
|VisitProportion|Float|访问占比。|
|Flow|String|流量，单位：byte。|
|FlowProportion|Float|流量占比。|

## 示例 {#section_wcy_kwk_gzf .section}

请求示例

``` {#codeblock_3t4_n6j_knz}
http://cdn.aliyuncs.com?Action=DescribeDomainTopReferVisit&DomainName=example.com
&StartTime=2018-10-03T16:00:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_1pb_dj2_l3u .language-json}
{
    "TopReferList": {
        "ReferList": [
            {
                "VisitData": "229567",
                "ReferDetail": "-",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "2496",
                "ReferDetail": "123.57.158.8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "448",
                "ReferDetail": "example1.com",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "3",
                "ReferDetail": "example2.net",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    },
    "RequestId": "95994621-8382-464B-8762-C708E73568D1",
    "DomainName": "example.com",
    "StartTime": "2018-10-03T16:00:00Z"
}       
```

## 特殊错误码 {#section_l64_lmn_m8t .section}

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
|MissingParameter|The specified value of parameter StartTime is not valid.|400|缺少StartTime参数。|
|InvalidStartTime.Malformed|Specified start time is malformed.|400|StartTime格式错误。|
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|当前时间和StartTime差值超过90天。|
|InvalidDomainName.ValueNotSupported|The specified value of parameter DomainName only support one or empty value.|400|DomainName只支持一个值或者不填。|

CDN所有API错误码，详情请参见[CDN错误码](https://error-center.aliyun.com/status/product/Cdn)。

