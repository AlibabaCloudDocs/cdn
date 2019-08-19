# DescribeUserDomains {#doc_api_Cdn_DescribeUserDomains .reference}

调用DescribeUserDomains接口查询用户名下所有的域名与状态。

支持域名模糊匹配过滤和域名状态过滤。域名状态包括：

-   运行中（表示域名服务状态正常，可以使用）
-   已停止
-   配置中
-   配置失败
-   审核中
-   审核失败

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeUserDomains&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeUserDomains|操作接口名，系统规定参数。取值：**DescribeUserDomains**。

 |
|CdnType|String|否|web|cdn业务类型，多个用逗号（,）隔开。

 |
|CheckDomainShow|Boolean|否|true|是否显示审核状态域名。

 |
|DomainName|String|否|www.yourdomain.com|域名模糊匹配过滤。

 |
|DomainSearchType|String|否|fuzzy\_match|域名查询类型：

 -   **fuzzy\_match**：模糊匹配。
-   **pre\_match**：前匹配。
-   **suf\_match**：后匹配。
-   **full\_match**： 完全匹配。

 默认值：**fuzzy\_match**。

 |
|DomainStatus|String|否|online|域名状态过滤。

 |
|FuncFilter|String|否|config|过滤。取值：

 -   **config**：已开通**funcid**。
-   **unconfig**：未开通**funcid**。

 |
|FuncId|String|否|98|功能ID，例如图片鉴黄功能98。

 |
|PageNumber|Integer|否|1|取得第几页。

 取值范围：1~100000。

 |
|PageSize|Integer|否|20|分页大小。

 取值范围：1~50之间的任意整数。

 默认值：20。

 |
|ResourceGroupId|String|否|your resourceGroupId|资源组ID。

 |
|Sources|String|否|a.b.com|根据回源地址查询。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|AA75AADB-5E25-4970-B480-EAA1F5658483|请求ID。

 |
|PageNumber|Long|1|返回数据的页码。

 |
|PageSize|Long|5|整页大小。

 |
|TotalCount|Long|16|总条数。

 |
|Domains| | |域名列表信息。

 |
|DomainName|String|onlytest.cdnpe.com|加速域名名称。

 |
|Cname|String|onlytest.cdnpe.com.w.alikunlun.net|加速域名对应的CNAME域名。

 |
|CdnType|String|video|加速业务类型。取值：

 -   **web**：图片小文件加速。
-   **download**：大文件下载加速。
-   **video**：视音频点播加速。
-   **livestream**：直播流媒体加速。
-   **httpsdelivery**：HTTPS安全加速。

 |
|DomainStatus|String|online|加速域名状态。取值：

 -   **online**：启用。
-   **offline**：停用。
-   **configuring**：配置中。
-   **configure\_failed**：配置失败。
-   **checking**：正在审核。
-   **check\_failed**：审核失败。

 |
|GmtCreated|String|2015-10-28T09:31:59Z|加速域名创建时间。

 |
|GmtModified|String|2015-10-28T11:05:50Z|加速域名修改时间。

 |
|Description|String|audit failed|审核失败原因。

 |
|ResourceGroupId|String|abcd1234abcd1234|资源组ID。

 |
|Sandbox|String|（空）|沙箱。

 |
|SourceType|String|oss|源站类型。

 |
|Sources| |\{ "Source": \[ "a.b.com" \] \}|源站信息。

 |
|SslProtocol|String|on|开关。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com?Action=DescribeUserDomains
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUserDomainsResponse>
      <PageNumber>1</PageNumber>
      <TotalCount>16</TotalCount>
      <PageSize>5</PageSize>
      <RequestId>851C35CB-27B0-49D9-A567-1D64324F0FB0</RequestId>
      <Domains>
            <PageData>
                  <CdnType>download</CdnType>
                  <DomainStatus>configure_failed</DomainStatus>
                  <DomainName>example.com</DomainName>
                  <GmtModified>2015-10-28T11:05:52Z</GmtModified>
                  <GmtCreated>2015-10-28T09:32:51Z</GmtCreated>
                  <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
            </PageData>
            <PageData>
                  <CdnType>web</CdnType>
                  <DomainStatus>configure_failed</DomainStatus>
                  <DomainName>example1.com</DomainName>
                  <GmtModified>2015-10-28T11:05:50Z</GmtModified>
                  <GmtCreated>2015-10-28T09:31:59Z</GmtCreated>
                  <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
            </PageData>
            <PageData>
                  <Cname>example2.com.w.alikunlun.net</Cname>
                  <CdnType>video</CdnType>
                  <DomainStatus>online</DomainStatus>
                  <DomainName>example2.com</DomainName>
                  <GmtModified>2015-10-27T06:26:34Z</GmtModified>
                  <GmtCreated>2015-10-23T09:30:00Z</GmtCreated>
                  <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
            </PageData>
            <PageData>
                  <Cname>example3.com.w.kunlunAr.com</Cname>
                  <CdnType>video</CdnType>
                  <DomainStatus>online</DomainStatus>
                  <DomainName>example3.com</DomainName>
                  <GmtModified>2015-10-23T09:23:29Z</GmtModified>
                  <GmtCreated>2015-10-23T09:23:20Z</GmtCreated>
                  <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
            </PageData>
            <PageData>
                  <Cname>example4.com.w.alikunlun.com</Cname>
                  <CdnType>video</CdnType>
                  <DomainStatus>online</DomainStatus>
                  <DomainName>example4.com</DomainName>
                  <GmtModified>2015-10-23T09:02:11Z</GmtModified>
                  <GmtCreated>2015-10-23T09:01:57Z</GmtCreated>
                  <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
            </PageData>
      </Domains>
</DescribeUserDomainsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":16,
	"PageSize":5,
	"RequestId":"AA75AADB-5E25-4970-B480-EAA1F5658483",
	"Domains":{
		"PageData":[
			{
				"Description":"audit failed",
				"CdnType":"download",
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"configure_failed",
				"DomainName":"example.com",
				"GmtModified":"2015-10-28T11:05:52Z",
				"GmtCreated":"2015-10-28T09:32:51Z"
			},
			{
				"CdnType":"web",
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"configure_failed",
				"DomainName":"example1.com",
				"GmtModified":"2015-10-28T11:05:50Z",
				"GmtCreated":"2015-10-28T09:31:59Z"
			},
			{
				"Cname":"example2.com.w.alikunlun.net",
				"CdnType":"video",
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"online",
				"DomainName":"example2.com",
				"GmtModified":"2015-10-27T06:26:34Z",
				"GmtCreated":"2015-10-23T09:30:00Z"
			},
			{
				"Cname":"example3.com.w.kunlunAr.com",
				"CdnType":"video",
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"online",
				"DomainName":"example3.com",
				"GmtModified":"2015-10-23T09:23:29Z",
				"GmtCreated":"2015-10-23T09:23:20Z"
			},
			{
				"Cname":"example4.com.w.alikunlun.com",
				"CdnType":"video",
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"online",
				"DomainName":"example4.com",
				"GmtModified":"2015-10-23T09:02:11Z",
				"GmtCreated":"2015-10-23T09:01:57Z"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidPageNumber.ValueNotSupported|The specified value of parameter PageNumber is not supported.|指定查询的当前页码参数值不合法。|
|400|InvalidPageSize.ValueNotSupported|The specified value of parameter PageSize is not supported.|指定查询的分页大小参数PageSize值不合法。|
|400|InvalidDomainStatus.ValueNotSupported|The specified value of parameter DomainStatus is not supported.|不支持参数DomainStatus。|
|400|InvalidCdnType.ValueNotSupported|The specified value of parameter CdnType is not supported.|参数CdnType不支持该参数值， 取值：web：图片及小文件分发；download：大文件下载加速；video：视音频点播加速；liveStream：直播流媒体加速。|
|400|InvalidDomainName.Malformed|The specific value of parameter DomainName is malformed.|域名不存在或不属于当前用户。请检查您填写的域名书写是否正确，或者域名是否在当前账号中，查看域名是否过期。|
|400|InvalidDomainSearchType.ValueNotSupported|The specified value of parameter DomainSearchType is not supported.|不支持参数DomainSearchType。|
|400|MissingParameter|Missing Parameter.|缺少参数。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

