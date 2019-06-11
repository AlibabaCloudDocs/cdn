# AddCdnDomain {#reference_pv4_cvf_cgb .reference}

调用AddCdnDomain添加加速域名。一次只能提交一个加速域名，一个用户最多添加20个域名。

**说明：** 

-   创建加速域名之前, 您需要先开通CDN服务。请参见[开通CDN服务](../../../../intl.zh-CN/产品定价/开通CDN服务.md#)。
-   加速域名必须已备案完成。
-   源站内容，如果不在阿里云平台上，需要审核，审核工作会在下一工作日前完成。

## 调试 {#section_l7j_ph7_bu2 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=AddCdnDomain)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_hjy_xwf_cgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。 取值：AddCdnDomain。|
|DomainName|String|是|需要接入CDN的域名。支持泛域名，以符号`.`开头，如：`.example.com`。|
|CdnType|String|是|加速域名的业务类型。 取值： -   web：图片及小文件分发。
-   download：大文件下载加速。
-   Video：视频点播加速。

 |
|Sources|String|是|回源地址列表。|
|CheckUrl|String|否|检测url。|
|Scope|String|否|取值范围： -   domestic
-   overseas
-   global

 默认值：domestic。国际用户、国内L3及以上用户设置有效。|
|ResourceGroupId|String|否|资源组id，不传时，自动补全默认资源组id。|
|TopLevelDomain|String|否|顶级接入域。|

Sources格式

``` {#codeblock_0du_v7a_4h8}
[{“content”:”1.1.1.1”,”type”:”ipaddr”,””:”20”,”port”:80,”weight”:”15”}]
```

Sources各字段含义

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|type|String|是|源站类型 。取值： -   ipaddr：IP源站。
-   domain：域名源站。
-   oss：OSS Bucket为源站。

 |
|content|String|是|回源地址。可以是IP或域名。|
|port|Integer|否|可以指定443或80。默认值：80。443走https回源或自定义端口。|
|priority|String|否|源站地址对应的优先级。默认值：20。|
|weight|String|否|回源权重。默认值：10。|

## 返回参数 {#section_qz2_j1g_cgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestID|String|该条任务请求ID。|

## 示例 {#section_hlm_fyf_cgb .section}

请求示例

``` {#codeblock_imp_rwt_7hg}
http://cdn.aliyuncs.com?Action=AddCdnDomain&CdnType=web&DomainName=example.com&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80}]&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_jup_d2a_xbx}
{
  "RequestId": "15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## 错误码 {#section_klm_fyf_cgb .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidDomainName.Malformed|Specified DomainName is malformed.|400|DomainName 参数错误。|
|InvalidCdnType.Malformed|Specified CdnType is malformed.|400|CdnType参数错误。|
|InvalidSourceType.Malformed|Specified SourceType is malformed.|400|SourceType参数错误。|
|InvalidSources.Malformed|Specified Sources is malformed.|400|回源地址与源站类型不一致。|
|InvalidScope.Malformed|Specified Scope is malformed.|400|Scope参数错误。|
|InvaildParameter|The Certificate you provided is malformed!|400|https安全加速时证书和密钥长度和过长。|
|BusinessExist|Business exist do not repeated submission|400|该域名正在添加，不用重复提交。|
|DomainAlreadyExist|This domain name is exist already|400|该域名已经添加。|
|DomainOverLimit|The Number of Domain is over the limit|403|超过域名个数限制。|
|DomainNotRegistration|The Domain name is not registered|404|该域名没有备案。|
|IllegalOperation|Illegal domain operate is not permitted.|403|没有权限执行当前操作。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中, 请稍后再试。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|InnerAddDomainDenied|Your account haven’t bind aoneId, can not add domain.|400|内部账号未绑定aoneId，不能添加域名。|
|ExtensiveAndAllBothExist|Extensive domain and the domain begins with ‘all.’ can not exist at the same time.|400|泛域名与all.开头域名不能同时存在。|
|CdnTypeNotSupportExtensiveDomain|Extensive domain not supported for this cdn type.|400|泛域名不支持该业务类型。|
|ExtensiveAndSpecificDomainConflict|Extensive domain and corresponding specific domain are mutually exclusive.|400|泛域名与对应同级别精确域名互斥。|
|InvalidParameter|Add live region parameters have error.|400|添加的直播region信息时出错。|
|InvalidRegion.Malformed|Specified Region is malformed.|400|region参数不正确。|
|Abs.resourceGroupId.Malformed|Specified ResourceGroupId is malformed.|400|资源组id参数不正确。|
|InvalidTopLevelDomain.Malformed|Specified TopLevelDomain is malformed.|400|TopLevelDomain参数不正确。|
|TopLevelDomain.NotFound|TopLevelDomain is not exist.|400|TopLevelDomain不存在。|
|InvalidResourceGroupId.Malformed|Specified ResourceGroupId is malformed.|400|ResourceGroupId参数不正确。|
|EntityNotExists.ResourceGroup|The resource group does not exist.|400|资源组不存在。|
|InvalidStatus.ResourceGroup|It’s now allowed to do this operation because of the current status of resource-group.|400|资源组状态检查失败。|
|InvalidPriorities.Malformed|The length of priorities is not the same with source.|400|优先级个数与源站个数不同。|
|NotInternationRealIdentity|You need to do real name authentication when you use Chinese mainland resources.|400|用中国大陆资源时，账号需要国际认证。|
|DomainReserved|The root domain of your domain is reserved by another account. Submit a ticket to contact customer support.|400|该域名的根域已经被其他账号占用，若需要新增提交工单处理。|

