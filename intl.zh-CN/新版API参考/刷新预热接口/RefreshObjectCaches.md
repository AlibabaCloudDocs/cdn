# RefreshObjectCaches {#reference_srr_cyc_5db .reference}

调用RefreshObjectCaches刷新节点上的文件内容。刷新指定URL内容至Cache节点，支持URL批量刷新。

支持post请求，参数用form表单。

**说明：** 

-   刷新预热类接口包含RefreshObjectCaches 刷新接口和PushObjectCache预热接口。
-   同一个 ID 每天最多可提交2000条URL刷新和100个目录刷新。
-   每次请求最多只能提交1000条URL刷新。
-   每秒最多50次请求。

## 调试 {#section_0oy_s1r_m7t .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=RefreshObjectCaches)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_rxs_wnz_5db .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：RefreshObjectCaches。|
|ObjectPath|String|是|示例：`example.com/image/1.png`，多个URL之间需要用换行符`\n`或`\r\n`分隔。|
|ObjectType|String|否|刷新的类型， 其值可以为File或Directory。默认值：File。|

**说明：** 当ObjectType值为Directory时，ObjectPath结尾需加符号`/`。

## 返回参数 {#section_vkr_f4z_5db .section}

|参数|类型|描述|
|:-|:-|:-|
|RefreshTaskId|String|刷新返回的任务ID，多个任务ID用逗号（,）分隔。|
|RequestId|String|请求ID。|

## 示例 {#section_fb4_44z_5db .section}

请求示例

``` {#codeblock_fop_f2u_xd7}
https://cdn.aliyuncs.com?&Action=RefreshObjectCaches&ObjectPath=example.com/test.txt&ObjectType=File&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_hci_h6f_smj}
{
"RefreshTaskId":"704222904"，"RequestId":"D61E4801-EAFF-4A63-AAE1-FBF6CE1CFD1C"
}
```

`XML`格式

``` {#codeblock_jdg_6u4_w4n}
<?xml version="1.0" encoding="utf-8"?>，<RefreshObjectCachesResponse>，<RefreshTaskId>704225667</RefreshTaskId>，<RequestId>AB14769A-A5F2-4CCD-B85B-3368DFF63C0A</RequestId>，</RefreshObjectCachesResponse>
```

## 错误码 {#section_ppd_x5r_bgb .section}

|错误码|错误信息|HTTP 状态码|描述|
|---|----|--------|--|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain operate is not permitted.|403|非法域名, 无法操作。|
|OperationDenied|Your account does not open CDN service yet.|403|您未开通CDN服务。开通CDN服务请参见[开通CDN服务](../../../../intl.zh-CN/产品定价/开通CDN服务.md#)。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|InvalidDomain.Offline|The domain provided is offline.|404|域名已下线。|
|QuotaExceeded.Refresh|You’ve exceeded the prescribed refresh limits.|400|超出当日刷新限制。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中, 请您稍后再试。|
|InvalidDomain.Configure\_failed|Failed to configure the provided domain.|500|域名配置失败, 无法刷新。|
|MissingParameter|The input parameter ObjectPaththat is mandatory for processing this request is not supplied.|400|缺少ObjectPath参数。|
|InvalidObjectType.ValueNotSupported|The specified value of ObjectType is not supported.|400|ObjectType不支持。|
|InvalidObjectPath.Malformed|The specific value of parameter ObjectPathis malformed.|400|ObjectPath格式错误。|
|InvalidExtensiveDomain.ValueNotSupported|Extensive domain not supported.|400|不支持泛域名。|
|QuotaPerMinuteExceeded.Refresh|You’ve exceeded the prescribed refresh limits per minute.|400|超出每分钟刷新限制。|

