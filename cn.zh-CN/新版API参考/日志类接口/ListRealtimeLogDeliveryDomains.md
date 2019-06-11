# ListRealtimeLogDeliveryDomains {#reference_ysq_rsy_dgb .reference}

调用ListRealtimeLogDeliveryDomains查询实时日志投递服务下所有域名。

## 请求参数 {#section_obx_rly_dgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：ListRealtimeLogDeliveryDomains。|
|Project|String|是|实时投递sls的ProjectName。|
|Logstore|String|是|实时投递sls的LogStoreName。|
|Region|String|是|实时投递sls的Region，例如上海：cn-shanghai。详情请参见[实时日志投递用户Region列表](../../../../intl.zh-CN/旧版API参考/附录.md#section_exc_kcz_dgb)。|

## 返回参数 {#section_vbx_rly_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|DomainName|String|域名。|
|Status|String|状态。 -   online：正在服务。
-   offline：停止服务。

 |

## 示例 {#section_ybx_rly_dgb .section}

请求示例

``` {#codeblock_83o_j8o_56w}
https://cdn.aliyuncs.com?Action=ListRealtimeLogDeliveryDomains&Project=test&Logstore=test&Region=test
```

正常返回示例

`JSON`格式

``` {#codeblock_2n1_q04_ete}
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

