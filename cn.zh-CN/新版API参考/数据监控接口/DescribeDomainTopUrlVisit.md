# DescribeDomainTopUrlVisit {#reference6138 .reference}

调用DescribeDomainTopUrlVisit获取加速域名某天内的热门URL列表。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   只支持一个域名或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#section_c1p_vku_m1o .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainTopUrlVisit)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_1ao_2l4_fgb .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainTopUrlVisit。|
|DomainName|String|是|只支持一个域名。|
|StartTime|String|否|开始获取数据的时间点。 -   格式为：YYYY-MM-DDThh:mm:ssZ。
-   查询某天的数据，建议传YYYY-MM-DDT16:00:00Z。
-   不写默认读取过去24小时数据。

 |
|SortBy|String|否|排序方式。支持traf和pv，默认pv。|

## 返回参数 {#section_bwm_vdq_rxd .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|DomainName|String|加速域名信息。|
|StartTime|String|查询指定日期。|
|AllUrlList|UrlList\[\]|全部热门URLlist。|
|Url200List|UrlList\[\]|返回为2xx的Urllist。|
|Url300List|UrlList\[\]|返回为3xx的Urllist。|
|Url400List|UrlList\[\]|返回为4xx的Urllist。|
|Url500List|UrlList\[\]|返回为5xx的Urllist。|

UrlList

|名称|类型|描述|
|--|--|--|
|UrlDetail|String|完整的Url地址。|
|VisitData|String|访问次数。|
|VisitProportion|Float|访问占比。|
|Flow|String|流量。单位：byte。|
|FlowProportion|Float|流量占比。|

## 示例 {#section_umv_plq_w0p .section}

请求示例

``` {#codeblock_1jp_lb9_u9b}
http://cdn.aliyuncs.com?Action=DescribeDomainTopUrlVisit&DomainName=example.com
&StartTime=2018-10-03T16:00:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_sam_txc_kgl .language-json}
{
    "AllUrlList": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "37",
                "UrlDetail": "http://example1.com/nn_live/nn_x64/ZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }                      
        ]
    },
    "Url300List": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example3.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "3",
                "UrlDetail": "http://example4.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    },
    "Url400List": {
        "UrlList": [
            {
                "VisitData": "1884",
                "UrlDetail": "http://example6.com/nn_live/nn_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "1",
                "UrlDetail": "http://example7.com/nn_live/nn_x64/aWQ9SEEwODgmpbmRleZPTE,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }           
        ]
    },
    "RequestId": "64D28B53-5902-409B-94F6-FD46680144FE",
    "DomainName": "example.com",
    "Url200List": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example8.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "3",
                "UrlDetail": "http://example9.com/nn_live/nn_x64/aWQ9SE5KU01QUDMlPTIwMTxMDk5ZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    },
    "StartTime": "2018-10-03T16:00:00Z",
    "Url500List": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example10.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },           
            {
                "VisitData": "3",
                "UrlDetail": "http://example11.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    }
}
```

## 错误码 {#section_cng_9zy_c77 .section}

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

