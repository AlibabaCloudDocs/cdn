# DescribeCdnDomainDetail {#doc_api_Cdn_DescribeCdnDomainDetail .reference}

调用DescribeCdnDomainDetail获取指定加速域名配置的基本信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainDetail&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnDomainDetail|操作接口名，系统规定参数。取值：**DescribeCdnDomainDetail**。

 |
|DomainName|String|是|www.yourdomain.com|需要接入CDN的域名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GetDomainDetailModel| | |域名详情。

 |
|CdnType|String|web|加速域名的业务类型。取值：

 -   **web**：片及小文件加速。
-   **download**：大文件下载加速。
-   **video**：视音频点播加速。

 |
|Cname|String|domain.w.alikunlun.net|为加速域名生成的一个CNAME域名，需要在域名解析服务商处将加速域名CNAME解析到该域名。

 |
|Description|String|直播域名|备注。

 |
|DomainName|String|yourdomain.com|接入CDN进行加速的域名。

 |
|DomainStatus|String|online|域名状态。

 |
|GmtCreated|String|2015-06-25T03:30:50Z|创建时间。

 |
|GmtModified|String|2017-06-25T03:30:50Z|最近修改时间。

 |
|HttpsCname|String|yourdomain.com.alikunlun.com|开启https的CNAME域名。

 |
|ResourceGroupId|String|abcd1234abcd1234|资源组id。

 |
|Scope|String|domestic|区域。

 |
|ServerCertificateStatus|String|on|是否开启ssl证书，**on**表示开启；**off**表示关闭。

 |
|SourceModels| | |源站信息。

 |
|SourceModel| | |源站信息。

 |
|Content|String|test.com|回源地址。

 |
|Enabled|String|online|状态。

 |
|Port|Integer|80|端口，支持443和80。

 |
|Priority|String|20|优先级。

 |
|Type|String|domain|源站类型，取值：

 -   **ipaddr**：IP源站。
-   **domain**：域名源站。
-   **oss**：OSSBucket为源站。

 |
|Weight|String|10|回源权重。

 |
|RequestId|String|18CF38AA-1275-451D-A12B-4EC0BF1C5E30|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeCdnDomainDetail&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCdnDomainDetailResponse>
	  <GetDomainDetailModel>
		    <CdnType>web</CdnType>
		    <Cname>bb.test.com.w.kunlunle.com</Cname>
		    <DomainName>bb.test.com</DomainName>
		    <DomainStatus>online</DomainStatus>
		    <GmtCreated>2015-06-25T03:30:50Z</GmtCreated>
		    <GmtModified>2015-06-25T03:30:53Z</GmtModified>
		    <HttpsCname>bb-test-com.alikunlun.com</HttpsCname>
		    <SourceType>domain</SourceType>
		    <Region>huadong</Region>
		    <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
		    <SourceModels>
			      <SourceModel>
				        <Enabled>online</Enabled>
				        <Port>80</Port>
				        <Type>domain</Type>
				        <Content>test.com</Content>
				        <Priority>20</Priority>
			      </SourceModel>
		    </SourceModels>
		    <Sources>
			      <Source>test.com</Source>
		    </Sources>
	  </GetDomainDetailModel>
	  <RequestId>18CF38AA-1275-451D-A12B-4EC0BF1C5E30</RequestId>
</DescribeCdnDomainDetailResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"GetDomainDetailModel":{
		"Cname":"bb.test.com.w.kunlunle.com",
		"Region":"huadong",
		"HttpsCname":"bb-test-com.alikunlun.com",
		"CdnType":"web",
		"SourceModels":{
			"SourceModel":[
				{
					"Enabled":"online",
					"Port":80,
					"Type":"domain",
					"Content":"test.com",
					"Priority":"20"
				}
			]
		},
		"ResourceGroupId":"abcd1234abcd1234",
		"SourceType":"domain",
		"DomainStatus":"online",
		"DomainName":"bb.test.com",
		"Sources":{
			"Source":[
				"test.com"
			]
		},
		"GmtModified":"2015-06-25T03:30:53Z",
		"GmtCreated":"2015-06-25T03:30:50Z"
	},
	"RequestId":"18CF38AA-1275-451D-A12B-4EC0BF1C5E30"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

