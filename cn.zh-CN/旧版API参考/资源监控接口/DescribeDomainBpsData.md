# DescribeDomainBpsData {#doc_api_Cdn_DescribeDomainBpsData .reference}

调用DescribeDomainBpsData接口获取加速域名的网络带宽监控数据。

单位：bit/second。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。
-   使用该接口一次性查询全部地区和运营商的数据可能存在偏差。因此建议您使用该接口时，逐个地区、运营商地查询。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainBpsData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainBpsData|操作接口名，系统规定参数。取值：**DescribeDomainBpsData**。

 |
|DomainName|String|否|test.test.com|如果参数为空，默认返回所有加速域名合并后数据。

 -   可以输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（,）分隔。

 |
|DomainType|String|否|dynamic|查询类型。

 -   传dynamic时，查询全站加速动态资源的实时带宽和静态资源的实时带宽。
-   不传时，查询静态资源的实时带宽。

 |
|EndTime|String|否|2015-12-10T20:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|Interval|String|否|300|查询数据的时间粒度。

 -   支持**300**、**3600**、**14400**、**28800**和**86400**秒。
-   不传和传的值不支持时，使用默认值**300**秒。

 |
|IspNameEn|String|否|telecom|运营商英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

 |
|StartTime|String|否|2015-12-10T20:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。
-   不写默认读取过去24小时数据。

 |
|TimeMerge|String|否|on|取值：

 -   **on**：默认值，每条记录的时间间隔会根据时间跨度做合并。
-   **off**：返回5分钟粒度数据，最大时间跨度为31天。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|BpsDataPerInterval| | |每个时间间隔的网络带宽数据。

 |
|DomesticL2Value|String|0|L2国内带宽bps。当按区域运营商查询时，此值为空。

 |
|DomesticValue|String|11286111|国内带宽bps。当按区域运营商查询时，此值为空。

 |
|DynamicDomesticValue|String|0|全站加速，国内带宽动态bps。当按区域运营商查询时，此值为空。

 |
|DynamicOverseasValue|String|0|全站加速，海外带宽动态bps。当按区域运营商查询时，此值为空。

 |
|DynamicValue|String|0|全站加速，动态bps数据值。单位：bit/second。

 |
|L2Value|String|0|L2 bps数据值。单位：bit/second。

 |
|OverseasL2Value|String|0|L2海外带宽bps。当按区域运营商查询时，此值为空。

 |
|OverseasValue|String|2000|海外带宽bps。当按区域运营商查询时，此值为空。

 |
|StaticDomesticValue|String|0|全站加速，国内带宽静态bps。当按区域运营商查询时，此值为空。

 |
|StaticOverseasValue|String|0|全站加速，海外带宽静态bps。当按区域运营商查询时，此值为空。

 |
|StaticValue|String|0|全站加速，静态bps数据值。单位：bit/second。

 |
|TimeStamp|String|2015-12-10T20:00:00Z|时间片起始时刻。

 |
|Value|String|11288111|bps数据值。单位：bit/second。

 |
|DataInterval|String|300|需要补充时间间隔规则，每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|test.test.com|加速域名。

 |
|EndTime|String|2015-12-10T20:00Z|结束时间。

 |
|IspName|String|联通|运营商名称。

 |
|IspNameEn|String|unicom|运营商英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationName|String|北京市|区域名。

 |
|LocationNameEn|String|beijing|区域英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

 |
|RequestId|String|3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F|请求ID。

 |
|StartTime|String|2015-12-10T20:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com?Action=DescribeDomainBpsData
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainBpsDataResponse>
	  <BpsDataPerInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>11288111</Value>
			      <DomesticValue>11286111</DomesticValue>
			      <OverseasValue>2000</OverseasValue>
			      <HttpsValue>11288111</HttpsValue>
			      <HttpsDomesticValue>11286111</HttpsDomesticValue>
			      <HttpsOverseasValue>2000</HttpsOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:05:00Z</TimeStamp>
			      <Value>12124821</Value>
			      <DomesticValue>12112821</DomesticValue>
			      <OverseasValue>12000</OverseasValue>
			      <HttpsValue>11288111</HttpsValue>
			      <HttpsDomesticValue>11286111</HttpsDomesticValue>
			      <HttpsOverseasValue>2000</HttpsOverseasValue>
		    </DataModule>
	  </BpsDataPerInterval>
	  <DomainName>example.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <RequestId>3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T21:00:00Z</EndTime>
</DescribeDomainBpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"300",
	"BpsDataPerInterval":{
		"DataModule":[
			{
				"HttpsOverseasValue":"2000",
				"TimeStamp":"2015-12-10T20:00:00Z",
				"Value":"11288111",
				"OverseasValue":"2000",
				"HttpsDomesticValue":"11286111",
				"DomesticValue":"11286111",
				"HttpsValue":"11288111"
			},
			{
				"HttpsOverseasValue":"2000",
				"TimeStamp":"2015-12-10T20:05:00Z",
				"Value":"12124821",
				"OverseasValue":"12000",
				"HttpsDomesticValue":"11286111",
				"DomesticValue":"12112821",
				"HttpsValue":"11288111"
			}
		]
	},
	"RequestId":"3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F",
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

