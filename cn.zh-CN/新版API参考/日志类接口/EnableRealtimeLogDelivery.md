# EnableRealtimeLogDelivery {#reference_rcf_msy_dgb .reference}

调用EnableRealtimeLogDelivery开启域名实时日志投递。

## 请求参数 {#section_obx_rly_dgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：EnableRealtimeLogDelivery。|
|Domain|String|是|暂停实时日志投递服务域名,支持多个，以`,`分隔。|

## 返回参数 {#section_vbx_rly_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|该条任务的请求ID。|

## 示例 {#section_ybx_rly_dgb .section}

请求示例

``` {#codeblock_6d9_ohh_xku}
https://cdn.aliyuncs.com?Action=EnableRealtimeLogDelivery&Domain=xxx.com
```

正常返回示例

`JSON`格式

``` {#codeblock_d9h_vrk_4gm}
{
    "RequestId": "9732E117-8A37-49FD-A36F-ABBB87556CA7",
}
```

## 错误码 {#section_zbx_rly_dgb .section}

|错误码|错误信息|HTTP 状态码|
|:--|:---|:-------|
|Unauthorized|没有开启实时投递授权|403|

