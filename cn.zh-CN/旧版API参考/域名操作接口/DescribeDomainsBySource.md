# DescribeDomainsBySource {#doc_api_Cdn_DescribeDomainsBySource .reference}

调用DescribeDomainsBySource接口查询用户名下源站对应的所有域名名称列表

-   不支持模糊匹配。
-   支持多个源站查询，源站用逗号隔开。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainsBySource&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainsBySource|操作接口名，系统规定参数。取值：**DescribeDomainsBySource**。

 |
|Sources|String|是|aaa.source.com|源站，多个源站用逗号隔开。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|B0F074E5-A1AC-4B32-8EA2-6F450410D1E0|请求ID

 |
|Sources|String|aaa.source.com,b.source.com|请求的源站

 |
|DomainsList| | |由**DomainsData**组成的数组格式，返回各个源站对应的域名名称列表。

 |
|Source|String|b.source.com|请求的一个源站

 |
|Domains| |b1.com|由**domainNames**组成的list格式，返回单个域名对应的域名名称列表。

 |
|DomainInfos| | |由**domainInfo**组成的list格式，返回域名的详细信息。

 |
|DomainName|String|b1.com|域名

 |
|Status|String|online|域名状态

 |
|CreateTime|String|2016-07-12T11:53:19+08:00|创建时间

 |
|UpdateTime|String|2017-03-31T04:49:00+08:00|更新时间

 |
|DomainCname|String|b1.com.w.alikunlun.com|**Cname** |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainsBySource
&Sources=aaa.source.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
	  <DomainsList>
		    <DomainsData>
			      <Source>aaa.source.com	</Source>
			      <Domains></Domains>
			      <DomainInfos></DomainInfos>
		    </DomainsData>
	  </DomainsList>
	  <RequestId>A936F8E2-DA7E-4482-A749-33F3DF999D71</RequestId>
	  <Sources>aaa.source.com	</Sources>
</APINAMEResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DomainsList":{
		"DomainsData":[
			{
				"Source":"aaa.source.com\t",
				"Domains":{
					"domainNames":[]
				},
				"DomainInfos":{
					"domainInfo":[]
				}
			}
		]
	},
	"RequestId":"A936F8E2-DA7E-4482-A749-33F3DF999D71",
	"Sources":"aaa.source.com\t"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The parameter Sources miss.|参数Sources缺失。|
|400|InvalidSources.Malformed|Specified Sources is malformed.|参数Sources格式错误。可以是IP或域名；IP支持最多20个，以逗号区分，域名只能输入一个。IP与域名不能同时输入。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

