# DescribeDomainsUsageByDay {#reference4378 .reference}

调用DescribeDomainsUsageByDay获取加速域名天粒度监控统计数据。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#section_4es_has_5tj .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainsUsageByDay)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_dky_ylu_nmt .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainsUsageByDay。|
|DomainName|String|否|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。|
|StartTime|String|否|获取数据起始时间点。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|EndTime|String|否| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回参数 {#section_02p_lfm_tap .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，固定值1天。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|UsageByDays|UsageByDay\[\]|每个时间间隔统计数据。|
|UsageTotal|UsageTotal|汇总数据。|

UsageByDay

|名称|类型|描述|
|--|--|--|
|TimeStamp|String|时间片起始时刻。|
|Qps|String|每秒访问量。|
|BytesHitRate|String|命中率。|
|RequestHitRate|String|请求命中率。|
|MaxBps|String|带宽峰值。|
|MaxBpsTime|String|带宽峰值时刻。|
|MaxSrcBps|String|回源带宽峰值。|
|MaxSrcBpsTime|String|回源带宽峰值时刻。|
|TotalAccess|String|总访问量。|
|TotalTraffic|String|总流量。|

UsageTotal

|名称|类型|描述|
|--|--|--|
|BytesHitRate|String|命中率。|
|RequestHitRate|String|请求命中率。|
|MaxBps|String|带宽峰值。|
|MaxBpsTime|String|带宽峰值时刻。|
|MaxSrcBps|String|回源带宽峰值。|
|maxSrcBpsTime|String|回源带宽峰值时刻。|
|TotalAccess|String|总访问量。|
|TotalTraffic|String|总流量。|

## 示例 {#section_aoq_7up_86a .section}

请求示例

``` {#codeblock_r6s_7ax_xeo}
http://cdn.aliyuncs.com?Action=DescribeDomainsUsageByDay&DomainName=example.com
&StartTime=2015-11-29T00:00:00Z
&EndTime=2015-11-30T00:00:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_cfq_83m_nd4 .language-json}
{
  "UsageTotal": {
    "RequestHitRate": "69.92610837438424",
    "MaxSrcBpsTime": "2015-12-02 17:20",
    "MaxBps": "1.0747912780000001E8",
    "MaxSrcBps": "2108177.5",
    "TotalTraffic": "1117711832100",
    "TotalAccess": "1319500",
    "MaxBpsTime": "2015-12-02 23:55",
    "BytesHitRate": "97.03110726801242"
  },
  "DataInterval": "86400",
  "UsageByDays": {
    "UsageByDay": [
      {
        "TimeStamp": "2015-12-01",
        "RequestHitRate": "70.24770071912111",
        "MaxSrcBpsTime": "2015-12-01 22:30",
        "MaxSrcBps": "1044521.5000000001",
        "MaxBps": "1.050307709E8",
        "TotalTraffic": "564300099309",
        "TotalAccess": "645093",
        "MaxBpsTime": "2015-12-01 01:20",
        "Qps": "7.466354166666667",
        "BytesHitRate": "97.46250599529726"
      },
      {
        "TimeStamp": "2015-12-02",
        "RequestHitRate": "69.61849446995657",
        "MaxSrcBpsTime": "2015-12-02 17:20",
        "MaxSrcBps": "2108177.5",
        "MaxBps": "1.0747912780000001E8",
        "TotalTraffic": "553411732791",
        "TotalAccess": "674407",
        "MaxBpsTime": "2015-12-02 23:55",
        "Qps": "7.805636574074074",
        "BytesHitRate": "96.59122077803737"
      }
    ]
  },
  "RequestId": "C88EF8ED-72F0-45EA-9E86-95114E224FC5",
  "DomainName": "example.com",
  "EndTime": "2015-12-02T00:00:00Z",
  "StartTime": "2015-12-01T00:00:00Z"
}
```

## 错误码 {#section_87j_stf_lbm .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|InvalidStartTime.Malformed|Specified StartTime is malformed.|400|StartTime格式错误。|
|InvalidEndTime.Malformed|Specified EndTime is malformed.|400|EndTime格式错误。|
|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|400|EndTime和StartTime差值超过90天。|
|InvalidDomain.NotFound|The domain provided does not exist in our records.|404|域名不存在或不属于当前用户。|
|InvalidEndTime.Mismatch|Specified EndTime does not math the specified StartTime.|400|EndTime小于StartTime。|

