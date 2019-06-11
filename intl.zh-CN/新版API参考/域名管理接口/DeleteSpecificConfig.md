# DeleteSpecificConfig {#reference_zdq_bb5_jgb .reference}

调用DeleteSpecificConfig删除加速域名的配置。

## 调试 {#section_bbg_6kn_s7n .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DeleteSpecificConfig)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_hh1_gb5_jgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DeleteSpecificConfig。|
|DomainName|String|是|您的加速域名。|
|ConfigId|String|是|配置ID，多个用`,`隔开。|

功能说明

|可选项|说明|
|---|--|
|referer\_white\_list\_set|refer白名单。|
|referer\_black\_list\_set|refer黑名单。|
|filetype\_based\_ttl\_set|文件过期时间设置。|
|path\_based\_ttl\_set|目录过期时间设置。|
|cc\_defense|防CC攻击。|
|oss\_auth|OSS鉴权Bucket。|
|ip\_black\_list\_set|IP黑名单。|
|ip\_white\_list\_set|IP白名单。|
|error\_page|错误页面重定向。|
|tesla|页面优化加速。|
|set\_req\_header|修改回源自定义头。|
|set\_req\_host\_header|修改回源host头。|
|set\_hashkey\_args|忽略url参数。|
|aliauth|阿里鉴权。|
|set\_resp\_header|设置响应头（浏览器端可见）。|
|video\_seek|视频切片拖拽开关。|
|range|Range请求功能。|
|gzip|页面Gzip优化。|
|https\_force|强制HTTPS跳转。|
|http\_force|强制HTTP跳转。|
|alilive|视频直播配置。|
|forward\_scheme|自适应回源。|
|tmd\_signature|TMD自定义规则。|

## 返回参数 {#section_nh1_gb5_jgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestID|String|该条任务请求ID。|

## 示例 {#section_sh1_gb5_jgb .section}

请求示例

``` {#codeblock_x2y_wda_78i}
http://cdn.aliyuncs.com/?Action=DeleteSpecificConfig
&DomainName=example.com
&ConfigId=2317
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_7vd_a86_0jb .language-json}
{
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 {#section_tnm_4b5_jgb .section}

|错误代码|错误信息|Http 状态码|描述|
|:---|:---|:-------|:-|
|MissingParameter|The specified value of parameter DomainName can not be empty.|400|DomainName为空。|
|MissingParameter|The specified value of parameter ConfigId can not be empty.|400|ConfigId为空。|
|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|400|FunctionName不支持。|

