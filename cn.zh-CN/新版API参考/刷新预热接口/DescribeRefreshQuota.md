# DescribeRefreshQuota {#reference1270 .reference}

调用DescribeRefreshQuota查询刷新、预热URL及目录的最大限制数量，以及当日剩余刷新、预热URL及目录的次数。

**说明：** 刷新预热类接口包含RefreshObjectCaches 刷新接口和PushObjectCache 预热接口。

## 调试 {#section_d1i_7pl_5au .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeRefreshQuota)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_o0i_gyr_18p .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeRefreshQuota。|

## 返回参数 {#section_6ln_5bx_pxm .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|UrlQuota|String|当天url刷新数量上限。|
|DirQuota|String|当天路径刷新数量上限。|
|UrlRemain|String|当天剩余url刷新数量。|
|DirRemain|String|当天剩余目录刷新数量。|
|PreloadQuota|String|当天预热数量上限。|
|PreloadRemain|String|当天剩余预热数量。|

## 示例 {#section_um3_web_d8x .section}

请求示例

``` {#codeblock_z4x_e2q_s17}
http://cdn.aliyuncs.com?Action=DescribeRefreshQuota
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_hyl_pwx_p08 .language-json}
{
    "DirQuota": "100",
    "DirRemain": "99",
    "RequestId": "42E0554B-80F4-4921-AED6-ACFB22CAAAD0",
    "UrlQuota": "2000",
    "UrlRemain": "1996",
    "PreloadQuota": "500",
    "PreloadRemain": "400"
}
```

## 错误码 {#section_qox_6sx_qoq .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|

