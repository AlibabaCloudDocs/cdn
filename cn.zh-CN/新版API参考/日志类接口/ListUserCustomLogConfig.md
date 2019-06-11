# ListUserCustomLogConfig {#reference3345 .reference}

调用ListUserCustomLogConfig获取用户下所有自定义日志配置信息。

## 请求参数 {#section_ubn_32b_mgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：ListUserCustomLogConfig。|

## 返回参数 {#section_fcn_32b_mgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|ConfigId|String|日志配置id。|

## 示例 {#section_zcn_32b_mgb .section}

请求示例

``` {#codeblock_qbg_orc_4q4}
https://cdn.aliyuncs.com?Action=ListUserCustomLogConfig<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_0zo_7e0_dwx}
{
    "RequestId": "95D5B69F-8AEC-419B-8F3A-612B35032B0D",
    "ConfigIds": {
        "ConfigId": [
            "c3bb2c78-2915-4d5a-b6a1-557789255555",
            "25473b84-d598-498e-b148-f23d0a255555",
            "1f1e6c6e-6701-4193-ae4d-54bf3e555555",
            ...
        ]
    }
}
```

## 错误码 {#section_sqb_hfb_mgb .section}

|错误码|错误信息|HTTP 状态码|描述|
|:--|:---|:-------|:-|
|ConfgIds.NotFound|You don't have any custom log config, please add first.|404|无自定义日志配置信息。|

