# DescribeDomainTrafficData {#doc_api_Cdn_DescribeDomainTrafficData .reference}

调用DescribeDomainTrafficData获取加速域名的网络流量监控数据，单位：byte。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。同时指定StartTime和EndTime时，按指定的起止时间查询。
-   支持批量域名查询，多个域名用逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTrafficData&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDomainTrafficData|操作接口名，系统规定参数，取值：**DescribeDomainTrafficData**。

 |
|DomainName|String|否|example.com|如果参数为空，默认返回所有加速域名合并后数据。

 可输入需要查询的加速域名。支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2015-12-10T21:00:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Interval|String|否|300|查询数据的时间粒度，支持300、 3600和86400秒。

 -   3天以内（不包含3天整）支持**300**、**3600**、 **86400**。
-   3-31天（不包含31天整）支持**3600**和**86400**。
-   31天以上支持**86400**。

 不传和传的值不支持时，使用默认值。

 |
|IspNameEn|String|否|beijing|运营商英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得，如果不填该参数，返回所有运营商。

 |
|LocationNameEn|String|否|unicom|区域英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得，如果不填该参数，返回所有区域。

 |
|StartTime|String|否|2015-12-10T20:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟，不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|example.com|加速域名信息。

 |
|EndTime|String|2015-12-10T21:00:00Z|结束时间。

 |
|RequestId|String|B955107D-E658-4E77-B913-E0AC3D31693E|请求ID。

 |
|StartTime|String|2015-12-10T20:00:00Z|开始时间。

 |
|TrafficDataPerInterval| | |每个时间间隔的流量数据。

 |
|DataModule| | |每个时间间隔的流量数据。

 |
|DomesticValue|String|0|国内流量。

 |
|HttpsDomesticValue|String|0|L1节点https国内流量。

 |
|HttpsOverseasValue|String|0|L1节点https海外流量。

 |
|HttpsValue|String|423304182|L1节点https总流量。

 |
|OverseasValue|String|0|海外流量。

 |
|TimeStamp|String|example.com|时间片起始时刻。

 |
|Value|String|423304182|总流量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainTrafficData
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainTrafficDataResponse>
	  <DomainName>example.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <TrafficDataPerInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>423304182</Value>
			      <DomesticValue>0</DomesticValue>
			      <OverseasValue>0</OverseasValue>
			      <HttpsValue>423304182</HttpsValue>
			      <HttpsDomesticValue>0</HttpsDomesticValue>
			      <HttpsOverseasValue>0</HttpsOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:05:00Z</TimeStamp>
			      <Value>454680793</Value>
			      <DomesticValue>0</DomesticValue>
			      <OverseasValue>0</OverseasValue>
			      <HttpsValue>423304182</HttpsValue>
			      <HttpsDomesticValue>0</HttpsDomesticValue>
			      <HttpsOverseasValue>0</HttpsOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:10:00Z</TimeStamp>
			      <Value>501718342</Value>
			      <DomesticValue>0</DomesticValue>
			      <OverseasValue>0</OverseasValue>
			      <HttpsValue>423304182</HttpsValue>
			      <HttpsDomesticValue>0</HttpsDomesticValue>
			      <HttpsOverseasValue>0</HttpsOverseasValue>
		    </DataModule>
	  </TrafficDataPerInterval>
	  <RequestId>B955107D-E658-4E77-B913-E0AC3D31693E</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T21:00:00Z</EndTime>
</DescribeDomainTrafficDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TrafficDataPerInterval":{
		"DataModule":[
			{
				"HttpsOverseasValue":"0",
				"TimeStamp":"2015-12-10T20:00:00Z",
				"Value":"423304182",
				"OverseasValue":"0",
				"HttpsDomesticValue":"0",
				"DomesticValue":"0",
				"HttpsValue":"423304182"
			},
			{
				"HttpsOverseasValue":"0",
				"TimeStamp":"2015-12-10T20:05:00Z",
				"Value":"454680793",
				"OverseasValue":"0",
				"HttpsDomesticValue":"0",
				"DomesticValue":"0",
				"HttpsValue":"423304182"
			},
			{
				"HttpsOverseasValue":"0",
				"TimeStamp":"2015-12-10T20:10:00Z",
				"Value":"501718342",
				"OverseasValue":"0",
				"HttpsDomesticValue":"0",
				"DomesticValue":"0",
				"HttpsValue":"423304182"
			}
		]
	},
	"DataInterval":"300",
	"RequestId":"B955107D-E658-4E77-B913-E0AC3D31693E",
	"DomainName":"example.com",
	"EndTime":"2015-12-10T21:00:00Z",
	"StartTime":"2015-12-10T20:00:00Z"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

