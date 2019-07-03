# ModifyCdnService {#reference_llj_4bt_vdb .reference}

调用ModifyCdnService变更CDN服务的计费类型。

计费类型：

-   按峰值带宽计费。
-   按使用流量计费。

**说明：** 

-   需先开通CDN服务才可执行此操作。
-   变更计费类型，次日00:00生效，多次变更以最新提交的为准。

## 调试 {#section_3t7_wdr_tyf .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=ModifyCdnService)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_udw_bqn_cgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：ModifyCdnService。|
|InternetChargeType|String|是|开通服务的计费类型：按流量、按带宽峰值。用户必须指定类型：按流量PayByTraffic，按带宽峰值PayByBandwidth。|

## 返回参数 {#section_zp9_g9h_5rw .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_sz4_ctt_vdb .section}

请求示例

``` {#codeblock_jt2_kxs_skt}
https://cdn.aliyuncs.com?&Action=ModifyCdnService&InternetChargeType=PayByTraffic&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_1si_5fc_4nc}
{
"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

## 错误码 {#section_rr2_nqn_cgb .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|OperationDenied|Your account does not open CDN service yet.|403|您的账户未开通CDN服务。|
|InvalidParameter|The specified value of parameter parameter name is not valid.|400|参数parameter name无效。|
|InsufficientBalance|Your account does not have enough balance.|400|您的账户余额不足。|
|Forbidden.NotVerified|Your account is not verified yet.|403|您的账户未进行验证。|

CDN所有API错误码，详情请参见[CDN错误码](https://error-center.aliyun.com/status/product/Cdn)。

