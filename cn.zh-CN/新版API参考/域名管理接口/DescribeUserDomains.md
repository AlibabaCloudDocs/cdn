# DescribeUserDomains {#reference_yct_d2r_dgb .reference}

调用DescribeUserDomains查询用户名下所有的域名与状态。支持域名模糊匹配过滤和域名状态过滤。

域名状态包括：

-   运行中（表示域名服务状态正常）。
-   已停止。
-   配置中。
-   配置失败。
-   审核中。
-   审核失败。

## 调试 {#section_md5_4us_8xo .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeUserDomains)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_m4h_m2r_dgb .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeUserDomains。|
|PageSize|Long|否|分页大小。默认值：20；最大值：50；取值：1~50之间的任意整数。|
|PageNumber|Long|否|取得第几页，取值范围：1~100000。|
|DomainName|String|否|域名模糊匹配过滤。|
|DomainSearchType|String|否|域名查询类型。 -   fuzzy\_match：模糊匹配。
-   pre\_match：前匹配。
-   suf\_match：后匹配。
-   full\_match：完全匹配。

 默认：fuzzy\_match。

 |
|CdnType|String|否|cdn业务类型，多个用逗号隔开。|
|DomainStatus|String|否|域名状态过滤。|
|ResourceGroupId|String|否|资源组id。|
|FuncFilter|String|否|过滤，支持config和unconfig。 -   config：开通了funcid。
-   unconfig：未开通funcid。

 |
|FuncId|String|否|funcid，如图片鉴黄功能98。|

## 返回参数 {#section_y4g_n2r_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|PageNumber|Long|返回数据的页码。|
|PageSize|Long|整页大小。|
|TotalCount|Long|总条数。|
|Domains|Domains|由Domains组成的数组格式，返回加速域名的状态信息。|

数据类型Domains

|名称|类型|描述|
|:-|:-|:-|
|DomainName|String|加速域名名称。|
|Cname|String|加速域名对应的CNAME域名。|
|DomainStatus|String|加速域名状态，取值范围： -   online：启用。
-   offline：停用。
-   configuring：配置中。
-   configure\_failed：配置失败。
-   checkingring：正在审核。
-   check\_failed：审核失败。

 |
|CdnType|String|加速业务类型，取值范围： -   web：图片小文件加速。
-   download：大文件下载加速。
-   video：视音频点播加速。
-   livestream：直播流媒体加速。
-   httpsdelivery：HTTPS安全加速。

 |
|GmtCreated|String|加速域名创建时间。|
|GmtModified|String|加速域名修改时间。|
|Description|String|审核失败原因。|
|ResourceGroupId|String|资源组id。|
|SslProtocol|String|https开关。 -   on：已开启。
-   off：未开启。

 |
|Sources|Source\[\]|源站信息。|

数据类型Source

|名称|类型|描述|
|:-|:-|:-|
|Type|String|源站类型。|
|Content|String|源站地址。|
|Port|Integer|源站端口。|
|Priority|String|优先级。|
|Weight|String|回源权重。|

## 示例 {#section_wkp_w2r_dgb .section}

请求示例

``` {#codeblock_fnu_kto_0qj}
https://cdn.aliyuncs.com?&Action=DescribeUserDomains&PageNumber=1&PageSize=5&DomainSearchType=fuzzy_match&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_uq9_xb7_nqs}
{
   "PageNumber": 1,
   "TotalCount": 16,
   "PageSize": 5,
   "RequestId": "AA75AADB-5E25-4970-B480-EAA1F5658483",
   "Domains": {
     "PageData": [
       {
         "CdnType": "download",
         "DomainStatus": "configure_failed",
         "DomainName": "example.com",
         "GmtModified": "2015-10-28T11:05:52Z",
         "GmtCreated": "2015-10-28T09:32:51Z",
         "Description": "audit failed",
         "ResourceGroupId":"abcd1234abcd1234"
       },
       {
         "CdnType": "web",
         "DomainStatus": "configure_failed",
         "DomainName": "aadda.cdnpe.com",
         "GmtModified": "2015-10-28T11:05:50Z",
         "GmtCreated": "2015-10-28T09:31:59Z",
         "ResourceGroupId":"abcd1234abcd1234"
       },
       {
         "Cname": "example.com.w.alikunlun.net",
         "CdnType": "video",
         "DomainStatus": "online",
         "DomainName": "example.com",
         "GmtModified": "2015-10-27T06:26:34Z",
         "GmtCreated": "2015-10-23T09:30:00Z",
         "ResourceGroupId":"abcd1234abcd1234"
       },
       {
         "Cname": "example.com.w.kunlunAr.com",
         "CdnType": "video",
         "DomainStatus": "online",
         "DomainName": "example.com",
         "GmtModified": "2015-10-23T09:23:29Z",
         "GmtCreated": "2015-10-23T09:23:20Z",
         "ResourceGroupId":"abcd1234abcd1234"
       },
       {
         "Cname": "example.com.w.alikunlun.com",
         "CdnType": "video",
         "DomainStatus": "online",
         "DomainName": "example.com",
         "GmtModified": "2015-10-23T09:02:11Z",
         "GmtCreated": "2015-10-23T09:01:57Z",
         "ResourceGroupId":"abcd1234abcd1234"
       }
     ]
   }
 }
```

## 错误码 {#section_tjp_w2r_dgb .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidPageNumber.ValueNotSupported|The specified value of parameter PageNumber is not supported.|400|输入的PageNumber参数值不支持。|
|InvalidPageSize.ValueNotSupported|The specified value of parameter PageSize is not supported.|400|输入的PageSize参数值不支持。|
|InvalidDomainName.Malformed|The specific value of parameter DomainName is malformed.|400|输入的DomainName参数值不支持。|
|InvalidDomainStatus.ValueNotSupported|The specified value of parameter DomainStatus is not supported.|400|输入的DomainStatus参数值不支持。|
|InvalidDomainSearchType.ValueNotSupported|The specified value of parameter DomainSearchType is not supported.|400|输入的DomainSearchType参数值不支持。|

