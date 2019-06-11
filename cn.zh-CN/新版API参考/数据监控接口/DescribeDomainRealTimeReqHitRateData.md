# DescribeDomainRealTimeReqHitRateData {#reference1612 .reference}

调用DescribeDomainRealTimeReqHitRateData获取域名1分钟粒度请求命中率数据。

**说明：** 

-   可以查询7天内的数据，单次查询StartTime和EndTime跨度不能超过24小时。
-   如果StartTime和EndTime均未指定，默认返回当前时间起一小时内的数据。
-   由于存在多域名合并存储的情况，可能会导致命中率数据不准确，具体情况以配置为准。

## 调试 {#section_jcp_2qe_dyh .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainRealTimeReqHitRateData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_0as_nfw_ec6 .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainRealTimeReqHitRateData。|
|DomainName|String|是|域名。|
|StartTime|String|是|起始时间。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|EndTime|String|是|结束时间。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |

## 返回参数 {#section_znz_pgg_aev .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求Id。|
|TimeStamp|String|数据时间戳。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|ReqHitRate|Float|请求命中率数据。|

## 示例 {#section_2fu_d9u_671 .section}

请求示例

``` {#codeblock_m9p_v9t_yli}
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeReqHitRateData&DomainName=example.com&EndTime=2018-01-02T11%3A05%3A37Z<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_xrf_vh6_9vn .language-json}
{
   "Data":{
      "ReqHitRateModel":[
         {
            "TimeStamp":"2018-01-02T11:26:00Z",
            "ReqHitRate":0.8956940476262277
         },
         {
            "TimeStamp":"2018-01-02T11:25:00Z",
            "ReqHitRate":0.8429129920796812
         }
      ]
   },
   "RequestId":"70A26B11-3673-479C-AEA8-E03FC5D3496D"
}
```

## 错误码 {#section_wfm_ior_p0r .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|InvalidTime.Malformed|时间参数格式不正确|400|时间参数不正确。|
|InvalidDomainName.Malformed|域名参数未提供或找不到域名|400|域名参数不正确。|

