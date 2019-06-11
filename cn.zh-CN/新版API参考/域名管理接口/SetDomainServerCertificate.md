# SetDomainServerCertificate {#reference_l1t_pjl_vdb .reference}

调用SetDomainServerCertificate该接口用于设置某域名下证书功能是否启用及修改证书信息。

## 调试 {#section_fs9_1kq_6k7 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=SetDomainServerCertificate)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_bcw_rjl_vdb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：SetDomainServerCertificate。|
|DomainName|String|是|指定证书所属加速域名 需属于https加速类型。|
|ServerCertificateStatus|String|是|HTTPS证书是否启用。取值范围： -   on：启用。
-   off：不启用。

 默认值：off。

 |
|ServerCertificate|String|否|安全证书内容，不启用证书则无需输入，配置证书请输入证书内容。|
|PrivateKey|String|否|私钥内容，不启用证书则无需输入，配置证书请输入私钥内容。|
|CertType|String|否| -   upload：上传证书。
-   cas：证书中心证书。
-   free：免费证书。

 |
|CertName|String|否|证书名称。|
|ForceSet|String|否|设置为1时，忽略证书名称重复的校验，覆盖原有同名证书信息。|

## 返回参数 {#section_nrn_yjl_vdb .section}

|参数|类型|描述|
|:-|:-|:-|
|RequestID|String|公共返回参数。|

## 示例 {#section_g1p_gcg_vdb .section}

请求示例

``` {#codeblock_e1z_qo5_zgj}
http://cdn.aliyuncs.com?Action=SetDomainServerCertificate&DomainName=test.com&CertName=myCert1&ServerCertificateStatus=on&ServerCertificate=xxx&PrivateKey=yyy&公共请求参数
```

正常返回示例

`JSON`格式

``` {#codeblock_n0g_e87_z6b}
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码 {#section_ug4_mpr_dgb .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|IllegalOperation|Illegal domain operate is not permitted.|403|没有权限执行当前操作。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中，请稍后再试。|
|InvalidDomain.Offline|The domain provided is offline.|400|域名已下线。|
|OperationDenied|Your CDN service is suspended.|403|该账号已经欠费，请充值。|
|InvalidServerCertificateStatus.ValueNotSupported|The specified value of parameter Enable is not supported.|400|ServerCertificateStatus的值不合法。|
|ServerCertificate.MissingParameter|An input parameter ServerCertificate that is mandatory for processing the request is not supplied.|400|ServerCertificate参数缺失。|
|PrivateKey.MissingParameter|An input parameter PrivateKey that is mandatory for processing the request is not supplied.|400|PrivateKey参数缺失。|
|InvalidCertificate|The Certificate you provided is malformed!|400|证书内容不合法。|
|InvalidPrivateKey|The Private Key you provided is malformed!|400|私钥内容不合法。|
|Certificate.MissMatch|The Private Key does not math the specified Certificate!|400|证书和私钥不匹配。|
|InvalidCertificate.TooLong|The Certificate you provided is over the max length!|400|证书内容超过长度限制。|
|InvalidCertName.TooLong|The Certificate name you provided is over the max length 128!|400|证书名称不能超过128个字符。|
|SetDomainServerCertificate.ParameterError|Parameters have error.|400|参数错误。|
|Certificate.StatusError|Certificate is not exist or its status is error.|400|证书不存在或证书状态错误。|
|DeleteFailed|Delete certificate is failed.|400|删除证书失败。|
|Certificate.NotFind|Not find the certificate info.|400|没有查到相应证书。|
|Certificate.Duplicated|The certificate name is duplicated.|400|证书名称重复。|
|Certificate.FormatError|The certificate format is error.|400|证书格式错误。|
|Certificate.StatusError|The certificate status is error.|400|证书状态错误。|
|Certificate.KeyNull|The private key is not null.|400|私钥不能为空。|
|Key.Malformed|The private key format is error.|400|私钥格式错误。|
|Certificate.NotPermittedOff|Turn off certificate will change domain scheduling, please contact customer service.|400|关闭证书会影响该域名调度，请联系客服调整。|
|Certificate.SettedNotEffect|Certificate was successfully setted but does't take effect for protecting current service, please contact customer service.|400|证书已经设置成功，但为保护当前服务还未生效，请联系客服处理。|

