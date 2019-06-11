# DescribeCdnDomainConfigs {#reference_90924_zh .reference}

调用DescribeCdnDomainConfigs查询域名配置，一次可查询多个功能配置。

## 调试 {#section_cba_0ou_0t8 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnDomainConfigs)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_vju_2nt_rz5 .section}

|参数|类型|是否必选|说明|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeCdnDomainConfigs。|
|DomainName|String|是|您的加速域名。|
|FunctionNames|String|否|功能列表名称，用`,`分隔。|

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

## 返回参数 {#section_y8r_99j_vd4 .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|该条任务请求Id。|
|DomainConfigs|DomainConfig\[\]|域名配置。|

DomainConfig

|名称|类型|描述|
|--|--|--|
|FunctionName|String|function名称。|
|Status|String|状态，包括success、testing、failed、configuring。|
|ConfigId|String|配置id。|
|FunctionArgs|FunctionArg\[\]|各个function。|

FunctionArg

|名称|类型|描述|
|--|--|--|
|ArgName|String|配置名称。|
|ArgValue|String|配置值。|

## 示例 {#section_mjv_zfd_cfb .section}

请求示例

``` {#codeblock_ovz_9cg_uc8}
http://cdn.aliyuncs.com/?Action=DescribeCdnDomainConfigs
&DomainName=www.xxx.org.cn
&FunctionNames=aliauth
&<公共请求参数>   
```

正常返回示例

`JSON`格式

``` {#codeblock_0m3_q7x_t04 .language-json}
{
    "RequestId": "C80705BF-0F76-41FA-BAD1-5B59296A4E59",
    "DomainConfigs": {
        "DomainConfig": [
            {
                "Status": "success",
                "FunctionArgs": {
                    "FunctionArg": [
                        {
                            "ArgName": "auth_type",
                            "ArgValue": "req_auth"
                        },
                        {
                            "ArgName": "ali_auth_dual",
                            "ArgValue": "on"
                        }
                    ]
                },
                "ConfigId": 6295,
                "FunctionName": "aliauth"
            }
        ]
    }
}        
```

## 错误码 {#section_wil_psl_xfn .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|InvalidFunctionName.ValueNotSupported|FunctionName %s is not supported.|400|不支持的FunctionName %s\(%s为具体功能名\)。|

