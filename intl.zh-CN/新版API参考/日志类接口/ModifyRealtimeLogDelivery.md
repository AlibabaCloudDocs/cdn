# ModifyRealtimeLogDelivery {#reference_d1h_kwd_2gb .reference}

更改域名实时日志投递\(一个域名同时仅支持投递单个logstore\)。

## 请求参数 {#section_obx_rly_dgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：ModifyRealtimeLogDelivery。|
|Domain|String|是|修改实时日志投递的域名|
|Project|String|是|实时投递sls的ProjectName|
|Logstore|String|是|实时投递sls的LogStoreName|
|Region|String|是|实时投递sls的Region，如上海:cn-shanghai。详情请参见 [附录](../../../../intl.zh-CN/旧版API参考/附录.md#table_nnm_mcz_dgb)。|

## 返回参数 {#section_vbx_rly_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|RequestId|

## 示例 {#section_ybx_rly_dgb .section}

请求示例

```
https://cdn.aliyuncs.com?Action=ModifyRealtimeLogDelivery&Domain=xxx.com&Project=test&Logstore=test&Region=test
```

返回示例

```
{
    "RequestId": "9732E117-8A37-49FD-A36F-ABBB87556CA7",
}
```

## 错误码 {#section_zbx_rly_dgb .section}

|错误码|错误信息|HTTP 状态码|
|:--|:---|:-------|
|LogstoreNotExist|未找到对应Logstore 信息|403|
|Domain.NotFound|域名未开通实时日志投递服务|404|

