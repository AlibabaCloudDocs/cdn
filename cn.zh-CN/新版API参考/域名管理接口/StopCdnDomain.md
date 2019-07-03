# StopCdnDomain {#reference1012 .reference}

调用StopCdnDomain停用某个加速域名，将DomainStatus变更为Offline。

**说明：** 停用该加速域名后，该条加速域名信息仍保留，针对加速域名的请求系统将做自动回源处理。

## 调试 {#section_dup_n5s_10t .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=StopCdnDomain)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_sp1_rjl_2rl .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数 取值：StopCdnDomain。|
|DomainName|String|是|需要接入全站加速的域名。|

## 返回参数 {#section_izj_qq3_6we .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|该条任务请求ID。|

## 示例 {#section_out_inz_or1 .section}

请求示例

``` {#codeblock_kld_azb_t7k}
http://cdn.aliyuncs.com?Action=StopCdnDomain&DomainName=example.com&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_7bn_9vw_iwn .language-json}
{
  "RequestId": "324AEFFF-308C-4DA7-8CD3-01B277B98F28"
}
```

## 错误码 {#section_chk_3a8_bvz .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|IllegalOperation|Illegal domain operate is not permitted.|403|没有权限执行当前操作。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中, 请稍后再试。|

CDN所有API错误码，详情请参见[CDN错误码](https://error-center.aliyun.com/status/product/Cdn)。

