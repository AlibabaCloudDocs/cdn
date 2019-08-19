# BatchDeleteCdnDomainConfig {#doc_api_Cdn_BatchDeleteCdnDomainConfig .reference}

调用BatchDeleteCdnDomainConfig接口删除域名配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=BatchDeleteCdnDomainConfig&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchDeleteCdnDomainConfig|操作接口名，系统规定参数。取值：**BatchDeleteCdnDomainConfig**。

 |
|DomainNames|String|是|www.macaron.org.cn,xxx.org.com|您的加速域名，多个用逗号（,）分隔。

 |
|FunctionNames|String|是|referer\_white\_list\_set,https\_force|功能列表名称，用逗号分隔。

 |

功能说明。

|名称

|参数

|
|----|----|
|referer\_white\_list\_set：refer白名单

|refer\_domain\_allow\_list：白名单列表，多个逗号（,）分隔。

 allow\_empty 是否允许空refer进入，取值范围：on或off。

 |
|referer\_black\_list\_set：refer黑名单

|refer\_domain\_deny\_list：黑名单列表，多个逗号（,）分隔。

 allow\_empty 是否允许空refer进入，取值范围：on或off。

 |
|filetype\_based\_ttl\_set：文件过期时间设置

|ttl：cache时间，单位：秒。

 file\_type：文件类型。支持多个，用逗号（,）隔开，例如txt,jpg。

 |
|path\_based\_ttl\_set：目录过期时间设置

|ttl：cache时间，单位：秒。

 path：目录，必须以正斜线（/）开头。

 |
|cc\_defense：防CC攻击

|enable：开启或关闭防CC攻击，取值范围：on或off。

|
|oss\_auth：OSS鉴权Bucket

|oss\_bucket\_id：用户bucket地址。

|
|ip\_black\_list\_set：IP黑名单

|ip\_list：IP列表多个用逗号（,）隔开。

|
|ip\_white\_list\_set：IP白名单

|ip\_list：IP列表多个用逗号（,）隔开。

|
|error\_page：错误页面重定向

|error\_code：错误码。

 rewrite\_page：重定向页面。

 |
|tesla：页面优化加速

|enable：功能开关，取值范围：on或off。

|
|set\_req\_host\_header：修改回源自定义头

|domain\_name：回源Host头内容。

|
|set\_hashkey\_args：忽略url参数

|hashkey\_args：保留参数的列表，多个用逗号（,）分隔。

 disable：disable等于on的时候表示忽略所有参数，off不忽略。

 |
|aliauth：阿里鉴权

|auth\_type：鉴权类型，取值范围no\_auth、type\_a、type\_b、type\_c。

 auth\_key1：鉴权key1；auth\_key2：鉴权key2。

 ali\_auth\_delta：自定义鉴权缓冲时间。

 |
|set\_resp\_header：设置响应头（浏览器端可见）

|key：响应头。

 value：响应头内容，删除填写null。

 |
|video\_seek：视频切片拖拽开关

|enable：功能开关，取值范围：on或off。

|
|range：Range请求功能

|enable：功能开关，取值范围：on或off。

|
|gzip：页面Gzip优化

|enable：功能开关，取值范围：on或off。

|
|https\_force：强制HTTPS跳转

|enable：功能开关，取值范围：on或off。

|
|http\_force：强制HTTP跳转

|enable：功能开关，取值范围：on或off。

|
|alilive：视频直播配置

|notify\_url：直播通知url；

 enable：功能开关，取值范围：on或off。

 |
|forward\_scheme：静态协议跟随回源

|enable：功能开关，取值范围：on或off。

 scheme\_origin：回源站协议，http、https、follow。

 scheme\_origin\_port：回源站协议端口，80、443。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com?Action=BatchDeleteCdnDomainConfig
&DomainNames=www.macaron.org.cn,xxx.org.com
&FunctionNames=referer_white_list_set,https_force
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchDeleteCdnDomainConfigResponse>
	  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</BatchDeleteCdnDomainConfigResponse>
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
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|此方法不支持。|
|400|DeleteFunctionFailed|Batch delete functions failed.|批量删除功能失败。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

