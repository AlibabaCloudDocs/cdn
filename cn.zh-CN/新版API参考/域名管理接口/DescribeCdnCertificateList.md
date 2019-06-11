# DescribeCdnCertificateList {#reference1754 .reference}

调用DescribeCdnCertificateList获取证书列表信息。

## 调试 {#section_erh_s83_so7 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnCertificateList)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_l3n_em6_jtl .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeCdnCertificateList。|
|DomainName|String|否|域名。|

## 返回参数 {#section_0ca_j9w_tn1 .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|RequestId。|
|CertificateListModel|CertificateListModel类型|证书id。|

数据类型CertificateListModel

|名称|类型|描述|
|:-|:-|:-|
|Count|Integer|证书个数。|
|CertList|Cert|证书列表信息。|

数据类型Cert

|名称|类型|描述|
|:-|:-|:-|
|CertName|String|证书名称。|
|CertId|Long|证书id。|
|Fingerprint|String|—|
|Common|String|—|
|Issuer|String|证书发行商。|
|LastTime|Long|时间。|

## 示例 {#section_238_03l_kks .section}

请求示例

``` {#codeblock_a4n_7hm_59w}
http://cdn.aliyuncs.com?Action=DescribeCdnCertificateList&DomainName=xxx&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_80x_2c7_tg6 .language-json}
{
    "CertificateListModel": {
        "Count": 2,
        "CertList": {
            "Cert": [
                {
                    "CertName": "证书1",
                    "Issuer": "xxx",
                    "LastTime": 1512388610,
                    "CertId": xxx,
                    "Common": "test",
                    "Fingerprint": "xxx"
                },
                {
                    "CertName": "证书2",
                    "Issuer": "xxx",
                    "LastTime": 1512388659,
                    "CertId": xxx,
                    "Common": "test",
                    "Fingerprint": "xxx"
                }
            ]
        }
    },
    "RequestId": "FC0E34AC-0239-44A7-AB0E-800DE522C8DA"
}
```

