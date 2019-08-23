# DescribeDomainSrcBpsData {#doc_api_Cdn_DescribeDomainSrcBpsData .reference}

调用DescribeDomainSrcBpsData获取加速域名的回源带宽监控数据。

获取数据的单位：bit/second。

**说明：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。同时指定StartTime和EndTime时，按指定的起止时间查询。
-   支持批量域名查询，多个域名用逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainSrcBpsData&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDomainSrcBpsData|操作接口名，系统规定参数。取值：**DescribeDomainSrcData**。

 |
|DomainName|String|否|www.yourdomain.com|如果参数为空，默认返回所有加速域名合并后数据。

 可输入需要查询的加速域名。支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2017-12-12T20:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Interval|String|否|300|查询数据的时间粒度，支持**300**、 **3600**和**86400**秒。

 -   3天以内（不包含3天整）支持**300**、**3600**、 **86400**。
-   3-31天（不包含31天整）支持**3600**和**86400**。
-   31天以上支持**86400**。

 不传和传的值不支持时，使用默认值。

 |
|StartTime|String|否|2017-12-10T20:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟， 不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|yourdomain.com|加速域名信息。

 |
|EndTime|String|2017-12-12T20:00Z|结束时间。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |
|SrcBpsDataPerInterval| | |每个时间间隔的回源带宽数据。

 |
|HttpsValue|String|10|https回源带宽。

 |
|TimeStamp|String|2017-12-10T20:45:00Z|时间片起始时刻。

 |
|Value|String|500|详细使用数据。

 |
|StartTime|String|2017-12-10T20:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainSrcBpsData
&DomainName=test.com
&StartTime=2017-12-10T20:00Z
&EndTime=2017-12-10T21:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainSrcBpsDataResponse>
	  <DomainName>test.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <SrcBpsDataPerInterval>
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
			      <Value>821</Value>
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
	  </SrcBpsDataPerInterval>
	  <RequestId>7CBCD6AD-B016-42E5-AE0B-B3731DE8F755</RequestId>
	  <StartTime>2017-12-10T20:00Z</StartTime>
	  <EndTime>2017-12-10T21:00Z</EndTime>
</DescribeDomainSrcBpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SrcBpsDataPerInterval":{
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
				"Value":"821"
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
	"RequestId":"7CBCD6AD-B016-42E5-AE0B-B3731DE8F755",
	"DomainName":"test.com",
	"EndTime":"2017-12-10T21:00Z",
	"StartTime":"2017-12-10T20:00Z"
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

