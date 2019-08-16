# DescribeDomainSrcFlowData {#doc_api_Cdn_DescribeDomainSrcFlowData .reference}

调用DescribeDomainSrcFlowData接口获取加速域名的回源流量监控数据。

获取数据单位：bit。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainSrcFlowData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainSrcFlowData|操作接口名，系统规定参数。取值：**DescribeDomainSrcFlowData**。

 |
|DomainName|String|否|www.yourdomain.com|如果参数为空，默认返回所有加速域名合并后数据。

 -   可以输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|FixTimeGap|String|否|false|是否补零。

 |
|Interval|String|否|300|时间间隔。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。
-   不写默认读取过去24小时数据。

 |
|TimeMerge|String|否|true|是否时间合并。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|test.com|加速域名信息。

 |
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|StartTime|String|2015-12-10T20:00Z|开始时间。

 |
|EndTime|String|2015-12-10T21:00Z|结束时间。

 |
|SrcFlowDataPerInterval| | |每个时间间隔的回源流量数据。

 |
|TimeStamp|String|2017-12-22T08:00:00:00Z|时间片起始时刻。

 |
|Value|String|0|详细使用数据。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com?Action=DescribeDomainSrcFlowData
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainSrcFlowDataResponse>
  <DomainName>test.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <SrcFlowDataPerInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T21:00:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:35:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:50:00Z</TimeStamp>
			      <Value>33886</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:05:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:10:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:55:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:30:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:25:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:40:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:15:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:45:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:20:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
	  </SrcFlowDataPerInterval>
	  <RequestId>A666D44F-19D6-490E-97CF-1A64AB962C57</RequestId>
	  <StartTime>2015-12-10T20:00Z</StartTime>
	  <EndTime>2015-12-10T21:00Z</EndTime>
</DescribeDomainSrcFlowDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SrcFlowDataPerInterval":{
		"DataModule":[
			{
				"TimeStamp":"2015-12-10T21:00:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:35:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:50:00Z",
				"Value":"33886"
			},
			{
				"TimeStamp":"2015-12-10T20:05:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:10:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:55:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:30:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:25:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:00:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:40:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:15:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:45:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:20:00Z",
				"Value":"0"
			}
		]
	},
	"DataInterval":"300",
	"RequestId":"A666D44F-19D6-490E-97CF-1A64AB962C57",
	"DomainName":"test.com",
	"EndTime":"2015-12-10T21:00Z",
	"StartTime":"2015-12-10T20:00Z"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|StartTime and EndTime can not be single.|开始时间与结束时间均为必填。|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|请检查时间设置是否正确，结束时间不能小于或等于开始时间。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

