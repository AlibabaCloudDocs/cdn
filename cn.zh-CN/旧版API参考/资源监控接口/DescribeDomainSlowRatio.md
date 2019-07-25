# DescribeDomainSlowRatio {#doc_api_Cdn_DescribeDomainSlowRatio .reference}

调用DescribeDomainSlowRatio接口获取视频加速域名5分钟维度的慢速比数据。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   不支持批量域名查询。
-   最多可获取最近30天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainSlowRatio&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainSlowRatio|操作接口名，系统规定参数。取值：**DescribeDomainSlowRatio**。

 |
|DomainName|String|是|test.test.com|加速域名

 |
|EndTime|String|否|2016-10-20T04:00:00Z|结束时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   起止时间和结束时间，间隔小于30天。
-   例如：2016-10-20T04:00:00Z。

 |
|PageNumber|Integer|否|1|页号，从1开始。

 |
|PageSize|Integer|否|20|每页大小。

 |
|StartTime|String|否|2016-10-20T04:00:00Z|起始时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|Integer|300|时间间隔。单位：秒。

 |
|EndTime|String|017-09-30T16:00:00Z|结束时间

 |
|PageNumber|Integer|1|当前页码，从1开始计数。

 |
|PageSize|Integer|20|页大小

 |
|StartTime|String|017-09-30T16:00:00Z|起始时间

 |
|TotalCount|Integer|2|慢速比数据条数

 |
|SlowRatioDataPerInterval| | |慢速比数据列表

 |
|IspNameEn|String|unicom|运营商英文信息

 |
|IspNameZh|String|联通|运营商中文信息

 |
|RegionNameEn|String|beijing|地区英文信息

 |
|RegionNameZh|String|北京市|地区中文信息

 |
|SlowRatio|Float|0.2|慢速比例

 |
|SlowUsers|Integer|3|慢速用户数

 |
|Time|String|2017-09-30T16:00:00Z|时间点

 |
|TotalUsers|Integer|15|总用户数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainSlowRatio
&DomainName=test.test.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
	  <DataInterval>300</DataInterval>
	  <EndTime>2017-09-30T17:00:00Z</EndTime>
	  <PageNumber>1</PageNumber>
	  <PageSize>20</PageSize>
	  <SlowRatioDataPerInterval>
		    <SlowRatioData>
			      <IspNameEn>telecom</IspNameEn>
			      <IspNameZh>电信</IspNameZh>
			      <RegionNameEn>guangdong</RegionNameEn>
			      <RegionNameZh>广东省</RegionNameZh>
			      <SlowRatio>0.1</SlowRatio>
			      <SlowUsers>2</SlowUsers>
			      <Time>2017-09-30T16:00:00Z</Time>
			      <TotalUsers>20</TotalUsers>
		    </SlowRatioData>
		    <SlowRatioData>
			      <IspNameEn>unicom</IspNameEn>
			      <IspNameZh>联通</IspNameZh>
			      <RegionNameEn>beijing</RegionNameEn>
			      <RegionNameZh>北京市</RegionNameZh>
			      <SlowRatio>0.2</SlowRatio>
			      <SlowUsers>3</SlowUsers>
			      <Time>2017-09-30T16:00:00Z</Time>
			      <TotalUsers>15</TotalUsers>
		    </SlowRatioData>
	  </SlowRatioDataPerInterval>
	  <StartTime>2017-09-30T16:00:00Z</StartTime>
	  <TotalCount>2</TotalCount>
</APINAMEResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":2,
	"SlowRatioDataPerInterval":{
		"SlowRatioData":[
			{
				"SlowUsers":2,
				"Time":"2017-09-30T16:00:00Z",
				"RegionNameEn":"guangdong",
				"IspNameZh":"电信",
				"TotalUsers":20,
				"SlowRatio":0.1,
				"IspNameEn":"telecom",
				"RegionNameZh":"广东省"
			},
			{
				"SlowUsers":3,
				"Time":"2017-09-30T16:00:00Z",
				"RegionNameEn":"beijing",
				"IspNameZh":"联通",
				"TotalUsers":15,
				"SlowRatio":0.2,
				"IspNameEn":"unicom",
				"RegionNameZh":"北京市"
			}
		]
	},
	"DataInterval":300,
	"PageSize":20,
	"EndTime":"2017-09-30T17:00:00Z",
	"StartTime":"2017-09-30T16:00:00Z"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

