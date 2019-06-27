# DescribeDomainBpsData {#reference3780 .reference}

调用DescribeDomainBpsData获取加速域名的网络带宽监控数据，单位：bit/second。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   支持批量域名查询，多个域名用半角逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#section_zz3_ckb_1z7 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainBpsData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_wi6_txq_edt .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainBpsData。|
|DomainName|String|否| -   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（,）分隔。

 |
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
|LocationNameEn|String|否|区域英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有区域。|
|IspNameEn|String|否|运营商英文名，通过DescribeCdnRegionAndIsp接口获得，不传为所有运营商。|

## 返回参数 {#section_aav_k7k_2qh .section}

|名称|类型|描述|
|--|--|--|
|DomainName|String|加速域名信息。|
|DataInterval|String|需要补充时间间隔规则。每条记录的时间间隔，以秒为单位。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|LocationNameEn|String|区域英文名。|
|IspNameEn|String|运营商英文名。|
|BpsDataPerInterval|DataModule\[\]|每个时间间隔的网络带宽数据。|

DataModule

|名称|类型|描述|
|--|--|--|
|TimeStamp|String|时间片起始时刻。|
|Value|String|bps数据值，单位：bit/second。|
|DomesticValue|String|国内带宽。当按区域运营商查询时，此值为空。|
|OverseasValue|String|海外带宽。当按区域运营商查询时，此值为空。|
|HttpsValue|String|L1节点https的带宽数据值，单位：bit/second。|
|HttpsDomesticValue|String|L1节点https国内带宽。当按区域运营商查询时，此值为空。|
|HttpsOverseasValue|String|L1节点海外https带宽。当按区域运营商查询时，此值为空。|

## 示例 {#section_kzx_nx8_f1q .section}

请求示例

``` {#codeblock_1dg_q9t_71c}
http://cdn.aliyuncs.com?Action=DescribeDomainBpsData&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:05:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_9dl_nih_eh5 .language-json}
{
    "BpsDataPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2015-12-10T20:00:00Z",
                "Value": "11288111",
                "DomesticValue": "11286111",
                "OverseasValue": "2000",
                "HttpsValue": "11288111",
                "HttpsDomesticValue": "11286111",
                "HttpsOverseasValue": "2000"
            },
            {
                "TimeStamp": "2015-12-10T20:05:00Z",
                "Value": "12124821",
                "DomesticValue": "12112821",
                "OverseasValue": "12000",
                "HttpsValue": "11288111",
                "HttpsDomesticValue": "11286111",
                "HttpsOverseasValue": "2000"
            }
        ]
    },
    "DomainName": "example.com",
    "DataInterval": "300",
    "RequestId": "3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F",
    "StartTime": "2015-12-10T20:00:00Z",
    "EndTime": "2015-12-10T21:00:00Z"
}
```

## 错误码 {#section_cq0_b1c_i0l .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|InvalidStartTime.Malformed|Specified StartTime is malformed.|400|StartTime格式错误。|
|InvalidEndTime.Malformed|Specified EndTime is malformed.|400|EndTime格式错误。|
|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|400|EndTime和StartTime差值超过90天。|
|InvalidEndTime.Mismatch|Specified EndTime does not math the specified StartTime.|400|EndTime小于StartTime。|

