# DescribeCdnUserResourcePackage {#reference2380 .reference}

调用DescribeCdnUserResourcePackage查询CDN用户当前流量包。

## 调试 {#section_tso_p8t_q0x .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnUserResourcePackage)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_kez_pic_x1w .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeCdnUserResourcePackage。|

## 返回参数 {#section_gwr_ps8_dc7 .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|ResourcePackageInfos|\[ResourcePackageInfo\]|由ResourcePackageInfo组成的数组格式。|

数据类型ResourcePackageInfo

|名称|类型|描述|
|:-|:-|:-|
|CurrCapacity|String|实例当前剩余容量。|
|InitCapacity|String|资源包总量。|
|CommodityCode|String|资源包商品code。|
|DisplayName|String|模板对外展现名称。如：CDN流量包（国内版）。|
|InstanceId|String|实例ID。|
|Status|String|资源包状态。取值： -   valid：有效。
-   closed：无效。

 |
|StartTime|String|生效时间。|
|EndTime|String|失效时间。|

## 示例 {#section_wdn_7pi_cib .section}

请求示例

``` {#codeblock_a6p_5wo_mmg}
https://cdn.aliyuncs.com?&Action=DescribeCdnUserResourcePackage&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_ojs_amf_1a4}
{
    "ResourcePackageInfos": {
        "ResourcePackageInfo": [
            {
                "Status": "closed",
                "InstanceId": "FP-mkqgwsyui",
                "CommodityCode": "cdnflowbag",
                "InitCapacity": "10995116277760",
                "EndTime": "2017-01-30T08:00:00Z",
                "StartTime": "2016-01-30T03:40:06Z",
                "DisplayName": "CDN流量包（国内版）",
                "CurrCapacity": "10995089554629"
            },
            {
                "Status": "valid",
                "InstanceId": "FP-ilttxc23a",
                "CommodityCode": "cdnflowbag",
                "InitCapacity": "536870912000",
                "EndTime": "2018-07-01T08:00:00Z",
                "StartTime": "2017-07-01T01:26:41Z",
                "DisplayName": "CDN流量包（国内版）",
                "CurrCapacity": "0"
            },
            {
                "Status": "valid",
                "InstanceId": "CDNHTTPSBAG-cn-v0h0dnlq4000m9",
                "CommodityCode": "cdnhttpsbag",
                "InitCapacity": "10000000",
                "EndTime": "2018-12-06T08:00:00Z",
                "StartTime": "2017-12-05T19:10:58Z",
                "DisplayName": "CDN HTTPS请求数资源包",
                "CurrCapacity": "9999645"
            }
        ]
    },
    "RequestId": "84839536-2B7E-457D-9D8C-82E6C7D4E1A3"
}
```

