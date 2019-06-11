# DescribeDomainCertificateInfo {#reference2279 .reference}

调用DescribeDomainCertificateInfo获取指定加速域名证书信息。

## 调试 {#section_dx0_4m1_50d .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeDomainCertificateInfo)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_426_kr3_fa9 .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数 ，取值：DescribeDomainCertificateInfo。|
|DomainName|String|是|CDN加速域名。|

## 返回参数 {#section_ksz_t4z_135 .section}

|名称|类型|描述|
|:-|:-|:-|
|CertInfos|CertInfo\[\]|证书信息。|

CertInfo

|名称|类型|描述|
|:-|:-|:-|
|DomainName|String|加速域名。|
|CertName|String|证书名称。|
|CertDomainName|String|证书匹配的域名。|
|CertStartTime|String|证书开始时间。|
|CertUpdateTime|String|证书更新时间。|
|CertExpireTime|String|证书过期时间。|
|CertLife|String|证书时长，单位： -   months：月。
-   years：年。

 |
|CertType|String|证书类型。 -   free：免费证书。
-   cas：云盾证书。
-   upload：自定义上传。

 |
|ServerCertificateStatus|String|https开启状态。 -   on：已开启。
-   off：未开启。

 |
|Status|String|证书状态。 -   success：已生效。
-   checking：检测域名是否在阿里云CDN。
-   cname\_error：域名没有切到阿里云CDN。
-   top\_domain\_cname\_error：顶级域名没有切到阿里云CDN。
-   domain\_invalid：域名包含非法字符。
-   unsupport\_wildcard：不支持泛域名。
-   applying：证书申请中。
-   get\_token\_timeout：证书申请超时。
-   check\_token\_timeout：校验超时。
-   get\_cert\_timeout：获取证书超时。
-   failed：证书申请失败。

 |
|ServerCertificate|String|证书公钥。|
|DomainCnameStatus|String|域名cname状态如下： -   ok：域名cname已切到阿里云CDN。
-   cname\_error ：域名cname错误，没有切到阿里云CDN。
-   top\_domain\_cname\_error：域名cname错误，没有切到阿里云CDN。
-   unsupport\_wildcard：不支持泛域名。

 |

## 示例 {#section_4tt_1hl_sro .section}

请求示例

``` {#codeblock_rs9_qxf_bu1}
http://cdn.aliyuncs.com?Action=DescribeDomainCertificateInfo&DomainName=example.com&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_tay_n6m_1vf .language-json}
{
  "CertInfos": {
    "CertInfo": [
      {
        "Status": "success",
        "CertLife": "3 months",
        "ServerCertificateStatus": "on",
        "CertType": "cas",
        "CertName": "example.com",
        "CertDomainName": "example.com",
        "DomainName": "example.com",
        "CertOrg": "Let's Encrypt",
        "CertExpireTime": "2018-06-03T22:03:39Z"
      }
    ]
  },
  "RequestId": "5C1E43DC-9E51-4771-82C0-7D5ECEB547A1"
}
```

## 错误码 {#section_ckh_27i_zt1 .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|

