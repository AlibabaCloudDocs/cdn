# DescribeDomainRealTimeSrcTrafficData {#doc_api_Cdn_DescribeDomainRealTimeSrcTrafficData .reference}

调用DescribeDomainRealTimeSrcTrafficData获取加速域名的1分钟回源流量监控数据，单位：bit。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。同时指定StartTime和EndTime时，按指定的起止时间查询。
-   支持批量域名查询，多个域名可用逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeSrcTrafficData&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|DomainName|String|是|example.com|如果该参数为空，默认返回所有加速域名合并后数据。

 可以输入需要查询的加速域名。支持批量域名查询，多个域名用逗号（,）分隔。

 |
|Action|String|否|DescribeDomainRealTimeSrcTrafficData|操作接口名，系统规定参数，取值：**DescribeDomainRealTimeSrcTrafficData**。

 |
|EndTime|String|否|2015-12-10T20:01:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|StartTime|String|否|2015-12-10T20:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   不写默认读取过去1小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|60|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|example.com|加速域名信息。

 |
|EndTime|String|2015-12-10T20:01:00Z|结束时间。

 |
|RealTimeSrcTrafficDataPerInterval| | |每个时间间隔的回源流量数据。

 |
|DataModule| | |每个时间间隔的回源流量数据。

 |
|TimeStamp|String|2015-12-10T20:01:00Z|时间片起始时刻。

 |
|Value|String|0|详细使用数据。

 |
|RequestId|String|A666D44F-19D6-490E-97CF-1A64AB962C57|请求ID。

 |
|StartTime|String|2015-12-10T20:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainRealTimeSrcTrafficData
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T20:01:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainRealTimeSrcTrafficDataResponse>
	  <DomainName>example.com</DomainName>
	  <DataInterval>60</DataInterval>
	  <RealTimeSrcTrafficDataPerInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:01:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
	  </RealTimeSrcTrafficDataPerInterval>
	  <RequestId>A666D44F-19D6-490E-97CF-1A64AB962C57</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T20:01:00Z</EndTime>
</DescribeDomainRealTimeSrcTrafficDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"60",
	"RealTimeSrcTrafficDataPerInterval":{
		"DataModule":[
			{
				"TimeStamp":"2015-12-10T20:00:00Z",
				"Value":"0"
			},
			{
				"TimeStamp":"2015-12-10T20:01:00Z",
				"Value":"0"
			}
		]
	},
	"RequestId":"A666D44F-19D6-490E-97CF-1A64AB962C57",
	"DomainName":"example.com",
	"EndTime":"2015-12-10T20:01:00Z",
	"StartTime":"2015-12-10T20:00:00Z"
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

