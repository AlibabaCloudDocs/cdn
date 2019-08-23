# DescribeDomainRealTimeSrcBpsData {#doc_api_Cdn_DescribeDomainRealTimeSrcBpsData .reference}

调用DescribeDomainRealTimeSrcBpsData获取域名1分钟粒度回源带宽数据。

 **调用该接口前，请您注意：** 

-   单次查询StartTime和EndTime跨度不能超过24小时。如果StartTime和EndTime均未指定，默认返回当前时间起一小时内的数据。
-   支持批量域名查询，多个域名用半角逗号（,）分隔。
-   最多可获取最近7天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeSrcBpsData&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|DomainName|String|是|example.com|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。

 |
|Action|String|否|DescribeDomainRealTimeSrcBpsData|操作接口名，系统规定参数，取值：**DescribeDomainRealTimeSrcBpsData**。

 |
|EndTime|String|否|2015-12-10T20:01:00Z|获取数据的结束时间点。

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
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|example.com|加速域名。

 |
|EndTime|String|2015-12-10T20:01:00Z|结束时间。

 |
|RealTimeSrcBpsDataPerInterval| | |每个时间间隔的回源带宽数据。

 |
|TimeStamp|String|2015-12-10T20:01:00Z|时间片起始时刻。

 |
|Value|String|0|详细使用数据。

 |
|RequestId|String|7CBCD6AD-B016-42E5-AE0B-B3731DE8F755|请求ID。

 |
|StartTime|String|2015-12-10T20:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainRealTimeSrcBpsData
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T20:01:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainRealTimeSrcBpsDataResponse>
	  <DomainName>example.com</DomainName>
	  <DataInterval>60</DataInterval>
	  <RealTimeSrcBpsDataPerInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>821</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:01:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
	  </RealTimeSrcBpsDataPerInterval>
	  <RequestId>7CBCD6AD-B016-42E5-AE0B-B3731DE8F755</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T20:01:00Z</EndTime>
</DescribeDomainRealTimeSrcBpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RealTimeSrcBpsDataPerInterval":{
		"DataModule":[
			{
				"TimeStamp":"2015-12-10T20:00:00Z",
				"Value":"821"
			},
			{
				"TimeStamp":"2015-12-10T20:01:00Z",
				"Value":"0"
			}
		]
	},
	"DataInterval":"60",
	"RequestId":"7CBCD6AD-B016-42E5-AE0B-B3731DE8F755",
	"DomainName":"example.com",
	"EndTime":"2015-12-10T20:01:00Z",
	"StartTime":"2015-12-10T20:00:00Z"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

