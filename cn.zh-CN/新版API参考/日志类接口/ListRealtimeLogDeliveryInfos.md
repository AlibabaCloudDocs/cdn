# ListRealtimeLogDeliveryInfos {#reference_mhl_2ty_dgb .reference}

调用ListRealtimeLogDeliveryInfos查询所有实时日志投递服务信息。

## 请求参数 {#section_obx_rly_dgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：ListRealtimeLogDeliveryInfos。|

## 返回参数 {#section_vbx_rly_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|Project|String|实时投递sls的ProjectName。|
|Logstore|String|实时投递sls的LogstoreName。|
|Region|String|实时投递sls的Region，例如上海：cn-shanghai。详情请参见[实时日志投递用户Region列表](../../../../intl.zh-CN/旧版API参考/附录.md#section_exc_kcz_dgb)。|

## 示例 {#section_ybx_rly_dgb .section}

请求示例

``` {#codeblock_xv7_qfw_ysj}
https://cdn.aliyuncs.com?Action=ListRealtimeLogDeliveryInfos
```

正常返回示例

`JSON`格式

``` {#codeblock_h7l_e1e_0ao}
{
    "Content":{
        "RealtimeLogDeliveryInfos":[
            {   
                "Project":"test",
                "Logstore":"test",
                "Region":"cn-shanghai"
            },
            {   
                "Project":"test1",
                "Logstore":"test2",
                "Region":"cn-shanghai"
            }
            ...
        ]
    },
    "RequestId":"95D5B69F-8AEC-419B-8F3A-612B35032B0D"
}
```

## 错误码 {#section_zbx_rly_dgb .section}

|错误码|错误信息|HTTP 状态码|
|:--|:---|:-------|
|Unauthorized|没有开启实时投递授权|403|

