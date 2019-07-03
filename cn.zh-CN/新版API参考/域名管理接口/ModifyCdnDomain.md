# ModifyCdnDomain {#reference2756 .reference}

调用ModifyCdnDomain修改加速域名。

**说明：** 创建加速域名之前，您需要[../../../../dita-oss-bucket/SP\_19/DNCDN11886185/ZH-CN\_TP\_5108\_V7.md\#](../../../../cn.zh-CN/快速入门/开通CDN服务.md#)。

## 调试 {#section_tzh_t0i_f0s .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=ModifyCdnDomain)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_2yf_q0q_c99 .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：ModifyCdnDomain。|
|DomainName|String|是|需要接入CDN的域名。|
|Sources|Json|否|回源地址列表。|
|ResourceGroupId|String|否|资源组id。|
|TopLevelDomain|String|否|顶级接入域。|

Sources格式

\[\{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80,"weight":"15"\}\]

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

## 示例 {#section_gwz_nzi_9o5 .section}

请求示例

``` {#codeblock_sbl_it1_0s0}
http://cdn.aliyuncs.com?Action=ModifyCdnDomain&SourceType=domain&DomainName=example.com&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80}]&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_jud_u36_so7}
{
  "RequestId": "15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## 错误码 {#section_53m_pes_ui6 .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidDomainName.Malformed|Specified DomainName is malformed.|400|DomainName参数错误。|
|InvalidSource.Content.Malformed|Specified source content is malformed.|400|回源地址参数错误。|
|InvalidSource.Type.Malformed|Specified source type is malformed.|400|源站类型参数错误。|
|InvalidTypeContent.Mismatch|Specified source type does not math the specified source content.|400|回源地址与回源类型不匹配。|
|InvalidSource.Priority.Malformed|Specified source priority is malformed.|400|优先级参数错误。|
|InvalidScope.Malformed|Specified Scope is malformed.|400|Scope参数错误。|
|IllegalOperation|Illegal domain operate is not permitted.|403|没有权限执行当前操作。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|Abs.resourceGroupId.Malformed|Specified ResourceGroupId is malformed.|400|资源组id参数不正确。|
|EntityNotExists.ResourceGroup|The resource group does not exist.|400|资源组不存在。|
|InvalidStatus.ResourceGroup|It's now allowed to do this operation because of the current status of resource-group.|400|资源组状态检查失败。|

CDN所有API错误码，详情请参见[CDN错误码](https://error-center.aliyun.com/status/product/Cdn)。

