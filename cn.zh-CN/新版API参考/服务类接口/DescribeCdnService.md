# DescribeCdnService {#reference1467 .reference}

调用DescribeCdnService查询CDN服务状态。包括：当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等。

## 调试 {#section_pj0_ii3_yns .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnService)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_ufl_khi_gag .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeCdnService。|

## 返回参数 {#section_9ri_nz8_jwx .section}

|名称|类型|描述|
|:-|:-|:-|
|InternetChargeType|String|计费类型。包括： -   PayByTraffic
-   PayByBandwidth
-   PayByBandwidth95
-   PayByBandwidth\_monthavg
-   PayByBandwidth\_month4th
-   PayByBandwidth\_monthday95avg
-   PayByBandwidth\_nighthalf95

 |
|OpeningTime|String|开通服务时间，ISO 8601时间格式。|
|ChangingChargeType|String|下次生效的计费类型。包括： -   PayByTraffic
-   PayByBandwidth
-   PayByBandwidth95
-   PayByBandwidth\_monthavg
-   PayByBandwidth\_month4th
-   PayByBandwidth\_monthday95avg
-   PayByBandwidth\_nighthalf95

 |
|ChangingAffectTime|Date|GMT时间。|
|OperationLocks|Struct|业务锁定状态。例如：financial（欠费）、安全等。|

## 示例 {#section_x8h_ibr_kv0 .section}

请求示例

``` {#codeblock_9ka_zo6_fav}
https://cdn.aliyuncs.com?&Action=DescribeCdnService&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_6kd_vix_59f}
{
    "ChangingAffectTime" : "2014-11-27T16:00:00Z",
    "ChangingChargeType" : "PayByBandwidth",
    "InternetChargeType" : "PayByTraffic",
    "OpeningTime" : "2014-02-28T13:11:49Z",
    "OperationLocks" : {
        "LockReason" : []
    },
    "RequestId" : "BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23"
}
```

## 错误码 {#section_8sa_fsl_xe8 .section}

|错误代码|错误信息|HTTP状态码|描述|
|:---|:---|:------|:-|
|OperationDenied|Your account does not open CDN service yet|403|您的账户未开通CDN服务。|

