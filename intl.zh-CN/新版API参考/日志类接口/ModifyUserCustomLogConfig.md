# ModifyUserCustomLogConfig {#reference3345 .reference}

调用ModifyUserCustomLogConfig修改用户下自定义日志配置信息。

## 调试 {#section_q6i_53p_xuv .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=ModifyUserCustomLogConfig)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_ubn_32b_mgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：ModifyUserCustomLogConfig。|
|ConfigId|String|是|日志配置ID。|
|Tag|String|是|日志配置tag信息\(不超过256个字符\)。|

## 返回参数 {#section_fcn_32b_mgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestID|String|该条任务请求ID。|

## 示例 {#section_zcn_32b_mgb .section}

请求示例

``` {#codeblock_5cz_h7p_cvc}
https://cdn.aliyuncs.com?Action=ModifyUserCustomLogConfig&Tag=xxxx<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_rln_375_vm3}
{
"RequestId":"CEC1492F-EB71-4481-94CF-34BA007DC8E1"
}
```

## 错误码 {#section_sqb_hfb_mgb .section}

|错误码|错误信息|HTTP 状态码|描述|
|:--|:---|:-------|:-|
|InvalidConfigId|The configId provided does not belong to you.|404|配置信息不属于当前用户或不存在。|
|InvalidTag|Tag should be less than 256 characters.|403|Tag信息最多256个字符。|

