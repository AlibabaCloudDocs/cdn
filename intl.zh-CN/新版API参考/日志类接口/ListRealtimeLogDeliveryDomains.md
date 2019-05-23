# ListRealtimeLogDeliveryDomains {#reference_ysq_rsy_dgb .reference}

查询实时日志投递服务下所有域名。

## 请求参数 {#section_obx_rly_dgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：ListRealtimeLogDeliveryDomains。|
|Project|String|是|实时投递sls的ProjectName|
|Logstore| |是|实时投递sls的LogStoreName|
|Region| |是|实时投递sls的Region，如上海:cn-shanghai。详情请参见 [附录](../../../../intl.zh-CN/旧版API参考/附录.md#table_nnm_mcz_dgb)。|

## 返回参数 {#section_vbx_rly_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|DomainName|String|域名|
|Status|String|状态。-   online：正在服务
-   offline：停止服务

|

## 示例 {#section_ybx_rly_dgb .section}

请求示例

```
https://cdn.aliyuncs.com?Action=ListRealtimeLogDeliveryDomains&Project=test&Logstore=test&Region=test
```

返回示例

```
{
    "Content":{
        "Domains":[
            {   
                "DomainName":"a.xxx.com",
                "Status":"online"
            },
            {   
                "DomainName":"b.xxx.com",
                "Status":"offline"
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
|LogstoreNotExist|未找到对应Logstore 信息|404|

