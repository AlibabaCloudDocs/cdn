# DescribeTopDomainsByFlow {#reference3734 .reference}

调用DescribeTopDomainsByFlow获取用户按流量排名的域名。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 最多可获取90天的数据。

## 调试 {#section_wf9_nst_gwa .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeTopDomainsByFlow)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_7vd_871_ike .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeTopDomainsByFlow。|
|StartTime|String|否|获取数据起始时间点。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟，不写默认读取当月数据。

 |
|EndTime|String|否| -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Limit|String|否|域名获取数量限制，默认为20，取值支持1~100。|

## 返回参数 {#section_6n6_9qe_78c .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|StartTime|String|开始时间。|
|EndTime|String|结束时间。|
|TopDomains|TopDomain\[\]|排名域名列表。|
|DomainCount|Long|账户下域名总数。|
|DomainOnlineCount|Long|账户下正在运行的域名总数。|

TopDomain

|名称|类型|描述|
|--|--|--|
|DomainName|String|域名。|
|Rank|Long|排名。|
|TotalTraffic|Double|总流量。|
|TrafficPercent|Double|流量占比。|
|MaxBps|Long|带宽峰值。|
|MaxBpsTime|Long|带宽峰值时刻。|
|TotalAccess|Long|访问次数。|

## 示例 {#section_hjq_zt1_bn6 .section}

请求示例

``` {#codeblock_60a_392_own}
http://cdn.aliyuncs.com?Action=DescribeTopDomainsByFlow
&StartTime=2016-03-01T04:00:00Z
&EndTime=2016-03-14T07:34:00Z
&Limit=5
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_y2c_1bq_i5e .language-json}
{
  "DomainCount": 68,
  "DomainOnlineCount": 68,
  "RequestId": "4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70",
  "EndTime": "2016-03-14T07:34:00Z",
  "TopDomains": {
    "TopDomain": [
      {
        "MaxBps": 22139626,
        "Rank": 1,
        "TrafficPercent": 30.64191989360235,
        "TotalTraffic": 2043859876683.9001,
        "TotalAccess": 107784230,
        "DomainName": "example1.com",
        "MaxBpsTime": 1457111400
      },
      {
        "MaxBps": 1008772351,
        "Rank": 2,
        "TrafficPercent": 25.936032624725815,
        "TotalTraffic": 1729970466149.2002,
        "TotalAccess": 3843128,
        "DomainName": "example2.com",
        "MaxBpsTime": 1457505600
      },
      {
        "MaxBps": 16046911,
        "Rank": 3,
        "TrafficPercent": 21.686305274906182,
        "TotalTraffic": 1446507574551.6,
        "TotalAccess": 547567,
        "DomainName": "example3.com",
        "MaxBpsTime": 1456897200
      },
      {
        "MaxBps": 15990893,
        "Rank": 4,
        "TrafficPercent": 21.261081185428147,
        "TotalTraffic": 1418144519687.5,
        "TotalAccess": 548380,
        "DomainName": "example4.com",
        "MaxBpsTime": 1457567700
      },
      {
        "MaxBps": 473599,
        "Rank": 5,
        "TrafficPercent": 0.4308743788055894,
        "TotalTraffic": 28739937242.500004,
        "TotalAccess": 152150,
        "DomainName": "example5.cn",
        "MaxBpsTime": 1457845800
      }
    ]
  },
  "StartTime": "2016-03-01T04:00:00Z"
}
```

## 错误码 {#section_i3a_d2d_bjn .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|InvalidStartTime.Malformed|Specified StartTime is malformed.|400|StartTime格式错误。|
|InvalidEndTime.Malformed|Specified EndTime is malformed.|400|EndTime格式错误。|
|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|400|EndTime和StartTime差值超过90天。|
|InvalidDomain.NotFound|The domain provided does not exist in our records.|404|域名不存在或不属于当前用户。|
|InvalidEndTime.Mismatch|Specified EndTime does not math the specified StartTime.|400|EndTime小于StartTime。|

