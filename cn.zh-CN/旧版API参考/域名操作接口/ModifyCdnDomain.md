# ModifyCdnDomain {#doc_api_Cdn_ModifyCdnDomain .reference}

调用ModifyCdnDomain接口修改加速域名。

目前支持修改源站。限制条件：

-   创建加速域名之前，必须先开通CDN服务。
-   加速域名必须已备案完成。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=ModifyCdnDomain&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyCdnDomain|操作接口名，系统规定参数。取值：**ModifyCdnDomain**。

 |
|DomainName|String|是|www.yourdomain.com|接入CDN的域名。

 |
|Priorities|String|否|20|源站地址对应的优先级。

 多个源站时，用逗号（,）分隔。

 默认值：20。

 |
|ResourceGroupId|String|否|abcdabcd|资源组ID。

 |
|SourcePort|Integer|否|80|回源端口。

 |
|SourceType|String|否|domain|源站类型。取值：

 -   **ipaddr**：IP源站。
-   **domain**：域名源站。
-   **oss**：OSS Bucket为源站（内部common：公共源）。

 **说明：** 如果您选择了直播流媒体加速的业务类型，无需填写源站类型和信息。

 |
|Sources|String|否|yourdomain.com|回源地址，可以是IP或域名。

 -   IP或域名支持最多20个，以逗号区分。
-   IP与域名不能同时输入。
-   除了业务类型为直播流媒体加速无需输入源站地址外，其他业务类型源站地址必填（内部用户，类型为common公有源，可以填写类型枚举值）。

 |
|TopLevelDomain|String|否|your.top.domain.com|顶级接入域。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=ModifyCdnDomain&SourceType=domain
&DomainName=example.com
&Sources=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyCdnDomainResponse>
    <RequestId>A22F5DDD-E6B8-4DB4-A210-FF3CA5A82644</RequestId>
</ModifyCdnDomainResponse>
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
|400|InvalidCdnType.Malformed|Specified CdnType is malformed.|参数CdnType不支持该参数值， 取值：web：图片及小文件分发；download：大文件下载加速；video：视音频点播加速；liveStream：直播流媒体加速。|
|400|MissingSourceType|The input parameter sourceType that is mandatory for processing this request is not supplied.|参数sourceType为必填。|
|400|MissingSources|The input parameter sourceStr that is mandatory for processing this request is not supplied.|参数sourceStr为必填。|
|400|InvalidDomainName.Malformed|The specific value of parameter DomainName is malformed.|域名不存在或不属于当前用户。请检查您填写的域名书写是否正确，或者域名是否在当前账号中，查看域名是否过期。|
|400|InvalidSourceType.Malformed|The specific value of parameter SourceType is malformed.|参数SourceType格式错误。|
|400|InvalidSources.Malformed|The specific value of parameter Sources is malformed.|参数Sources格式错误。可以是IP或域名；IP支持最多20个，以逗号区分，域名只能输入一个。IP与域名不能同时输入。|
|400|InvalidSourcePort.Malformed|Specified port is not supported.|不支持参数port。|
|400|InvalidResourceGroupId.Malformed|Specified ResourceGroupId is malformed.|参数 ResourceGroupId格式错误。|
|400|EntityNotExists.ResourceGroup|The resource group does not exist.|资源组不存在。|
|400|InvalidStatus.ResourceGroup|It's now allowed to do this operation because of the current status of resource-group.|资源组当前状态不允许进行此操作。|
|400|InvalidPriorities.Malformed|The length of priorities is not the same with source.|优先级的个数与源站个数不一致。|
|400|InvalidTopLevelDomain.Malformed|Specified TopLevelDomain is malformed.|参数 TopLevelDomain 错误。|
|400|TopLevelDomain.NotFound|TopLevelDomain is not exist.|TopLevelDomain 不存在。|
|403|DomainInProtectedMode|This domain is in the protected mode. if you want to do this operation, please contact us!|此域名处于被保护模式。如果您想做这个操作，请联系我们。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

