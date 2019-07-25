# DescribeDomainFlowData {#doc_api_Cdn_DescribeDomainFlowData .reference}

调用DescribeDomainFlowData接口获取加速域名的网络流量监控数据。

单位：byte。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   支持批量域名查询，多个域名用逗号（半角）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainFlowData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainFlowData|操作接口名，系统规定参数。取值：**DescribeDomainFlowData**。

 |
|DomainName|String|否|www.yourdomain.com|-   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（半角）分隔。

 |
|DomainType|String|否|dynamic|查询类型。

 -   传**dynamic**时，查询全站加速动态资源的实时流量和静态资源的实时流量。
-   不传时查询静态资源的实时流量。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|-   结束时间需大于起始时间。
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
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间点。

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
|DomainName|String|test.com|加速域名信息

 |
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|StartTime|String|2015-12-10T20:00Z|开始时间

 |
|EndTime|String|2015-12-10T21:00Z|结束时间

 |
|FlowDataPerInterval| | |每个时间间隔的流量数据

 |
|TimeStamp|String|2017-12-22T08:00:00:00Z|时间片起始时刻

 |
|Value|String|423304182|总流量

 |
|DomesticValue|String|0|国内流量

 |
|OverseasValue|String|0|海外流量

 |
|DynamicValue|String|0|全站加速，动态流量。当按区域运营商查询时，此值为空。

 |
|DynamicDomesticValue|String|0|全站加速，国内动态流量。当按区域运营商查询时，此值为空。

 |
|DynamicOverseasValue|String|0|全站加速，海外动态流量。当按区域运营商查询时，此值为空。

 |
|StaticValue|String|0|全站加速，静态流量。当按区域运营商查询时，此值为空。

 |
|StaticDomesticValue|String|0|全站加速，国内静态流量。当按区域运营商查询时，此值为空。

 |
|StaticOverseasValue|String|0|全站加速，海外静态流量。当按区域运营商查询时，此值为空。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainFlowData
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
	  <DomainName>test.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <FlowDataPerInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>423304182</Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:05:00Z</TimeStamp>
			      <Value>454680793</Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:10:00Z</TimeStamp>
			      <Value>501718342</Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:15:00Z</TimeStamp>
			      <Value>434816025</Value>
			      <DynamicValue>0</DynamicValue>
			      <DynamicDomesticValue>0</DynamicDomesticValue>
			      <DynamicOverseasValue>0</DynamicOverseasValue>
			      <StaticValue>0</StaticValue>
			      <StaticDomesticValue>0</StaticDomesticValue>
			      <StaticOverseasValue>0</StaticOverseasValue>
		    </DataModule>
	  </FlowDataPerInterval>
	  <RequestId>B955107D-E658-4E77-B913-E0AC3D31693E</RequestId>
	  <StartTime>2015-12-10T20:00Z</StartTime>
	  <EndTime>2015-12-10T21:00Z</EndTime>
</APINAMEResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"300",
	"RequestId":"B955107D-E658-4E77-B913-E0AC3D31693E",
	"FlowDataPerInterval":{
		"DataModule":[
			{
				"TimeStamp":"2015-12-10T20:00:00Z",
				"StaticValue":"0",
				"DynamicDomesticValue":"0",
				"Value":"423304182",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DynamicValue":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:05:00Z",
				"StaticValue":"0",
				"DynamicDomesticValue":"0",
				"Value":"454680793",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DynamicValue":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:10:00Z",
				"StaticValue":"0",
				"DynamicDomesticValue":"0",
				"Value":"501718342",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DynamicValue":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:15:00Z",
				"StaticValue":"0",
				"DynamicDomesticValue":"0",
				"Value":"434816025",
				"DynamicOverseasValue":"0",
				"StaticOverseasValue":"0",
				"StaticDomesticValue":"0",
				"DynamicValue":"0"
			}
		]
	},
	"DomainName":"test.com",
	"EndTime":"2015-12-10T21:00Z",
	"StartTime":"2015-12-10T20:00Z"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

