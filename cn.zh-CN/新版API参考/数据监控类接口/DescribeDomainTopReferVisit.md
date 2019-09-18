# DescribeDomainTopReferVisit {#doc_api_Cdn_DescribeDomainTopReferVisit .reference}

调用DescribeDomainTopReferVisit获取加速域名某天的热门页面引用次数排名。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据；同时指定StartTime和EndTime时，按指定的起止时间查询。

-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTopReferVisit&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainTopReferVisit|操作接口名，系统规定参数，取值：**DescribeDomainTopReferVisit**。

 |
|DomainName|String|是|example.com|如果不填该参数，默认返回所有加速域名合并后数据。

 可以输入需要查询的加速域名 ，多个域名用逗号\(,\)分隔。

 |
|Percent|String|否|0.5|百分比。

 |
|SortBy|String|否|pv|排序方式。支持**traf**和**pv**，默认值：**pv**。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间，不写默认读取过去24小时数据。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|95994621-8382-464B-8762-C708E73568D1|请求ID。

 |
|DomainName|String|test.com|加速域名信息。

 |
|StartTime|String|2015-11-28|查询指定日期。

 |
|TopReferList| | |全部热门ReferUrllist。

 |
|ReferList| | |全部热门ReferUrllist。

 |
|ReferDetail|String|live-hunantv.cdnpe.com|完整的ReferUrl地址。

 |
|VisitData|String|3|访问次数。

 |
|Flow|String|200|流量。单位：byte。

 |
|FlowProportion|Float|0.5|流量占比。

 |
|VisitProportion|Float|0.5|访问占比。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainTopReferVisit
&DomainName=test.com
&StartTime=2015-11-28
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainTopReferVisitResponse>
  <TopReferList>
		    <ReferList>
			      <VisitData>229567</VisitData>
			      <ReferDetail>-</ReferDetail>
		    </ReferList>
		    <ReferList>
			      <VisitData>2496</VisitData>
			      <ReferDetail>123.57.158.8</ReferDetail>
		    </ReferList>
		    <ReferList>
			      <VisitData>448</VisitData>
			      <ReferDetail>live-hunantv.cdnpe.com</ReferDetail>
		    </ReferList>
		    <ReferList>
			      <VisitData>3</VisitData>
			      <ReferDetail>video.ccdemo.ccgslb.net</ReferDetail>
		    </ReferList>	
      </TopReferList>
	  <RequestId>95994621-8382-464B-8762-C708E73568D1</RequestId>
	  <DomainName>test.com</DomainName>
	  <StartTime>2015-11-28</StartTime>	
</DescribeDomainTopReferVisitResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TopReferList":{
		"ReferList":[
			{
				"VisitData":"229567",
				"ReferDetail":"-"
			},
			{
				"VisitData":"2496",
				"ReferDetail":"123.57.158.8"
			},
			{
				"VisitData":"448",
				"ReferDetail":"live-hunantv.cdnpe.com"
			},
			{
				"VisitData":"3",
				"ReferDetail":"video.ccdemo.ccgslb.net"
			}
		]
	},
	"RequestId":"95994621-8382-464B-8762-C708E73568D1",
	"DomainName":"test.com",
	"StartTime":"2015-11-28"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

