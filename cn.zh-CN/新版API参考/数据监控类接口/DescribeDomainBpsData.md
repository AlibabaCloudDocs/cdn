# DescribeDomainBpsData {#doc_api_Cdn_DescribeDomainBpsData .reference}

调用DescribeDomainBpsData获取加速域名的网络带宽监控数据。

获取数据单位：bit/second。

**说明：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。同时指定StartTime和EndTime时，按指定的起止时间查询。
    -   支持批量域名查询，多个域名用逗号（,）分隔。
    -   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainBpsData&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainBpsData|操作接口名，系统规定参数，取值：**DescribeDomainBpsData**。

 |
|DomainName|String|否|test.test.com|如果参数为空，默认返回所有加速域名合并后数据。

 可输入需要查询的加速域名，支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2015-12-10T20:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Interval|String|否|300|查询数据的时间粒度，支持**300**、 **3600**和**86400**秒。

 -   3天以内（不包含3天整）支持**300**、**3600**、 **86400**。
-   3-31天（不包含31天整）支持**3600**和**86400**。
-   31天及以上支持**86400**。

 不传和传的值不支持时，使用默认值。

 |
|IspNameEn|String|否|telecom|运营商英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得，不传为所有区域。

 |
|StartTime|String|否|2015-12-10T20:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟，
-   不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|BpsDataPerInterval| | |每个时间间隔的网络带宽数据。

 |
|DataModule| | |每个时间间隔的网络带宽数据。

 |
|DomesticValue|String|11286111|国内带宽bps，当按区域运营商查询时，此值为空。

 |
|HttpsDomesticValue|String|11286111|L1节点https国内带宽。当按区域运营商查询时，此值为空。

 |
|HttpsOverseasValue|String|2000|L1节点海外https带宽。当按区域运营商查询时，此值为空。

 |
|HttpsValue|String|11288111|L1节点https的带宽数据值，单位：bit/second。

 |
|OverseasValue|String|2000|海外带宽bps，当按区域运营商查询时，此值为空。

 |
|TimeStamp|String|2015-12-10T20:00:00Z|时间片起始时刻。

 |
|Value|String|11288111|bps数据值，单位：bit/second。

 |
|DataInterval|String|300|需要补充时间间隔规则，每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|test.test.com|加速域名。

 |
|EndTime|String|2015-12-10T20:00Z|结束时间。

 |
|IspNameEn|String|unicom|运营商英文名。

 |
|LocationNameEn|String|beijing|区域英文名。

 |
|RequestId|String|3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F|请求ID。

 |
|StartTime|String|2015-12-10T20:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainBpsData
&DomainName=test.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
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
			      <L2Value>0</L2Value>
			      <DomesticL2Value>0</DomesticL2Value>
			      <OverseasL2Value>0</OverseasL2Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:05:00Z</TimeStamp>
			      <Value>12124821</Value>
			      <DomesticValue>12112821</DomesticValue>
			      <OverseasValue>12000</OverseasValue>
			      <L2Value>0</L2Value>
			      <DomesticL2Value>0</DomesticL2Value>
			      <OverseasL2Value>0</OverseasL2Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
	  </BpsDataPerInterval>
	  <SupplyBpsDatas>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:05:00Z</TimeStamp>
			      <Value>12124821</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:06:00Z</TimeStamp>
			      <Value>12144838</Value>
		    </DataModule>
	  </SupplyBpsDatas>
	  <DomainName>test.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <RequestId>3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F</RequestId>
	  <StartTime>2015-12-10T20:00Z</StartTime>
	  <EndTime>2015-12-10T21:00Z</EndTime>
</DescribeDomainBpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"300",
	"BpsDataPerInterval":{
		"DataModule":[
			{
				"Value":"11288111",
				"DynamicDomesticValue":"0",
				"OverseasValue":"2000",
				"L2Value":"0",
				"TimeStamp":"2015-12-10T20:00:00Z",
				"StaticValue":"0",
				"OverseasL2Value":"0",
				"DomesticValue":"11286111",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DomesticL2Value":"0",
				"DynamicValue":"0"
			},
			{
				"Value":"12124821",
				"DynamicDomesticValue":"0",
				"OverseasValue":"12000",
				"L2Value":"0",
				"TimeStamp":"2015-12-10T20:05:00Z",
				"StaticValue":"0",
				"OverseasL2Value":"0",
				"DomesticValue":"12112821",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DomesticL2Value":"0",
				"DynamicValue":"0"
			}
		]
	},
	"RequestId":"3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F",
	"DomainName":"test.com",
	"EndTime":"2015-12-10T21:00Z",
	"StartTime":"2015-12-10T20:00Z",
	"SupplyBpsDatas":{
		"DataModule":[
			{
				"TimeStamp":"2015-12-10T20:05:00Z",
				"Value":"12124821"
			},
			{
				"TimeStamp":"2015-12-10T20:06:00Z",
				"Value":"12144838"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

