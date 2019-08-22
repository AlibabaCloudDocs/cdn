# BatchAddCdnDomain {#doc_api_Cdn_BatchAddCdnDomain .reference}

调用BatchAddCdnDomain批量添加加速域名，一个用户最多添加20个域名。

添加加速域名，一次只能提交一个加速域名，一个用户最多添加20个域名。 限制条件如下所示：

-   创建加速域名之前, 必须先开通CDN服务，具体操作请参见[开通CDN服务](~~27272~~)。
-   加速域名必须已备案完成。
-   源站内容，如果不在阿里云平台上，需要审核，审核工作会在下一工作日前完成。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=BatchAddCdnDomain&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchAddCdnDomain|操作接口名，系统规定参数。 取值：**BatchAddCdnDomain**。

 |
|CdnType|String|是|web|加速域名的业务类型。 取值：

 -   **web**：图片及小文件分发。
-   **download**：大文件下载加速。
-   **Video**：视频点播加速。

 |
|DomainName|String|是|example.com|需要接入CDN的域名。多个域名之间用逗号（,）隔开。

 |
|Sources|String|是|\[\{“content”:”1.1.1.1”,”type”:”ipaddr”,”priority”:”20”,”port”:80,”weight”:”15”\}\]|回源地址列表。

 |
|CheckUrl|String|否|url|检测url。

 |
|ResourceGroupId|String|否|123|资源组id，不传时，自动补全默认资源组id。

 |
|Scope|String|否|domestic|取值范围：

 -   **domestic**
-   **overseas**
-   **global**

 |
|TopLevelDomain|String|否|www.yourdomain.com|顶级接入域。

 |

Sources各字段含义

|参数

|类型

|必须?

|描述

|
|----|----|-----|----|
|type

|String

|是

|源站类型取值：ipaddr：IP源站；domain：域名源站；oss：OSSBucket为源站；fc\_domain：函数计算源站。

|
|content

|String

|是

|回源地址，可以是IP或域名。

|
|port

|Integer

|否

|可以指定443,80。默认值80。443的话走https回源。也可以自定义端口。

|
|priority

|String

|否

|源站地址对应的优先级，默认20。

|
|weight

|String

|否

|回源权重，默认10。

|

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com/?Action=BatchAddCdnDomain
&CdnType=web
&DomainName=example.com
&Sources=[{“content”:”1.1.1.1”,”type”:”ipaddr”,”priority”:”20”,”port”:80,”weight”:”15”}]
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchAddCdnDomainResponse>
	  <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
</BatchAddCdnDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidDomainName.Malformed|Specified DomainName is malformed.|域名格式错误或批量新增不支持泛域名。|
|400|MissingParameter|The input parameter cdnType that is mandatory for processing this request is not supplied.|参数cdnType为必填。|
|400|InvalidCdnType.Malformed|Specified CdnType is malformed.|参数CdnType不支持该参数值， 取值：web：图片及小文件分发；download：大文件下载加速；video：视音频点播加速；liveStream：直播流媒体加速。|
|400|InvalidSources.Malformed|Specified Sources is malformed.|参数Sources格式错误。可以是IP或域名；IP支持最多20个，以逗号区分，域名只能输入一个。IP与域名不能同时输入。|
|400|MissingParameter|The input parameter sourceType that is mandatory for processing this request is not supplied.|参数sourceType为必填。|
|400|InvalidSourceType.Malformed|Specified CdnType is malformed.|CdnType格式错误。|
|400|InvalidScope.Malformed|Specified Scope is malformed.|Scope格式错误。|
|400|SourceIp.Exceed|The Certificate you provided is malformed!|证书格式不正确。|
|400|InvalidCertificate|The Certificate you provided is malformed!|证书格式不正确。|
|400|InvalidCertificate.TooLong|The Certificate you provided is over the max length!|证书和私钥长度超出限制。|
|400|InnerAddDomainDenied|Your account haven't bind aoneId, can not add domain.|您的帐户没有绑定aoneId，不能添加域名。|
|400|ExtensiveAndAllBothExist|Extensive domain and the domain begins with 'all.' can not exist at the same time.|泛域名与all.开头域名不能同时存在。|
|400|CdnTypeNotSupportExtensiveDomain|Extensive domain not supported for this cdn type.|泛域名不支持该业务类型，目前泛域名只支持图片小文件加速，大文件下载加速，视频点播加速，请知悉。|
|400|ExtensiveAndSpecificDomainConflict|Extensive domain and corresponding specific domain are mutually exclusive.|泛域名和同级精确域名互斥，请重新添加。|
|400|InvalidResourceGroupId.Malformed|Specified ResourceGroupId is malformed.|参数 ResourceGroupId格式错误。|
|400|InvalidDomainNameLevel|Domain name suffixed with alicdn.com only support third level.|alicdn.com最多支持三级域名。|
|400|InvalidTopLevelDomain.Malformed|Specified TopLevelDomain is malformed.|参数 TopLevelDomain 错误。|
|400|TopLevelDomain.NotFound|TopLevelDomain is not exist.|TopLevelDomain 不存在。|
|400|EntityNotExists.ResourceGroup|The resource group does not exist.|资源组不存在。|
|400|InvalidStatus.ResourceGroup|It's now allowed to do this operation because of the current status of resource-group.|资源组当前状态不允许进行此操作。|
|400|NotInternationRealIdentity|You need to do real name authentication when you use Chinese mainland resources.|根据中华人民共和国法律规定，在中国境内购买使用信息服务的用户需要进行实名登记。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

