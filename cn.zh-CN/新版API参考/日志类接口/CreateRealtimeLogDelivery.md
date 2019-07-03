# CreateRealtimeLogDelivery {#reference_pwd_vgy_dgb .reference}

调用CreateRealtimeLogDelivery创建域名实时日志投递。

## 请求参数 {#section_t1g_ygy_dgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：CreateRealtimeLogDelivery。|
|Project|String|是|实时投递sls的ProjectName。|
|Logstore|String|是|实时投递sls的LogStoreName。|
|Region|String|是|实时投递sls的Region，例如上海：cn-shanghai。详情请参见[实时日志投递用户Region列表](../../../../cn.zh-CN/旧版API参考/附录.md#section_exc_kcz_dgb)。|
|Domain|String|是|开启实时日志投递服务域名。|

## 返回参数 {#section_uqf_jhy_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|该条任务的请求ID。|

## 示例 {#section_ifn_qhy_dgb .section}

请求示例

``` {#codeblock_jp8_uky_nf2}
https://cdn.aliyuncs.com?Action=CreateRealtimeLogDelivery?Domain=xxx.com&Project=test&Logstore=test&Region=test
```

正常返回示例

`JSON`格式

``` {#codeblock_jgo_123_ska}
{
    "RequestId": "F32C57AA-7BF8-49AE-A2CC-9F42390F5A19",
}
```

## 错误码 {#section_mmt_mhy_dgb .section}

|错误码|错误信息|HTTP 状态码|
|:--|:---|:-------|
|Unauthorized|没有开启实时投递授权|403|
|LogstoreNotExist|未找到对应Logstore 信息|404|

CDN所有API错误码，详情请参见[CDN错误码](https://error-center.aliyun.com/status/product/Cdn)。

