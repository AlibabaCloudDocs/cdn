# BatchSetCdnDomainConfig {#reference4941 .reference}

调用BatchSetCdnDomainConfig进行域名批量配置。

## 调试 {#section_qp2_4ds_2vx .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=BatchSetCdnDomainConfig)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_s7z_e8e_qua .section}

|参数|类型|是否必选|说明|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：BatchSetCdnDomainConfig。|
|DomainNames|String|是|您的加速域名，多个用逗号`,`分隔。|
|Functions|Json|是|功能列表。|

Functions格式

-   ``` {#codeblock_fpn_nhh_jji}
[{"functionArgs":[{"argName":"domain_name","argValue":"api.hellodtworld.com"}],"functionName":"set_req_host_header"}]
```

-   某些功能，如filetype\_based\_ttl\_set，可以设置多条纪录，当需要更新其中某条纪录时，可通过该条纪录的configId来指定。

    ``` {#codeblock_haa_nzp_x3v}
    [{"functionArgs":[{"argName":"file_type","argValue":"jpg"},{"argName":"ttl","argValue":"18"},{"argName":"weight","argValue":"30"}],"functionName":"filetype_based_ttl_set","configId":5068995}]
    ```


功能说明

所有参数值均按照字符串类型处理。

|名称|描述|参数|
|:-|:-|:-|
|referer\_white\_list\_set|refer白名单| -   refer\_domain\_allow\_list：白名单列表，多个用`,`分隔。
-   allow\_empty：是否允许空refer进入，取值on或off。

 |
|referer\_black\_list\_set|refer黑名单| -   refer\_domain\_deny\_list：黑名单列表，多个`,`分隔。
-   allow\_empty：是否允许空refer进入，取值on或off。

 |
|filetype\_based\_ttl\_set|文件过期时间设置| -   ttl：cache时间，单位：秒。
-   file\_type：文件类型，支持多个，用`,`隔开。如：txt,jpg。
-   weight：权重，取值范围1~199。

 |
|path\_based\_ttl\_set|目录过期时间设置| -   ttl：cache时间，单位：秒。
-   path：目录，必须以`/`开头。
-   weight：权重，取值范围1~199。

 |
|oss\_auth|OSS鉴权Bucket|oss\_bucket\_id：用户bucket地址。|
|ip\_black\_list\_set|IP黑名单|ip\_list：IP列表多个用`,`隔开。|
|ip\_allow\_list\_set|IP白名单|ip\_list：IP列表多个用`,`隔开。|
|ip\_white\_list\_set|TMD免拦截|ip\_list：IP列表多个用`,`隔开。|
|error\_page|错误页面重定向| -   error\_code：错误码。
-   rewrite\_page：重定向页面。

 |
|set\_req\_host\_header|修改回源自定义头|domain\_name：回源Host头内容。|
|set\_hashkey\_args|忽略url参数| -   hashkey\_args：保留参数的列表，多个用`,`分隔。
-   disable：disable等于on的时候表示忽略所有参数，off不忽略。

 |
|ali\_remove\_args|忽略url参数\(删除\)| -   ali\_remove\_args：必填，删除指定的参数，多个参数之间用空格隔开，剩余参数将作为hashkey中URL args部分。
-   keep\_oss\_args：支持on/off。on表示回源保留所有参数，off表示与缓存hashkey的参数一致。

 |
|aliauth|阿里鉴权| -   auth\_type：鉴权类型，取值范围no\_auth，type\_a，type\_b，type\_c。
-   auth\_key1：鉴权key1。
-   auth\_key2：鉴权key2。
-   ali\_auth\_delta：自定义鉴权缓冲时间。

 |
|set\_resp\_header|设置响应头（浏览器端可见）| -   key：响应头。
-   value：响应头内容，删除填写null。

 |
|https\_force|强制HTTPS跳转|enable：功能开关，取值on或off。|
|http\_force|强制HTTP跳转|enable：功能开关，取值on或off。|
|https\_option|HTTPS基础参数|http2：http2开关，取值on或off。|
|l2\_oss\_key|L2 OSS 回源私钥|private\_oss\_auth：是否开启私有oss鉴权功能，取值on或off。|
|forward\_scheme|swift自适应回源| -   enable：开关，取值on或off。
-   scheme\_origin：回源站协议，支持http、https和follow。

 |
|green\_manager|鉴黄功能|enable：是否开启鉴黄功能，取值on或off。|
|tmd\_signature|TMD自定义规则| -   name：规则名称，域名内不可重复。
-   path：可重复，需校验uri路径合法性。
-   pathType ：匹配规则。0：前缀匹配；1：完全匹配。
-   interval：监测时长。单位秒，参数限制必须\>=10。
-   count：单IP访问次数。
-   action：阻断类型。0：封禁；1：人机识别。
-   ttl：阻断时长，单位秒。

 |
|dynamic|全站加速相关配置| -   enable：开关，必填，支持on/off。
-   static\_route\_type：静态加速文件后缀。
-   static\_route\_url：静态加速URI。
-   static\_route\_path：静态加速PATH。
-   dynamic\_route\_origin：回源路由 scheme，支持http/https/follow。

 |
|set\_req\_header|自定义回源HTTP头| -   key：回源头。
-   value：回源头内容。

 |
|l2\_oss\_key|私有buckct回源|private\_oss\_auth：私有Bucket回源开关，支持on/off。|
|range|range回源|enable：开关，支持on/off/force。|
|video\_seek|视频拖拽播放|enable：开关，支持on/off|
|https\_tls\_version|TLS协议版本| -   tls10：开启 TLSv1.0。默认：on，支持on/off。
-   tls11：开启 TLSv1.1。默认：on，支持on/off。
-   tls12：开启 TLSv1.2。默认：on，支持on/off。
-   tls13：开启 TLSv1.3。默认：on，支持on/off。

 |
|HSTS|HSTS| -   enabled：开关，必填。默认：off，支持on/off。
-   https\_hsts\_max\_age：过期时间，必填。单位：s，建议填写5184000s（60天）。
-   https\_hsts\_include\_subdomains：HSTS头包含includeSubDomains参数，支持on/off。请谨慎开启，开启前，请确保该加速域名所有子域名都已开启 HTTPS，否则会导致子域名自动跳转到HTTPS后无法访问。

 |
|filetype\_force\_ttl\_code|文件状态码过期时间设置| -   file\_type：文件类型，必填。支持多个，用逗号\(英文\)隔开，如txt,jpg。
-   code\_string：状态码，必填。例：302=0,301=0,4xx=2。

 |
|path\_force\_ttl\_code|路径状态码过期时间设置| -   path：必填，必须以/开头，举例：/image。
-   code\_string：状态码，必填。例：302=0,301=0,4xx=2。

 |
|gzip|智能压缩|enable：必填，功能开关，支持on/off。|
|tesla|页面优化|enable：必填，功能开关，支持on/off。|
|https\_origin\_sni|回源SNI| -   enabled：功能开关，支持on/off。
-   https\_origin\_sni：回源SNI，必填。

 |
|brotli|Brotli压缩| -   enable：必填，功能开关，支持on/off。
-   brotli\_level：压缩等级，数字，取值范围\[1,11\]。

 |
|ali\_ua|UsageAgent黑/白名单| -   ua：User-Agent。
-   type：名单类型。black或white。

 |
|host\_redirect|重写| -   regex：需要重写的URL，例如/$。
-   replacement：目标URL，例如/go/act/sale/tbzlsy.php。
-   flag：仅支持：redirect、break。

 |

## 返回参数 {#section_75o_7p3_u9u .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|该条任务请求Id。|

## 示例 {#section_a2g_imy_0hv .section}

请求示例

``` {#codeblock_mxn_o14_rb0}
http://cdn.aliyuncs.com/?Action=BatchSetCdnDomainConfig
&DomainName=example.com
&Functions=[{"functionArgs":[{"argName":"domain_name","argValue":"api.hellodtworld.com"}],"functionName":"set_req_host_header"}]
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_ydx_zvi_ut9 .language-json}
{
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 {#section_pkn_92j_u81 .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidFunctions.Malformed|Specified Functions is malformed.|400|指定的Functions不合法。|
|InvalidFunctionName.ValueNotSupported|FunctionName %s is not supported.|400|不支持的FunctionName %s\(%s为具体功能名\)。|
|InvalidArgName.ValueNotSupported|ArgName %s is not supported.|400|不支持的ArgName%s\(%s为具体参数名\)。|
|InvalidArgValue.Malformed|Specified ArgValue is malformed.|400|指定的ArgValue不合法。|

CDN所有API错误码，详情请参见[CDN错误码](https://error-center.aliyun.com/status/product/Cdn)。

