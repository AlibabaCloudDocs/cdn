# StartCdnDomain {#reference1016 .reference}

调用StartCdnDomain启用状态为停用的加速域名，将 DomainStatus 变更为 Online。

**说明：** 域名对应账户如果由于欠费，或域名处于非法状态，无法正常调用该接口启用加速域名。

## 调试 {#section_pob_oy3_uor .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=StartCdnDomain)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_ex2_2nx_muw .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数 取值：StartCdnDomain。|
|DomainName|String|是|需要接入全站加速的域名。|

## 返回参数 {#section_ock_hlq_yot .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|该条任务请求ID。|

## 示例 {#section_mhj_prh_nun .section}

请求示例

``` {#codeblock_3dh_dkg_1t5}
http://cdn.aliyuncs.com?Action=StartCdnDomain&DomainName=example.com&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_6pz_j9d_tlc .language-json}
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码 {#section_q7w_cr7_d94 .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|IllegalOperation|Illegal domain operate is not permitted.|403|没有权限执行当前操作。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中，请稍后再试。|

