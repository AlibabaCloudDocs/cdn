# DescribeDomainQpsData {#doc_api_Cdn_DescribeDomainQpsData .reference}

调用DescribeDomainQpsData获取加速域名的每秒访问次数QPS。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。同时指定StartTime和EndTime时，按指定的起止时间查询。
-   支持批量域名查询，多个域名用逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainQpsData&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDomainQpsData|操作接口名，系统规定参数。取值：**DescribeDomainQpsData**。

 |
|DomainName|String|否|test.test.com|如果参数为空，默认返回所有加速域名合并后数据。

 可输入需要查询的加速域名。支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2015-12-10T21:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Interval|String|否|300|查询数据的时间粒度，支持**300**、 **3600**和**86400**秒。

 -   3天以内（不包含3天整）支持**300**、**3600**、 **86400**。
-   3-31天（不包含31天整）支持**3600**和**86400**。
-   31天以上支持**86400**。

 不传和传的值不支持时，使用默认值。

 |
|IspNameEn|String|否|unicom|运营商英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得，不传为所有区域。

 |
|StartTime|String|否|2015-12-10T20:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟，不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|test.test.com|加速域名信息。

 |
|EndTime|String|2015-12-10T21:00Z|结束时间。

 |
|QpsDataInterval| | |每个时间间隔的每秒访问次数Qps。

 |
|AccDomesticValue|String|0|国内访问次数。

 |
|AccOverseasValue|String|0|海外访问次数。

 |
|AccValue|String|0|总访问次数。

 |
|DomesticValue|String|0|国内QPS。

 |
|HttpsAccDomesticValue|String|1|L1节点国内https请求数。

 |
|HttpsAccOverseasValue|String|1|L1节点海外https请求数。

 |
|HttpsAccValue|String|1|L1节点https请求数。

 |
|HttpsDomesticValue|String|1|L1节点https国内QPS值。

 |
|HttpsOverseasValue|String|1|L1节点https海外QPS值。

 |
|HttpsValue|String|1|L1节点https的QPS值。

 |
|OverseasValue|String|0|海外QPS。

 |
|TimeStamp|String|2015-12-10T21:00:00Z|时间片起始时刻。

 |
|Value|String|0|总QPS。

 |
|RequestId|String|B8333EDB-4595-46E0-AFE9-29BAA290D0E0|请求ID。

 |
|StartTime|String|2015-12-10T20:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainQpsData
&DomainName=test.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainQpsDataRResponse>
	  <QpsDataInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T21:00:00Z</TimeStamp>
			      <Value>0.56</Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:35:00Z</TimeStamp>
			      <Value>0.64</Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:50:00Z</TimeStamp>
			      <Value>0.4</Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:05:00Z</TimeStamp>
			      <Value>1.0033333333333334</Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
	  </QpsDataInterval>
	  <DomainName>test.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <RequestId>BEA5625F-8FCF-48F4-851B-CA63946DA664</RequestId>
	  <StartTime>2015-12-10T20:00Z</StartTime>
	  <EndTime>2015-12-10T21:00Z</EndTime>
</DescribeDomainQpsDataRResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"QpsDataInterval":{
		"DataModule":[
			{
				"TimeStamp":"2015-12-10T21:00:00Z",
				"StaticValue":"0",
				"DynamicDomesticValue":"0",
				"Value":"0.56",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DynamicValue":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:35:00Z",
				"StaticValue":"0",
				"DynamicDomesticValue":"0",
				"Value":"0.64",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DynamicValue":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:50:00Z",
				"StaticValue":"0",
				"DynamicDomesticValue":"0",
				"Value":"0.4",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DynamicValue":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:05:00Z",
				"StaticValue":"0",
				"DynamicDomesticValue":"0",
				"Value":"1.0033333333333334",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DynamicValue":"0"
			}
		]
	},
	"DataInterval":"300",
	"RequestId":"BEA5625F-8FCF-48F4-851B-CA63946DA664",
	"DomainName":"test.com",
	"EndTime":"2015-12-10T21:00Z",
	"StartTime":"2015-12-10T20:00Z"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

