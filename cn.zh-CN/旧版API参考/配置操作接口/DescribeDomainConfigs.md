# DescribeDomainConfigs {#doc_api_Cdn_DescribeDomainConfigs .reference}

调用DescribeDomainConfigs接口获取指定加速域名的配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainConfigs&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainConfigs|操作接口名，系统规定参数 。取值：**DescribeDomainConfigs**。

 |
|DomainName|String|是|test.test.com|需要接入CDN的域名。

 |
|ConfigList|String|否|cache\_expired|需要查询的配置，多个配置用逗号（,）分隔，当前支持：

 -   **cache\_expired**
-   **cc**、**error\_page**
-   **http\_header**
-   **optimize**
-   **page\_compress**
-   **ignore\_query\_string**
-   **range**
-   **referer**
-   **req\_auth**
-   **src\_host**
-   **video\_seek**
-   **waf**
-   **notify\_url**
-   **redirect\_type**

 不填代表查询所有。

 |

ConfigList说明。

|名称

|类型

|描述

|
|----|----|----|
|cache\_expired

|String

|目录或文件过期配置。

|
|cc

|String

|CC防护功能、IP黑白名单配置。

|
|error\_page

|String

|自定义404错误页面跳转。

|
|http\_header

|String

|自定义http头。

|
|optimize

|String

|页面优化。

|
|page\_compress

|String

|智能压缩。

|
|ignore\_query\_string

|String

|过滤参数。

|
|range

|String

|range回源功能。

|
|referer

|String

|Refer防盗链功能。

|
|req\_auth

|String

|访问鉴权配置。

|
|src\_host

|String

|回源host。

|
|video\_seek

|String

|拖拽播放功能。

|
|waf

|String

|Waf防护功能。

|
|notify\_url

|String

|视频直播notify url。

|
|redirect\_type

|String

|强制访问跳转方式, 取值：Off、 Http、Https。

|
|dynamic

|String

|全站加速相关配置信息。

|
|set\_req\_header

|String

|设置回源自定义头。

|
|remove\_query\_string

|String

|忽略url参数（删除）。

|
|l2\_oss\_key

|String

|L2 OSS 回源私钥。

|
|macservice

|String

|移动加速。

|
|green\_manager

|String

|图片鉴黄。

|
|https\_option

|String

|https基础参数。

|

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|67E027D8-7A58-4599-B17A-63E9A54FC54F|请求ID

 |
|DomainConfigs| | |对应的配置数据

 |
|AliBusinessConfig| | |特定用户定制

 |
|AliBusinessTable|String|abc|模式字符串

 |
|AliBusinessType|String|typea|业务类型

 |
|ConfigId|String|4125638|配置id

 |
|Status|String|success|配置状态

 |
|CacheExpiredConfigs| | |文件、路径过期时间设置

 |
|CacheContent|String|jpeg|文件类型/路径

 |
|CacheType|String|suffix|**suffix**/**path**

 |
|ConfigId|String|604991|配置id

 |
|Status|String|success|配置状态

 |
|TTL|String|1000|cache时间

 单位：秒

 |
|Weight|String|1|SeqId

 |
|CcConfig| | |防cc攻击

 |
|AllowIps|String|1.2.3.4|TMD免拦截

 |
|BlockIps|String|3.4.5.6|IP黑名单

 |
|ConfigId|String|123|配置id

 |
|Enable|String|on|开启或关闭防CC攻击

 |
|Status|String|success|配置状态

 |
|DynamicConfigs| | |全站加速配置。

 |
|ConfigId|String|20|配置id

 |
|DynamicCacheControl|String|no-cache|Cache-Control内容匹配配置中任一规则强制开启动态加速，不再检查其余配置。样例: no-cache no-store

 |
|DynamicOrigin|String|http|回源路由 scheme

 |
|Enable|String|on|开关。

 |
|StaticPath|String|/to/no\_dynamic\_rou|URI为和配置内容正则匹配正确时关闭动态加速，多个用空格隔开，完全匹配\(^配置内容$\)，如需要彻底关闭动态加速可用"/\*"或"\*"。样例: /1

 -   \*.py

 |
|StaticType|String|jpg|文件后缀名完全匹配配置内容时关闭动态加速，多个用空格隔开。示例: .jpg .txt .html

 |
|StaticUri|String|yyy/ggss/ccc/a.txt|URI和配置内容完全匹配时关闭动态加速，多个用空格隔开。样例: /1/2/3.jpg /a/b/4.js

 |
|Status|String|success|配置状态

 |
|ErrorPageConfig| | |错误页面重定向

 |
|ConfigId|String|123|配置id

 |
|CustomPageUrl|String|http://promotion.alicdn.com/help/oss/error.html|重定向页面

 |
|ErrorCode|String|404|错误码

 |
|PageType|String|charity|类型

 |
|Status|String|success|配置状态

 |
|ForwardSchemeConfig| | |swift自适应回源

 |
|ConfigId|String|123|配置id

 |
|Enable|String|on|开关

 |
|SchemeOrigin|String|http|回源站协议 \(\*\*http\*\*|\*\*https\*\*|\*\*follow\*\*\)

 |
|SchemeOriginPort|String|80|回源站协议端口 \(80|443|80:443\)

 |
|Status|String|success1|配置状态

 |
|GreenManagerConfig| | |图片鉴黄

 |
|ConfigId|String|4047862|配置id

 |
|Enabled|String|off|开关

 |
|Status|String|success|配置状态

 |
|HttpErrorPageConfigs| | |错误页面重定向

 |
|ConfigId|String|23|配置id

 |
|ErrorCode|String|501|错误码

 |
|PageUrl|String|http://test.com/501.html|重定向页面

 |
|Status|String|success|配置状态

 |
|HttpHeaderConfigs| | |设置响应头（浏览器端可见）

 |
|ConfigId|String|602016|配置id

 |
|HeaderKey|String|content-type|应答头支持参数任何内容

 |
|HeaderValue|String|application|应答头内容支持参数任何内容，删除头请填写null

 |
|Status|String|success|配置状态

 |
|HttpsOptionConfig| | |HTTPS基础参数

 |
|ConfigId|String|3498758|配置id

 |
|Http2|String|off|http2开关

 |
|Status|String|success|配置状态

 |
|IgnoreQueryStringConfig| | |忽略url参数（保留）

 |
|ConfigId|String|123|配置id

 |
|Enable|String|on|缓存hashkey忽略所有参数

 |
|HashKeyArgs|String|time|缓存hashkey保留的参数列表，多个用逗号分隔，内容只允许是64位的10个元素

 |
|Status|String|success|配置状态

 |
|IpAllowListConfig| | |IP白名单

 |
|ConfigId|String|123|配置id

 |
|IpAclXfwd|String|on|on优先使用xff头中的ip,off优先使用remote\_addr ,all同时匹配

 |
|IpList|String|8.8.8.8|IP列表多个用逗号隔开

 |
|Status|String|success|配置状态

 |
|L2OssKeyConfig| | |L2 OSS 回源私钥

 |
|ConfigId|String|3512607|配置id

 |
|PrivateOssAuth|String|on|是否开启私有oss鉴权功能

 |
|Status|String|success|配置状态

 |
|MacServiceConfig| | |移动加速

 |
|AppList|String|app,app2|applist

 |
|ConfigId|String|3605171|配置id

 |
|Enabled|String|on|开关

 |
|ProcessResult|String|0|0 配置成功，1 移动加速SDK配置下发失败，2 移动加速调度节点配置失败，3 移动加速节点配置失败，4 移动加速证书生成失败，5 系统错误

 |
|Status|String|success|配置状态

 |
|NotifyUrlConfig| | |直播

 |
|Enable|String|on|开关

 |
|NotifyUrl|String|http://test.com|url

 |
|OptimizeConfig| | |页面优化加速

 |
|ConfigId|String|123123|配置id

 |
|Enable|String|off|开关

 |
|Status|String|success|配置状态

 |
|PageCompressConfig| | |页面Gzip优化

 |
|ConfigId|String|123|配置id

 |
|Enable|String|off|开关

 |
|Status|String|success|配置状态

 |
|RangeConfig| | |Range请求功能

 |
|ConfigId|String|123|配置id

 |
|Enable|String|on|开关

 |
|Status|String|success|配置状态

 |
|RedirectTypeConfig| | |强制HTTP/HTTPS跳转

 |
|RedirectType|String|Https|强制跳转

 |
|RefererConfig| | |Referer黑白名单设置

 |
|AllowEmpty|String|on|允许空refer进入

 |
|ConfigId|String|123|配置id

 |
|DisableAst|String|test|关闭域名前的. ，使用精确匹配

 |
|ReferList|String|www.aliyun.com|refer域名，多个域名用逗号隔开，前后不能包含“.”，后缀匹配。

 示例：sina.com 匹配www.sina.com,www.ch.sina.com

 |
|ReferType|String|block|refer类型

 |
|Status|String|success|配置状态

 |
|RemoveQueryStringConfig| | |忽略url参数（删除）

 |
|AliRemoveArgs|String|time|删除指定的参数，多个参数之间用空格隔开，剩余参数将作为hashkey中URL args部分

 |
|ConfigId|String|1123|配置id

 |
|Status|String|success|配置状态

 |
|ReqAuthConfig| | |阿里鉴权

 |
|AliAuthWhiteList|String|test|鉴权白名单

 |
|AuthAddr|String|http://test.com/test|远程验证服务器地址url

 |
|AuthM3u8|String|on|开启m3u8内容改写功能：on|off

 |
|AuthRemoteDesc|String|test|模式字符串

 |
|AuthType|String|type\_c|类型

 |
|ConfigId|String|123|配置id

 |
|Key1|String|vadfawerq|鉴权keyA

 |
|Key2|String|Acbdert|鉴权keyB

 |
|Status|String|success|配置状态

 |
|TimeOut|String|2400|自定义鉴权缓冲时间

 |
|ReqHeaderConfigs| | |修改回源自定义头

 |
|ConfigId|String|123|配置id

 |
|Key|String|testKey|回源头

 |
|Status|String|success|配置状态

 |
|Value|String|testValue|回源头内容，删除头请填写null

 |
|SetVarsConfigs| | |变量设置

 |
|ConfigId|String|4125719|配置id

 |
|Status|String|success|配置状态

 |
|VarName|String|typeb|已存在的nginx可写变量

 |
|VarValue|String|typeb|变量值，可引用其他变量

 |
|SrcHostConfig| | |修改回源Host头

 |
|ConfigId|String|123|配置id

 |
|DomainName|String|www.aliyun.com|回源Host头内容

 |
|Status|String|success|配置状态

 |
|VideoSeekConfig| | |视频切片拖拽开关

 |
|ConfigId|String|123|配置id

 |
|Enable|String|on|开关

 |
|Status|String|success|配置状态

 |
|WafConfig| | |防跨站注入攻击

 |
|ConfigId|String|123|配置id

 |
|Enable|String|off|开关

 |
|Status|String|success|配置状态

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainConfigs
&DomainName=example.com
&ConfigList="cache_expired,cc,page_compress"
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainConfigsResponse>
	  <DomainConfigs>
		    <DynamicConfigs>
			      <DynamicConfig>
				        <DynamicOrigin>http</DynamicOrigin>
				        <StaticType>jpg</StaticType>
				        <StaticUri>yyy/ggss/ccc/a.txt</StaticUri>
				        <StaticPath>/to/no_dynamic_rou</StaticPath>
				        <DynamicCacheControl>no-cache</DynamicCacheControl>
				        <ConfigId>20</ConfigId>
			      </DynamicConfig>
		    </DynamicConfigs>
		    <PageCompressConfig>
			      <Enable>off</Enable>
		    </PageCompressConfig>
		    <WafConfig>
			      <Enable>off</Enable>
		    </WafConfig>
		    <IgnoreQueryStringConfig>
			      <Enable>on</Enable>
		    </IgnoreQueryStringConfig>
		    <VideoSeekConfig>
			      <Enable>on</Enable>
		    </VideoSeekConfig>
		    <ReqAuthConfig>
			      <Key1>vadfawerq</Key1>
			      <Key2>Acbdert</Key2>
			      <AuthType>type_c</AuthType>
			      <TimeOut>2400</TimeOut>
		    </ReqAuthConfig>
		    <RangeConfig>
			      <Enable>on</Enable>
		    </RangeConfig>
		    <SrcHostConfig>
			      <DomainName>example.com</DomainName>
		    </SrcHostConfig>
		    <OptimizeConfig>
			      <Enable>off</Enable>
		    </OptimizeConfig>
		    <ErrorPageConfig>
			      <PageType>charity</PageType>
			      <CustomPageUrl>http://promotion.alicdn.com/help/oss/error.html</CustomPageUrl>
			      <ErrorCode>404</ErrorCode>
		    </ErrorPageConfig>
		    <HttpErrorPageConfigs>
			      <HttpErrorPageConfig>
				        <PageUrl>http://promotion.alicdn.com/help/oss/error.html</PageUrl>
				        <ErrorCode>404</ErrorCode>
			      </HttpErrorPageConfig>
			      <HttpErrorPageConfig>
				        <PageUrl>http://example.com/501.html</PageUrl>
				        <ErrorCode>501</ErrorCode>
			      </HttpErrorPageConfig>
			      <HttpErrorPageConfig>
				        <PageUrl>http://example.com/502.html</PageUrl>
				        <ErrorCode>502</ErrorCode>
			      </HttpErrorPageConfig>
		    </HttpErrorPageConfigs>
		    <RefererConfig>
			      <AllowEmpty>on</AllowEmpty>
			      <ReferType>block</ReferType>
			      <ReferList>example.com</ReferList>
		    </RefererConfig>
		    <CcConfig>
			      <Enable>on</Enable>
			      <AllowIps>1.2.3.4</AllowIps>
			      <BlockIps>3.4.5.6</BlockIps>
		    </CcConfig>
		    <HttpHeaderConfigs>
			      <HttpHeaderConfig>
				        <Status>success</Status>
				        <HeaderKey>content-type</HeaderKey>
				        <ConfigId>602016</ConfigId>
				        <HeaderValue>application</HeaderValue>
			      </HttpHeaderConfig>
			      <HttpHeaderConfig>
				        <Status>testing</Status>
				        <HeaderKey>content-type</HeaderKey>
				        <ConfigId>608841</ConfigId>
				        <HeaderValue>app</HeaderValue>
			      </HttpHeaderConfig>
			      <HttpHeaderConfig>
				        <Status>success</Status>
				        <HeaderKey>cache-control</HeaderKey>
				        <ConfigId>602018</ConfigId>
				        <HeaderValue>application</HeaderValue>
			      </HttpHeaderConfig>
			      <HttpHeaderConfig>
				        <Status>success</Status>
				        <HeaderKey>content-disposition</HeaderKey>
				        <ConfigId>602021</ConfigId>
				        <HeaderValue>application</HeaderValue>
			      </HttpHeaderConfig>
			      <HttpHeaderConfig>
				        <Status>success</Status>
				        <HeaderKey>content-language</HeaderKey>
				        <ConfigId>602024</ConfigId>
				        <HeaderValue>application</HeaderValue>
			      </HttpHeaderConfig>
			      <HttpHeaderConfig>
				        <Status>success</Status>
				        <HeaderKey>expires</HeaderKey>
				        <ConfigId>602026</ConfigId>
				        <HeaderValue>application</HeaderValue>
			      </HttpHeaderConfig>
			      <HttpHeaderConfig>
				        <Status>success</Status>
				        <HeaderKey>access-control-allow-origin</HeaderKey>
				        <ConfigId>602036</ConfigId>
				        <HeaderValue>application</HeaderValue>
			      </HttpHeaderConfig>
			      <HttpHeaderConfig>
				        <Status>success</Status>
				        <HeaderKey>access-control-allow-methods</HeaderKey>
				        <ConfigId>602038</ConfigId>
				        <HeaderValue>application</HeaderValue>
			      </HttpHeaderConfig>
			      <HttpHeaderConfig>
				        <Status>success</Status>
				        <HeaderKey>access-control-max-age</HeaderKey>
				        <ConfigId>602040</ConfigId>
				        <HeaderValue>application</HeaderValue>
			      </HttpHeaderConfig>
			      <HttpHeaderConfig>
				        <Status>success</Status>
				        <HeaderKey>content-type</HeaderKey>
				        <ConfigId>609871</ConfigId>
				        <HeaderValue>bbbb</HeaderValue>
			      </HttpHeaderConfig>
		    </HttpHeaderConfigs>
		    <AliBusinessConfig>
			      <Status>success</Status>
			      <AliBusinessType>typea</AliBusinessType>
			      <ConfigId>4125638</ConfigId>
		    </AliBusinessConfig>
		    <SetVarsConfigs>
			      <SetVarsConfig>
				        <Status>success</Status>
				        <VarValue>typeb</VarValue>
				        <VarName>typeb</VarName>
				        <ConfigId>4125719</ConfigId>
			      </SetVarsConfig>
			      <SetVarsConfig>
				        <Status>success</Status>
				        <VarValue>typea</VarValue>
				        <VarName>typea</VarName>
				        <ConfigId>4125726</ConfigId>
			      </SetVarsConfig>
		    </SetVarsConfigs>
		    <HttpsOptionConfig>
			      <Status>success</Status>
			      <ConfigId>3498758</ConfigId>
			      <Http2>off</Http2>
		    </HttpsOptionConfig>
		    <CacheExpiredConfigs>
			      <CacheExpiredConfig>
				        <Status>testing</Status>
				        <TTL>1000</TTL>
				        <CacheType>suffix</CacheType>
				        <CacheContent>jpeg</CacheContent>
				        <Weight>1</Weight>
				        <ConfigId>604991</ConfigId>
			      </CacheExpiredConfig>
			      <CacheExpiredConfig>
				        <Status>testing</Status>
				        <TTL>600</TTL>
				        <CacheType>suffix</CacheType>
				        <CacheContent>jpg,png</CacheContent>
				        <Weight>99</Weight>
				        <ConfigId>607216</ConfigId>
			      </CacheExpiredConfig>
			      <CacheExpiredConfig>
				        <Status>success</Status>
				        <TTL>99</TTL>
				        <CacheType>suffix</CacheType>
				        <CacheContent>ppp</CacheContent>
				        <ConfigId>609865</ConfigId>
			      </CacheExpiredConfig>
			      <CacheExpiredConfig>
				        <Status>testing</Status>
				        <TTL>300</TTL>
				        <CacheType>path</CacheType>
				        <CacheContent>/bmp</CacheContent>
				        <ConfigId>606402</ConfigId>
			      </CacheExpiredConfig>
			      <CacheExpiredConfig>
				        <Status>testing</Status>
				        <TTL>600</TTL>
				        <CacheType>path</CacheType>
				        <CacheContent>/static/html/</CacheContent>
				        <ConfigId>607206</ConfigId>
			      </CacheExpiredConfig>
			      <CacheExpiredConfig>
				        <Status>success</Status>
				        <TTL>100</TTL>
				        <CacheType>path</CacheType>
				        <CacheContent>/abc/def</CacheContent>
				        <ConfigId>609853</ConfigId>
			      </CacheExpiredConfig>
		    </CacheExpiredConfigs>
		    <NotifyUrlConfig>
			      <Enable>on</Enable>
			      <NotifyUrl>http://example.com</NotifyUrl>
		    </NotifyUrlConfig>
		    <RedirectTypeConfig>
			      <RedirectType>Https</RedirectType>
		    </RedirectTypeConfig>
		    <RemoveQueryStringConfig>
			      <ConfigId>1123</ConfigId>
			      <AliRemoveArgs>time</AliRemoveArgs>
		    </RemoveQueryStringConfig>
		    <L2OssKeyConfig>
			      <Status>success</Status>
			      <ConfigId>3512607</ConfigId>
			      <PrivateOssAuth>on</PrivateOssAuth>
		    </L2OssKeyConfig>
		    <GreenManagerConfig>
			      <Status>success</Status>
			      <Enabled>off</Enabled>
			      <ConfigId>4047862</ConfigId>
		    </GreenManagerConfig>
		    <MacServiceConfig>
			      <Status>success</Status>
			      <Enabled>on</Enabled>
			      <AppList>app,app2</AppList>
			      <ConfigId>3605171</ConfigId>
		    </MacServiceConfig>
		    <ReqHeaderConfigs>
			      <ReqHeaderConfig>
				        <Value>testValue</Value>
				        <Key>testKey</Key>
				        <ConfigId>123</ConfigId>
			      </ReqHeaderConfig>
		    </ReqHeaderConfigs>
	  </DomainConfigs>
	  <RequestId>67E027D8-7A58-4599-B17A-63E9A54FC54F</RequestId>
</DescribeDomainConfigsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"67E027D8-7A58-4599-B17A-63E9A54FC54F",
	"DomainConfigs":{
		"DynamicConfigs":{
			"DynamicConfig":[
				{
					"DynamicOrigin":"http",
					"StaticType":"jpg",
					"StaticUri":"yyy/ggss/ccc/a.txt",
					"StaticPath":"/to/no_dynamic_rou",
					"ConfigId":"20",
					"DynamicCacheControl":"no-cache"
				}
			]
		},
		"PageCompressConfig":{
			"Enable":"off"
		},
		"NotifyUrlConfig":{
			"NotifyUrl":"http://example.com",
			"Enable":"on"
		},
		"RedirectTypeConfig":{
			"RedirectType":"Https"
		},
		"RemoveQueryStringConfig":{
			"ConfigId":"1123",
			"AliRemoveArgs":"time"
		},
		"WafConfig":{
			"Enable":"off"
		},
		"MacServiceConfig":{
			"Enabled":"on",
			"Status":"success",
			"AppList":"app,app2",
			"ConfigId":"3605171"
		},
		"ReqHeaderConfigs":{
			"ReqHeaderConfig":[
				{
					"Value":"testValue",
					"Key":"testKey",
					"ConfigId":"123"
				}
			]
		},
		"HttpErrorPageConfigs":{
			"HttpErrorPageConfig":[
				{
					"PageUrl":"http://promotion.alicdn.com/help/oss/error.html",
					"ErrorCode":"404"
				},
				{
					"PageUrl":"http://example.com/501.html",
					"ErrorCode":"501"
				},
				{
					"PageUrl":"http://example.com/502.html",
					"ErrorCode":"502"
				}
			]
		},
		"RangeConfig":{
			"Enable":"on"
		},
		"ReqAuthConfig":{
			"Key2":"Acbdert",
			"Key1":"vadfawerq",
			"TimeOut":"2400",
			"AuthType":"type_c"
		},
		"SetVarsConfigs":{
			"SetVarsConfig":[
				{
					"Status":"success",
					"VarValue":"typeb",
					"VarName":"typeb",
					"ConfigId":"4125719"
				},
				{
					"Status":"success",
					"VarValue":"typea",
					"VarName":"typea",
					"ConfigId":"4125726"
				}
			]
		},
		"OptimizeConfig":{
			"Enable":"off"
		},
		"CcConfig":{
			"BlockIps":"3.4.5.6",
			"Enable":"on",
			"AllowIps":"1.2.3.4"
		},
		"L2OssKeyConfig":{
			"Status":"success",
			"ConfigId":"3512607",
			"PrivateOssAuth":"on"
		},
		"GreenManagerConfig":{
			"Enabled":"off",
			"Status":"success",
			"ConfigId":"4047862"
		},
		"HttpsOptionConfig":{
			"Status":"success",
			"ConfigId":"3498758",
			"Http2":"off"
		},
		"VideoSeekConfig":{
			"Enable":"on"
		},
		"IgnoreQueryStringConfig":{
			"Enable":"on"
		},
		"SrcHostConfig":{
			"DomainName":"example.com"
		},
		"AliBusinessConfig":{
			"Status":"success",
			"AliBusinessType":"typea",
			"ConfigId":"4125638"
		},
		"ErrorPageConfig":{
			"CustomPageUrl":"http://promotion.alicdn.com/help/oss/error.html",
			"ErrorCode":"404",
			"PageType":"charity"
		},
		"RefererConfig":{
			"AllowEmpty":"on",
			"ReferType":"block",
			"ReferList":"example.com"
		},
		"HttpHeaderConfigs":{
			"HttpHeaderConfig":[
				{
					"Status":"success",
					"HeaderValue":"application",
					"ConfigId":"602016",
					"HeaderKey":"content-type"
				},
				{
					"Status":"testing",
					"HeaderValue":"app",
					"ConfigId":"608841",
					"HeaderKey":"content-type"
				},
				{
					"Status":"success",
					"HeaderValue":"application",
					"ConfigId":"602018",
					"HeaderKey":"cache-control"
				},
				{
					"Status":"success",
					"HeaderValue":"application",
					"ConfigId":"602021",
					"HeaderKey":"content-disposition"
				},
				{
					"Status":"success",
					"HeaderValue":"application",
					"ConfigId":"602024",
					"HeaderKey":"content-language"
				},
				{
					"Status":"success",
					"HeaderValue":"application",
					"ConfigId":"602026",
					"HeaderKey":"expires"
				},
				{
					"Status":"success",
					"HeaderValue":"application",
					"ConfigId":"602036",
					"HeaderKey":"access-control-allow-origin"
				},
				{
					"Status":"success",
					"HeaderValue":"application",
					"ConfigId":"602038",
					"HeaderKey":"access-control-allow-methods"
				},
				{
					"Status":"success",
					"HeaderValue":"application",
					"ConfigId":"602040",
					"HeaderKey":"access-control-max-age"
				},
				{
					"Status":"success",
					"HeaderValue":"bbbb",
					"ConfigId":"609871",
					"HeaderKey":"content-type"
				}
			]
		},
		"CacheExpiredConfigs":{
			"CacheExpiredConfig":[
				{
					"Status":"testing",
					"Weight":"1",
					"CacheType":"suffix",
					"CacheContent":"jpeg",
					"ConfigId":"604991",
					"TTL":"1000"
				},
				{
					"Status":"testing",
					"Weight":"99",
					"CacheType":"suffix",
					"CacheContent":"jpg,png",
					"ConfigId":"607216",
					"TTL":"600"
				},
				{
					"Status":"success",
					"CacheType":"suffix",
					"CacheContent":"ppp",
					"ConfigId":"609865",
					"TTL":"99"
				},
				{
					"Status":"testing",
					"CacheType":"path",
					"CacheContent":"/bmp",
					"ConfigId":"606402",
					"TTL":"300"
				},
				{
					"Status":"testing",
					"CacheType":"path",
					"CacheContent":"/static/html/",
					"ConfigId":"607206",
					"TTL":"600"
				},
				{
					"Status":"success",
					"CacheType":"path",
					"CacheContent":"/abc/def",
					"ConfigId":"609853",
					"TTL":"100"
				}
			]
		}
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidConfigList.ValueNotSupported|The specified value of parameter ConfigList is not supported.|指定查询的配置项参数值不合法。|
|400|MissingParameter|The specified value of parameter "DomainName" is not valid.|参数“DomainName”的值无效。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

