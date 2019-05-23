# DescribeDomainISPData {#reference4167 .reference}

调用DescribeDomainISPData获取加速域名天粒度的 用户运营商分布数据统计。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。

**说明：** 

-   只支持一个域名或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 请求参数 {#section_dnw_t42_tzn .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainISPData。|
|DomainName|String|否|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。|
|StartTime|String|否| -   获取数据起始时间点，UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   不写默认读取过去24小时数据。

 |
|EndTime|String|否| -   结束时间需大于起始时间，UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回参数 {#section_cky_xl8_fb8 .section}

|名称|类型|描述|
|--|--|--|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，固定值1天。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|ISPDataInterval|UsageData\[\]|每个时间间隔的用户区域分布统计。|

UsageData

|名称|类型|描述|
|--|--|--|
|Value|ISPProportionData\[\]|各运营商访问占比数据list|

ISPProportionData

|名称|类型|描述|
|--|--|--|
|ISP|String|运营商信息。|
|Proportion|String|占比使用数据。|
|IspEname|String|运营商英文名称。|
|AvgObjectSize|String|响应平均大小，单位：byte。|
|AvgResponseTime|String|平均响应时间，单位：毫秒。|
|Bps|String|带宽。|
|ByteHitRate|String|字节命中率。|
|Qps|String|每秒查询率。|
|ReqErrRate|String|请求错误率。|
|ReqHitRate|String|请求命中率。|
|AvgResponseRate|String|平均响应速度，单位：byte/毫秒。|
|TotalBytes|String|总流量。|
|BytesProportion|String|总流量占比。|
|TotalQuery|String|总请求次数。|

## 示例 {#section_wgl_8es_kas .section}

请求示例

``` {#codeblock_z4l_30t_6sw}
http://cdn.aliyuncs.com?Action=DescribeDomainISPData&DomainName=example.com
&StartTime=2015-12-05T00:00:00Z
&EndTime=2015-12-07T00:00:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_ld0_b4p_6ov .language-json}
{
  "Value": {
    "ISPProportionData": [
      {
        "ByteHitRate": "100.0",
        "TotalQuery": "1",
        "Bps": "1311.4601296296296",
        "Proportion": "0.004509176173513099",
        "AvgResponseRate": "88.92594866772144",
        "IspEname": "alibaba",
        "AvgObjectSize": "7081884.7",
        "ISP": "阿里巴巴",
        "ReqErrRate": "0.0",
        "Qps": "2.3148148148148147E-5",
        "AvgResponseTime": "79638.0",
        "ReqHitRate": "100.0",
        "TotalBytes": "7081884",
        "BytesProportion": "0.012220518530445479"
      },
      {
        "ByteHitRate": "100.0",
        "TotalQuery": "3",
        "Bps": "444.455",
        "Proportion": "0.013527528520539298",
        "AvgResponseRate": "154.3345765545624",
        "IspEname": "overseas",
        "AvgObjectSize": "800019.0",
        "ISP": "海外ISP",
        "ReqErrRate": "0.0",
        "Qps": "6.944444444444444E-5",
        "AvgResponseTime": "5183.666666666667",
        "ReqHitRate": "100.0",
        "TotalBytes": "2400057",
        "BytesProportion": "0.004141544558417533"
      },
      {
        "ByteHitRate": "100.0",
        "TotalQuery": "82",
        "Bps": "45838.64816666667",
        "Proportion": "0.3697524462280741",
        "AvgResponseRate": "1025.5028528460102",
        "IspEname": "drpeng",
        "AvgObjectSize": "3018642.684146342",
        "ISP": "鹏博士",
        "ReqErrRate": "0.0",
        "Qps": "0.0018981481481481482",
        "AvgResponseTime": "2943.5731707317073",
        "ReqHitRate": "100.0",
        "TotalBytes": "247528700",
        "BytesProportion": "0.42713616424581613"
      },
      {
        "ByteHitRate": "99.99999999999999",
        "TotalQuery": "114",
        "Bps": "65933.51396296297",
        "Proportion": "0.5140460837804933",
        "AvgResponseRate": "484.6396117340071",
        "IspEname": "cernet",
        "AvgObjectSize": "3123166.4508771934",
        "ISP": "教育网",
        "ReqErrRate": "0.0",
        "Qps": "0.002638888888888889",
        "AvgResponseTime": "6444.30701754386",
        "ReqHitRate": "100.0",
        "TotalBytes": "356040975",
        "BytesProportion": "0.6143852267848392"
      },
      {
        "ByteHitRate": "100.0",
        "TotalQuery": "207",
        "Bps": "81128.73735185186",
        "Proportion": "0.9333994679172115",
        "AvgResponseRate": "752.2096624205244",
        "IspEname": "tietong",
        "AvgObjectSize": "2116401.843961353",
        "ISP": "铁通",
        "ReqErrRate": "0.0",
        "Qps": "0.004791666666666666",
        "AvgResponseTime": "2813.5797101449275",
        "ReqHitRate": "100.0",
        "TotalBytes": "438095181",
        "BytesProportion": "0.7559781771177001"
      },
      {
        "ByteHitRate": "100.00000000000001",
        "TotalQuery": "256",
        "Bps": "129137.37100000001",
        "Proportion": "1.1543491004193533",
        "AvgResponseRate": "321.5924922592767",
        "IspEname": "other",
        "AvgObjectSize": "2723991.4195312504",
        "ISP": "其他",
        "ReqErrRate": "0.0",
        "Qps": "0.005925925925925926",
        "AvgResponseTime": "8470.3203125",
        "ReqHitRate": "100.0",
        "TotalBytes": "697341803",
        "BytesProportion": "1.2033348171432345"
      },
      {
        "ByteHitRate": "99.14745652563326",
        "TotalQuery": "2866",
        "Bps": "879955.1972037038",
        "Proportion": "12.923298913288543",
        "AvgResponseRate": "1004.5513789924338",
        "IspEname": "mobile",
        "AvgObjectSize": "1657975.598360084",
        "ISP": "移动",
        "ReqErrRate": "0.0",
        "Qps": "0.06634259259259259",
        "AvgResponseTime": "1650.463712491277",
        "ReqHitRate": "97.3831123517097",
        "TotalBytes": "4751758064",
        "BytesProportion": "8.19964599032574"
      },
      {
        "ByteHitRate": "99.99981717005271",
        "TotalQuery": "6534",
        "Bps": "3194660.60262963",
        "Proportion": "29.46295711773459",
        "AvgResponseRate": "1171.525957981939",
        "IspEname": "unicom",
        "AvgObjectSize": "2640215.374074074",
        "ISP": "联通",
        "ReqErrRate": "0.0",
        "Qps": "0.15125",
        "AvgResponseTime": "2253.6550352004897",
        "ReqHitRate": "99.96939087848179",
        "TotalBytes": "17251167254",
        "BytesProportion": "29.768658772680293"
      },
      {
        "ByteHitRate": "99.99968869093071",
        "TotalQuery": "12114",
        "Bps": "6333214.260796296",
        "Proportion": "54.62416016593768",
        "AvgResponseRate": "984.184264638081",
        "IspEname": "telecom",
        "AvgObjectSize": "2823126.71357933",
        "ISP": "电信",
        "ReqErrRate": "0.0",
        "Qps": "0.28041666666666665",
        "AvgResponseTime": "2868.494056463596",
        "ReqHitRate": "99.97523526498266",
        "TotalBytes": "34199357008",
        "BytesProportion": "59.01449878861353"
      }
    ]
  },
  "DataInterval": "86400",
  "RequestId": "DE81639B-DAC1-4C76-AB72-F34B836837D5",
  "DomainName": "example1.com",
  "EndTime": "2016-03-14T00:00:00Z",
  "StartTime": "2016-03-13T00:00:00Z"
}
			
```

## 错误码 {#section_il3_dwb_5ir .section}

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
|InvalidStartTime.Malformed|Specified start time is malformed.|400|StartTime格式错误。|
|InvalidEndTime.Malformed|Specified end time is malformed.|400|EndTime格式错误。|
|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|400|EndTime小于StartTime。|
|InvalidStartTime.ValueNotSupported|Specified end time does not math the specified start time.|400|EndTime和StartTime差值超过90天。|

