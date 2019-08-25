# BatchSetCdnDomainConfig {#doc_api_Cdn_BatchSetCdnDomainConfig .reference}

调用BatchSetCdnDomainConfig进行域名批量配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=BatchSetCdnDomainConfig&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchSetCdnDomainConfig|操作接口名，系统规定参数，取值：**BatchSetCdnDomainConfig**。

 |
|DomainNames|String|是|example.com|加速域名，多个用逗号（,）分隔。

 |
|Functions|String|是|\[\{"functionArgs":\[\{"argName":"domain\_name","argValue":"api.hellodtworld.com"\}\],"functionName":"set\_req\_host\_header"\}\]|功能列表。

 |

某些功能，例如：filetype\_based\_ttl\_set，可以设置多条纪录，当需要更新其中某条纪录时，可通过该条纪录的configId来指定。

```
[{"functionArgs":[{"argName":"file_type","argValue":"jpg"},{"argName":"ttl","argValue":"18"},{"argName":"weight","argValue":"30"}],"functionName":"filetype_based_ttl_set","configId":5068995}]
```

功能说明：所有参数值均按照字符串类型处理。

|名称

|参数

|
|----|----|
|referer\_white\_list\_set：refer白名单

|refer\_domain\_allow\_list：白名单列表，多个逗号（,）分隔。

 allow\_empty：是否允许空refer进入，取值范围：on或off。

 |
|referer\_black\_list\_set：refer黑名单

|refer\_domain\_deny\_list：黑名单列表，多个逗号（,）分隔。

 allow\_empty：是否允许空refer进入，取值范围：on或off。

 |
|filetype\_based\_ttl\_set：文件过期时间设置

|ttl：cache时间，单位：秒。

 file\_type：文件类型：支持多个，用逗号（,）隔开，例如：txt,jpg。

 weight：权重，取值范围1~199。

 |
|path\_based\_ttl\_set：目录过期时间设置

|ttl：cache时间，单位：秒。

 path：目录，必须以正斜线（/）开头。

 weight：权重，取值范围1~99。

 |
|oss\_auth：OSS鉴权Bucket

|oss\_bucket\_id：用户bucket地址。

|
|ip\_black\_list\_set：IP黑名单

|ip\_list：IP列表多个用逗号（,）隔开。

|
|ip\_allow\_list\_set：IP白名单

|ip\_list：IP列表多个用逗号（,）隔开。

|
|ip\_white\_list\_set：TMD免拦截

|ip\_list：IP列表多个用逗号（,）隔开。

|
|error\_page：错误页面重定向

|error\_code：错误码。

 rewrite\_page：重定向页面。

 |
|set\_req\_host\_header：修改回源自定义头

|domain\_name：回源Host头内容。

|
|set\_hashkey\_args：忽略url参数

|hashkey\_args：保留参数的列表，多个用逗号（,）分隔。

 disable：disable等于on的时候表示忽略所有参数，off不忽略（缓存hashkey忽略所有参数，优先级低于保留缓存参数列表功能\)。

 keep\_oss\_args：on时候表示回源保留所有参数，of表示与缓存hashkey的参数一致。

 |
|aliauth：阿里鉴权

|auth\_type：鉴权类型，取值范围：no\_auth、type\_a、type\_b、type\_c。

 auth\_key1：鉴权key1；auth\_key2：鉴权key2。

 ali\_auth\_delta：自定义鉴权缓冲时间。

 |
|set\_resp\_header：设置响应头（浏览器端可见）

|key：响应头，取值范围：Content-Type、Cache-Control、Content-Disposition、Content-Language、Expires、Access-Control-Allow-Origin、Access-Control-Allow-Methods、Access-Control-Allow-Headers、Access-Control-Max-Age、Access-Control-Expose-Headers。

 value：响应头内容，删除填写null。

 |
|https\_force：强制HTTPS跳转

|enable：功能开关，取值范围：on或off。

|
|http\_force：强制HTTP跳转

|enable：功能开关，取值范围：on或off。

|
|https\_option：HTTPS基础参数

|http2：http2开关，取值范围：on或off。

|
|forward\_scheme：静态协议跟随回源

|enable：开关，取值范围：on或off。

 scheme\_origin：回源站协议，支持http、https和follow。

 |
|green\_manager 鉴黄功能

|enable：是否开启鉴黄功能，取值范围：on或off。

|
|tmd\_signature：TMD自定义规则

|name：规则名称，域名内不可重复。

 path：可重复，需校验uri路径合法性。

 pathType：匹配规则，0为前缀匹配，1为完全匹配。

 interval：监测时长，单位：秒，参数限制必须大于等于10。

 count：单IP访问次数。

 action：阻断类型，0为封禁，1为人机识别。

 ttl：阻断时长，单位：秒。

 |
|dynamic：全站加速相关配置

|enable：必填，开关，支持on或off。

 static\_route\_type：静态加速文件后缀。

 static\_route\_url：静态加速URI。

 static\_route\_path：静态加速PATH。

 dynamic\_route\_origin：回源路由scheme，支持http、https、follow。

 dynamic\_route\_round\_robin：开启负载均衡开关，支持on或off。

 |
|set\_req\_header：自定义回源HTTP头

|key：回源头。

 value：回源头内容。

 |
|l2\_oss\_key：私有buckct回源

|private\_oss\_auth：私有Bucket回源开关，支持on或off。

|
|range：range回源

|enable：开关，支持on、off、force。

|
|video\_seek：视频拖拽播放

|enable：开关，支持on或off，必填。

 flv\_seek\_by\_time：开启flv按时间拖拽，支持on或off。

 mp4\_seek\_start：自定义MP4开始参数。

 mp4\_seek\_end：自定义MP4结束参数。

 flv\_seek\_start：自定义flv开始参数。

 flv\_seek\_end：自定义flv结束参数。

 |
|ali\_remove\_args：忽略url参数\(删除\)

|ali\_remove\_args：必填，删除指定的参数，多个参数之间用空格隔开，剩余参数将作为hashkey中URL args部分。

 keep\_oss\_args：支持on或off。on表示回源保留所有参数，off表示与缓存hashkey的参数一致。

 |
|https\_tls\_version：TLS协议版本

|tls10：开启 TLSv1.0 默认：on，支持on或off。

 tls11：开启 TLSv1.1 默认：on，支持on或off。

 tls12：开启 TLSv1.2 默认：on，支持on或off。

 tls13：开启 TLSv1.3 默认：off，支持on或off。

 |
|HSTS：HSTS

|enabled：必填，开关，默认： off，支持on或off。

 https\_hsts\_max\_age：必填，过期时间，单位：s，建议填写5184000s（60天）。

 https\_hsts\_include\_subdomains： HSTS头包含includeSubDomains参数，支持on或off。请谨慎开启，开启前，请确保该加速域名所有子域名都已开启HTTPS，否则会导致子域名自动跳转到HTTPS后无法访问。

 |
|filetype\_force\_ttl\_code：文件状态码过期时间设置

|file\_type：必填，支持多个文件类型，用逗号（,）隔开，例如：txt,jpg。

 code\_string：必填，状态码，例如：302=0、301=0、4xx=2。

 |
|path\_force\_ttl\_code：路径状态码过期时间设置。

|path：必填，必须以正斜线（/）开头，例如：/image。

 code\_string：必填，状态码，例如：302=0、301=0、4xx=2。

 |
|gzip：页面Gzip优化

|enable：必填，功能开关，支持on或off。

|
|tesla：页面优化加速

|enable：必填，功能开关，支持on或off。

|
|https\_origin\_sni：回源SNI

|enabled：功能开关，支持on或off。

 https\_origin\_sni：回源SNI，必填。

 |
|limit\_rate：单请求限速

|ali\_limit\_rate：必填，默认限速，限速多少（例如：200k、1m等），单位Byte/s。

 ali\_limit\_rate\_after：不限速大小，在发送了多少数据之后限速，单位Byte。

 traffic\_limit\_arg：限速参数名称，根据url中的提取的arg进行限速,例如：rate。

 traffic\_limit\_unit：限速参数单位，支持m、k、g，当rate=1，则限速1m或1k或1g。

 ali\_limit\_start\_hour：限速开始时间，请输入0-24范围的数字，小于限速结束时间，默认值为0。

 ali\_limit\_end\_hour：限速结束时间，请输入0-24范围的数字，大于限速开始时间，默认值为24。

 |
|brotli：页面brotli压缩

|enable：必填，功能开关，支持on或off。

 brotli\_level：压缩等级，数字，取值范围\[1,11\]。

 |
|ali\_ua：User-Agent限制访问

|ua：User-Agent。

 type：名单类型，black或white。

 |
|set\_l2\_req\_header：修改L2回源自定义头

|key：回源头。

 value：回源头内容，删除头请填写null。

 |
|host\_redirect：rewrite功能

|regex：需要重写的URL，例如：^/$。

 replacement：目标URL，例如： /go/act/sale/tbzlsy.php。

 flag：支持redirect、break。

 |
|quic：QUIC基础参数

|quic\_enable：quic开关，支持on或off。

|
|forward\_timeout：回源请求超时

|forward\_timeout：单位为s，一般不要配置大于100。

|
|ali\_video\_split：音视频分离

|enabled：开关，支持on或off。

|

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com/?Action=BatchSetCdnDomainConfig
&DomainName=example.com
&Functions=[{"functionArgs":[{"argName":"domain_name","argValue":"api.hellodtworld.com"}],"functionName":"set_req_host_header"}]
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchSetCdnDomainConfigResesponse>
	  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</BatchSetCdnDomainConfigResesponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidHeaderKey.ValueNotSupported|The specified value of parameter HeaderKey is not supported.|指定的HTTP头参数不合法，超出可选范围。取值：Content-Type,Cache-Control,Content-Disposition,Content-Language,Expires,Access-Control-Allow-Origin,Access-Control-Allow-Methods,Access-Control-Allow-Headers,Access-Control-Max-Age,Access-Control-Expose-Headers,Access-Control-Allow-Credentials。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

