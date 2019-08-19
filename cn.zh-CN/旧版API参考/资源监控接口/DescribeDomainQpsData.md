# DescribeDomainQpsData {#doc_api_Cdn_DescribeDomainQpsData .reference}

调用DescribeDomainQpsData接口获取加速域名的每秒访问次数QPS。

 **调用该接口前，请您注意：** 

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainQpsData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainQpsData|操作接口名，系统规定参数。取值：**DescribeDomainQpsData**。

 |
|DomainName|String|否|test.test.com|-   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（半角）分隔。

 |
|DomainType|String|否|dynamic|查询类型。

 -   传**dynamic**时，查询全站加速动态资源的QPS。
-   不传时查询静态资源的QPS。

 |
|EndTime|String|否|2015-12-10T21:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|Interval|String|否|300|查询数据的时间粒度。

 -   支持300, 3600, 14400, 28800和86400秒。
-   不传和传的值不支持时，使用默认值300秒。

 |
|IspNameEn|String|否|unicom|运营商英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

 |
|StartTime|String|否|2015-12-10T20:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。

 |
|TimeMerge|String|否|on|取值：

 -   **on**：默认值，每条记录的时间间隔会根据时间跨度做合并。
-   **off**：返回5分钟粒度数据，最大时间跨度为31天。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|test.test.com|如果参数为空，默认返回所有加速域名合并后数据。

 -   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（,）分隔。

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
|DynamicDomesticValue|String|0|全站加速，国内带宽动态QPS。当按区域运营商查询时，此值为空。

 |
|DynamicOverseasValue|String|0|全站加速，海外带宽动态QPS。当按区域运营商查询时，此值为空。

 |
|DynamicValue|String|0|全站加速，动态QPS数据值。

 |
|OverseasValue|String|0|海外QPS。

 |
|StaticDomesticValue|String|0|全站加速，国内带宽静态QPS。当按区域运营商查询时，此值为空。

 |
|StaticOverseasValue|String|0|全站加速，海外带宽静态QPS。当按区域运营商查询时，此值为空。

 |
|StaticValue|String|0|全站加速，静态QPS数据值。单位：bit/second。

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
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainQpsDataResponse>
	  <QpsDataInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T21:00:00Z</TimeStamp>
			      <Value>0.56</Value>
			      <DomesticValue>0</DomesticValue>
			      <OverseasValue>0</OverseasValue>
			      <AccValue>0</AccValue>
			      <AccDomesticValue>0</AccDomesticValue>
			      <AccOverseasValue>0</AccOverseasValue>
			      <HttpsValue>0.56</HttpsValue>
			      <HttpsDomesticValue>0</HttpsDomesticValue>
			      <HttpsOverseasValue>0</HttpsOverseasValue>
			      <HttpsAccValue>0</HttpsAccValue>
			      <HttpsAccDomesticValue>0</HttpsAccDomesticValue>
			      <HttpsAccOverseasValue>0</HttpsAccOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:35:00Z</TimeStamp>
			      <Value>0.64</Value>
			      <DomesticValue>0</DomesticValue>
			      <OverseasValue>0</OverseasValue>
			      <AccValue>0</AccValue>
			      <AccDomesticValue>0</AccDomesticValue>
			      <AccOverseasValue>0</AccOverseasValue>
			      <HttpsValue>0.56</HttpsValue>
			      <HttpsDomesticValue>0</HttpsDomesticValue>
			      <HttpsOverseasValue>0</HttpsOverseasValue>
			      <HttpsAccValue>0</HttpsAccValue>
			      <HttpsAccDomesticValue>0</HttpsAccDomesticValue>
			      <HttpsAccOverseasValue>0</HttpsAccOverseasValue>
		    </DataModule>
	  </QpsDataInterval>
	  <DomainName>example.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <RequestId>BEA5625F-8FCF-48F4-851B-CA63946DA664</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T21:00:00Z</EndTime>
</DescribeDomainQpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"QpsDataInterval":{
		"DataModule":[
			{
				"HttpsAccOverseasValue":"0",
				"Value":"0.56",
				"OverseasValue":"0",
				"AccValue":"0",
				"AccOverseasValue":"0",
				"HttpsAccValue":"0",
				"HttpsAccDomesticValue":"0",
				"AccDomesticValue":"0",
				"TimeStamp":"2015-12-10T21:00:00Z",
				"HttpsOverseasValue":"0",
				"HttpsDomesticValue":"0",
				"DomesticValue":"0",
				"HttpsValue":"0.56"
			},
			{
				"HttpsAccOverseasValue":"0",
				"Value":"0.64",
				"OverseasValue":"0",
				"AccValue":"0",
				"AccOverseasValue":"0",
				"HttpsAccValue":"0",
				"HttpsAccDomesticValue":"0",
				"AccDomesticValue":"0",
				"TimeStamp":"2015-12-10T20:35:00Z",
				"HttpsOverseasValue":"0",
				"HttpsDomesticValue":"0",
				"DomesticValue":"0",
				"HttpsValue":"0.56"
			}
		]
	},
	"DataInterval":"300",
	"RequestId":"BEA5625F-8FCF-48F4-851B-CA63946DA664",
	"DomainName":"example.com",
	"EndTime":"2015-12-10T21:00:00Z",
	"StartTime":"2015-12-10T20:00:00Z"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

