# DescribeDomainRegionData {#reference4167 .reference}

调用DescribeDomainRegionData获取加速域名天粒度的用户区域分布数据统计。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

## 调试 {#section_4tv_y4k_4mi .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainRegionData)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_cqf_lsk_2uh .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainRegionData。|
|DomainName|String|否|需要查询的加速域名，只支持一个域名，不写代表所有。|
|StartTime|String|否| -   获取数据起始时间点，UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   不写默认读取过去24小时数据。

 |
|EndTime|String|否| -   结束时间需大于起始时间，UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回参数 {#section_ysy_zqg_m6k .section}

|参数|类型|描述|
|--|--|--|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，固定值1天。|
|StartTime|DateTime|开始时间。|
|EndTim。e|DateTime|结束时间。|
|RegionDataInterval|UsageData\[\]|每个时间间隔的用户区域分布统计。|

UsageData

|参数|类型|描述|
|--|--|--|
|Value|RegionProportionData\[\]|各地区访问占比数据list。|

RegionProportionData

|参数|类型|描述|
|--|--|--|
|Region|String|地区信息。|
|Proportion|String|访问占比数据，如返回90即为90%。|
|RegionEname|String|地区英文名称。|
|AvgObjectSize|String|响应平均大小，单位：byte。|
|AvgResponseTime|String|平均响应时间，单位：毫秒。|
|Bps|String|带宽。|
|Qps|String|每秒查询率。|
|AvgResponseRate|String|平均响应速度，单位：byte/秒。|
|TotalBytes|String|总流量。|
|BytesProportion|String|总流量占比，如返回90即为90%。|
|TotalQuery|String|总请求次数。|

## 示例 {#section_cjs_wdb_dd1 .section}

请求示例

``` {#codeblock_sb2_0l0_4w1}
http://cdn.aliyuncs.com?Action=DescribeDomainRegionData&DomainName=example.com
&StartTime=2015-12-05T12:00:00Z
&EndTime=2015-12-07T12:00:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_hoq_tyt_qqk .language-json}
{
  "Value": {
    "RegionProportionData": [
      {
        "Bps": "380.9614285714286",
        "Proportion": "0.01155980271270037",
        "TotalBytes": "2400057",
        "BytesProportion": "0.003544181046236794",
        "TotalQuery": "3",
        "RegionEname": "",
        "Region": "日本",
        "AvgResponseRate": "154.3345765545624",
        "AvgObjectSize": "800019.0",
        "Qps": "5.9523809523809524E-5",
        "AvgResponseTime": "5183.666666666667"
      },
      {
        "Bps": "25110.431412698414",
        "Proportion": "0.31211467324291",
        "TotalBytes": "158195717",
        "BytesProportion": "0.23360872886644055",
        "TotalQuery": "81",
        "RegionEname": "xizang",
        "Region": "西藏自治区",
        "AvgResponseRate": "1397.1430909315718",
        "AvgObjectSize": "1953033.5543209878",
        "Qps": "0.0016071428571428571",
        "AvgResponseTime": "1397.8765432098764"
      },
      {
        "Bps": "40343.86242857143",
        "Proportion": "0.33908754623921084",
        "TotalBytes": "254166333",
        "BytesProportion": "0.37532921137846464",
        "TotalQuery": "88",
        "RegionEname": "chongqing",
        "Region": "重庆市",
        "AvgResponseRate": "787.8073097249128",
        "AvgObjectSize": "2888253.7875",
        "Qps": "0.001746031746031746",
        "AvgResponseTime": "3666.193181818182"
      }
    ]
  },
  "DataInterval": "86400",
  "RequestId": "2E5AD83F-BD7B-462E-8319-2E30E305519A",
  "DomainName": "example1.com",
  "EndTime": "2015-12-05T12:00:00Z",
  "StartTime": "2015-12-07T12:00:00Z"
}
			
```

## 错误码 {#section_b0z_x4y_nyv .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|InvalidStartTime.Malformed|Specified StartTime is malformed.|400|StartTime格式错误。|
|InvalidEndTime.Malformed|Specified EndTime is malformed.|400|EndTime格式错误。|
|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|400|EndTime和StartTime差值超过90天。|
|InvalidDomain.NotFound|The domain provided does not exist in our records.|404|域名不存在或不属于当前用户。|
|InvalidEndTime.Mismatch|Specified EndTime does not math the specified StartTime.|400|EndTime小于StartTime。|

