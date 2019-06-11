# DescribeDomainRealtimeLogDelivery {#reference_pwd_vgy_dgb .reference}

调用DescribeDomainRealtimeLogDelivery查询域名实时日志投递信息。

## 请求参数 {#section_t1g_ygy_dgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainRealtimeLogDelivery。|
|Domain|String|是|开启实时日志投递服务域名。|

## 返回参数 {#section_uqf_jhy_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求Id。|
|Status|String|域名实时投递状态。|
|Project|String|实时投递sls的ProjectName。|
|Logstore|String|实时投递sls的LogStoreName。|
|Region|String|实时投递sls的Region，例如上海：cn-shanghai。详情请参见[实时日志投递用户Region列表](../../../../intl.zh-CN/旧版API参考/附录.md#section_exc_kcz_dgb)。|

## 示例 {#section_ifn_qhy_dgb .section}

请求示例

``` {#codeblock_4sh_lmv_rr7}
https://cdn.aliyuncs.com?Action=DescribeDomainRealtimeLogDelivery&Domain=xxx.com
```

正常返回示例

`JSON`格式

``` {#codeblock_1et_mx3_730}
{
    "Project":"test",
    "Logstore":"test",
    "Region":"cn-shanghai",
    "Status":"online",
    "RequestId":"2F8F3852-912F-42AC-80EB-F1CF4284DE93"
}
```

## 错误码 {#section_mmt_mhy_dgb .section}

|错误码|错误信息|HTTP 状态码|
|:--|:---|:-------|
|Domain.NotFound|域名未开通实时日志投递服务|404|

