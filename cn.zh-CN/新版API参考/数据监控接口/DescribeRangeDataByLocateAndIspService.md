# DescribeRangeDataByLocateAndIspService {#reference_omx_vlp_yfb .reference}

调用DescribeRangeDataByLocateAndIspService获取加速域名的在某个时刻不同Locate和Isp上的带宽数据，单位：bit/second。

**说明：** 

-   不支持批量域名查询。
-   时间精确到5分钟粒度。

## 调试 {#section_oui_qop_85g .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeRangeDataByLocateAndIspService)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_ktd_j5x_dgb .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数取值：DescribeRangeDataByLocateAndIspService。|
|DomainNames|String|是|要查询的域名，不能为空。|
|LocationNames|String|否| -   需要查询目标区域列表，用`,`隔开，不能为空。
-   Location名通过DescribeCdnRegionAndIsp接口获得。

 |
|IspNames|String|否| -   需要查询目标Isp列表，用“,”隔开，不能为空。
-   ISP名通过DescribeCdnRegionAndIsp接口获得。

 |
|StartTime|String|是|开始时间。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。

 |
|EndTime|String|是|结束时间。 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回参数 {#section_rcw_p5x_dgb .section}

|名称|类型|描述|
|--|--|--|
|LocationAndISPInfoList|LocationAndISPInfo|返回区域运营商监控信息。|

LocationAndISPInfo

|名称|类型|描述|
|--|--|--|
|LocationAndISPJson|String|数据json串。|

## 示例 {#section_zd5_35x_dgb .section}

请求示例

``` {#codeblock_l38_8ww_jy9}
http://cdn.aliyuncs.com?Action=DescribeRangeDataByLocateAndIspService&DomainNames=example.com
&LocationNames=liaoning,guangxi
&IspNames=unicom,telecom
&StartTime=2016-08-01T22:00:00Z
&EndTime=2016-08-02T22:00:00Z
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_w36_bgc_669}
{
        "1472659200": {
            "天津市": {
                "电信": {
                    "bandwidth": 9889849.592, 
                    "pv": 5739, 
                    "hit_rate": 0, 
                    "http_codes": {
                        "200": 5675, 
                        "206": 5, 
                        "302": 5, 
                        "304": 45, 
                        "400": 1, 
                        "403": 8, 
                        "404": 0, 
                        "405": 0, 
                        "408": 0, 
                        "412": 0, 
                        "416": 0, 
                        "500": 0, 
                        "501": 0, 
                        "502": 0, 
                        "503": 0, 
                        "504": 0, 
                        "000": 0
                    }, 
                    "rt": 0
                },
                "联通":{},
                "移动":{}
            },
            "北京市": {
                "电信": {
                    "bandwidth": 9889849.592, 
                    "pv": 5739, 
                    "hit_rate": 0, 
                    "http_codes": {
                        "200": 5675, 
                        "206": 5, 
                        "302": 5, 
                        "304": 45, 
                        "400": 1, 
                        "403": 8, 
                        "404": 0, 
                        "405": 0, 
                        "408": 0, 
                        "412": 0, 
                        "416": 0, 
                        "500": 0, 
                        "501": 0, 
                        "502": 0, 
                        "503": 0, 
                        "504": 0, 
                        "000": 0
                    }, 
                    "rt": 0
                },
                "联通":{},
                "移动":{}
            }
        }, 
        "1472659500": {
            "天津市": {
                "电信": {
                    "bandwidth": 7024681.44, 
                    "pv": 5819, 
                    "hit_rate": 0, 
                    "http_codes": {
                        "200": 5716, 
                        "206": 11, 
                        "302": 3, 
                        "304": 72, 
                        "400": 1, 
                        "403": 16, 
                        "404": 0, 
                        "405": 0, 
                        "408": 0, 
                        "412": 0, 
                        "416": 0, 
                        "500": 0, 
                        "501": 0, 
                        "502": 0, 
                        "503": 0, 
                        "504": 0, 
                        "000": 0
                    }, 
                    "rt": 0
                },
                "联通":{},
                "移动":{}
            }
        }
    }, 
    "description": "Ok", 
    "retCode": 0
}
```

## 错误码 {#section_m42_s5x_dgb .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|InvalidDomainNames.Malformed|Specified domainNames is malformed.|400|域名不合法。|
|InvalidStartTime.Malformed|Specified StartTime is malformed.|400|开始时间错误。|
|InvalidEndTime.Malformed|Specified EndTime is malformed.|400|结束时间错误。|
|InvalidTime.ValueNotSupported|StartTime or EndTime is miss match.|400|开始时间和结束时间不匹配。|
|LossParams|DomainNames, StartTime and EndTime should not be empty or domainName have been registered.|400|缺少参数。|
|InvalidParams|Your parameters is invalid.|400|参数不合法。|

