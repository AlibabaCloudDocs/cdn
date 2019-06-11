# DescribeDomainRealTimeByteHitRateData {#reference1684 .reference}

调用DescribeDomainRealTimeByteHitRateData获取域名1分钟粒度字节命中率数据。

**说明：** 

-   可以查询7天内的数据，单次查询StartTime和EndTime跨度不能超过24小时。
-   由于存在多域名合并存储的情况，可能会导致命中率数据不准确，具体情况以配置为准。

## 调试 {#section_xyt_rg1_4ov .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainRealTimeByteHitRateData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_7tb_4en_80v .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainRealTimeByteHitRateData。|
|DomainName|String|是|域名。|
|StartTime|String|否|起始时间。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从EndTime起一小时内的数据。

 |
|EndTime|String|否|结束时间。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从开始时间起一小时内的数据。

 |

## 返回参数 {#section_3j7_y2x_wk2 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求Id。|
|TimeStamp|String|数据时间戳。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|ByteHitRate|Float|字节命中率数据。|

## 示例 {#section_a65_dw0_1vp .section}

请求示例

``` {#codeblock_l50_om8_gx7}
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeByteHitRateData&DomainName=example.com&EndTime=2018-01-02T11%3A05%3A37Z<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_r7v_jcj_lap .language-json}
{
   "Data":{
      "ByteHitRateModel":[
         {
            "TimeStamp":"2018-01-02T11:26:00Z",
            "ByteHitRate":0.8956940476262277
         },
         {
            "TimeStamp":"2018-01-02T11:25:00Z",
            "ByteHitRate":0.8429129920796812
         }
      ]
   },
   "RequestId":"70A26B11-3673-479C-AEA8-E03FC5D3496D"
}
			
```

## 错误码 {#section_6im_pdx_mvh .section}

|错误码|错误信息|HTTP 返回码|描述|
|---|----|--------|--|
|InvalidTime.Malformed|时间参数格式不正确|400|时间参数不正确。|
|InvalidDomainName.Malformed|域名参数未提供或找不到域名|400|域名参数不正确。|

