# DescribeCdnDomainDetail {#reference2293 .reference}

调用DescribeCdnDomainDetail获取指定加速域名配置的基本信息。

## 调试 {#section_c8r_h64_2ru .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnDomainDetail)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_25m_1p7_e6o .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeCdnDomainDetail。|
|DomainName|String|是|需要接入CDN的域名。|

## 返回参数 {#section_jpf_k0w_n6e .section}

|参数|类型|描述|
|:-|:-|:-|
|DomainName|String|接入CDN进行加速的域名。|
|Cname|String|为加速域名生成的一个CNAME域名，需要在域名解析服务商处将加速域名CNAME解析到该域名。|
|HttpsCname|String|开启https的CNAME域名。|
|DomainStatus|String|加速域名运行状态。 取值范围： -   online：启用。
-   offline：停用。
-   configuring：配置中。
-   configure\_failed：配置失败。
-   checking：正在审核。
-   check\_failed：审核失败。

 |
|ServerCertificateStatus|String|是否开启ssl证书。 -   on：开启。
-   off：关闭。

 |
|GmtCreated|String|创建时间。|
|GmtModified|String|最近修改时间。|
|ResourceGroupId|String|资源组id。|
|Description|String|备注。|
|Scope|String|范围。|
|SourceModels|SourceModel\[\]|源站信息。|

SourceModel

|参数|类型|描述|
|:-|:-|:-|
|Content|String|回源地址。|
|Type|String|源站类型。取值： -   ipaddr：IP源站。
-   domain：域名源站。
-   oss：OSS Bucket为源站。

 |
|Port|Integer|端口，支持443和80。|
|Enabled|String|状态。|
|Priority|String|优先级。|
|Weight|String|回源权重。|

## 示例 {#section_w01_vy2_t2x .section}

请求示例

``` {#codeblock_pqx_3zc_fyb}
http://cdn.aliyuncs.com?Action=DescribeCdnDomainDetail&DomainName=example.com&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_a51_uuz_5wv .language-json}
{
  "GetDomainDetailModel": {
    "Cname": "example.com.w.kunlunle.com",
    "DomainName": "example.com",
    "DomainStatus": "online",
    "GmtCreated": "2015-06-25T03:30:50Z",
    "GmtModified": "2015-06-25T03:30:53Z",
    "HttpsCname": "example.com.alikunlun.com",
    "ResourceGroupId":"abcd1234abcd1234",
    "SourceModels": {
        "SourceModel": [
            {
             "Enabled": "online",
             "Port": 80,
             "Type": "domain",
             "Content": "example.com",
             "Priority": "20",
             "Weight": "10"
             }
           ]
            }
  },
  "RequestId": "18CF38AA-1275-451D-A12B-4EC0BF1C5E30"
}
```

