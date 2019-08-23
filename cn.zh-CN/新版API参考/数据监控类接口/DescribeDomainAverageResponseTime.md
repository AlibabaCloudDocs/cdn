# DescribeDomainAverageResponseTime {#doc_api_Cdn_DescribeDomainAverageResponseTime .reference}

调DescribeDomainAverageResponseTime获取加速域名的平均响应时间。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。同时指定StartTime和EndTime时，按指定的起止时间查询。
-   只支持一个域名或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainAverageResponseTime&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainAverageResponseTime|操作接口名，系统规定参数，取值：**DescribeDomainAverageResponseTime**。

 |
|DomainName|String|否|example.com|如果参数为空，默认返回所有加速域名合并后数据。

 可以输入需要查询的加速域名。支持批量域名查询，多个域名用逗号（,）分隔。

 |
|DomainType|String|否|123|域名类型。

 |
|EndTime|String|否|2015-12-10T21:00:00Z|获取数据的结束时间点。结束时间需大于起始时间。

 获取日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

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
|StartTime|String|否|2015-12-10T20:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟，不写默认读取过去24小时数据。

 |
|TimeMerge|String|否|1|是否自适应计算interval值，如果timeMerge=1，会根据startTime和endTime计算出合适的inteval值，和interval参数任选。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AvgRTPerInterval| | |每个时间点平均响应时间。

 |
|TimeStamp|String|2015-12-10T20:00:00Z|时间片起始时刻。

 |
|Value|String|3|平均响应时间。

 |
|DataInterval|String|300|数据时间间隔。

 |
|DomainName|String|example.com|加速域名。

 |
|EndTime|String|2015-12-11T21:00:00Z|结束时间。

 |
|RequestId|String|3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F|请求ID。

 |
|StartTime|String|2015-12-10T20:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainAverageResponseTime
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-11T21:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainAverageResponseTimeResponse>
	  <DomainName>example.com</DomainName>
	  <RequestId>3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-11T21:00:00Z</EndTime>
	  <DataInterval>300</DataInterval>
	  <AvgRTPerInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>3</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:05:00Z</TimeStamp>
			      <Value>3</Value>
		    </DataModule>
	  </AvgRTPerInterval>
</DescribeDomainAverageResponseTimeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"300",
	"RequestId":"3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F",
	"DomainName":"example.com",
	"EndTime":"2015-12-11T21:00:00Z",
	"StartTime":"2015-12-10T20:00:00Z",
	"AvgRTPerInterval":{
		"DataModule":[
			{
				"TimeStamp":"2015-12-10T20:00:00Z",
				"Value":"3"
			},
			{
				"TimeStamp":"2015-12-10T20:05:00Z",
				"Value":"3"
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

