# DescribeDomainsUsageByDay {#doc_api_Cdn_DescribeDomainsUsageByDay .reference}

调用DescribeDomainsUsageByDay获取加速域名天粒度监控统计数据。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。同时指定StartTime和EndTime时，按指定的起止时间查询。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainsUsageByDay&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDomainsUsageByDay|操作接口名，系统规定参数。取值：**DescribeDomainsUsageByDay**。

 |
|DomainName|String|否|www.yourdomain.com|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|结束时间需大于起始时间。

 获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间点。

 日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C88EF8ED-72F0-45EA-9E86-95114E224FC5|请求ID。

 |
|DomainName|String|test.com|加速域名信息。

 |
|DataInterval|String|86400|每条记录的时间间隔，固定值1天。

 |
|StartTime|String|2015-12-01|开始时间。

 |
|EndTime|String|2015-12-02|结束时间。

 |
|UsageByDays| | |每个时间间隔统计数据。

 |
|BytesHitRate|String|97.46250599529726|命中率。

 |
|TimeStamp|String|2017-12-22T08:00:00:00Z|时间片起始时刻。

 |
|Qps|String|7.466354166666667|每秒访问量。

 |
|RequestHitRate|String|70.24770071912111|请求命中率。

 |
|MaxBps|String|1.050307709E8|带宽峰值。

 |
|MaxBpsTime|String|2015-12-01 01:20|带宽峰值时刻。

 |
|MaxSrcBps|String|2015-12-01 22:30|回源带宽峰值。

 |
|TotalAccess|String|645093|总访问量。

 |
|MaxSrcBpsTime|String|2015-12-01 22:30|回源带宽峰值时刻。

 |
|TotalTraffic|String|564300099309|总流量。

 |
|UsageTotal| | |汇总数据。

 |
|BytesHitRate|String|97.03110726801242|命中率。

 |
|RequestHitRate|String|69.92610837438424|请求命中率。

 |
|MaxBps|String|1.0747912780000001E8|带宽峰值。

 |
|MaxBpsTime|String|2015-12-02 23:55|带宽峰值时刻。

 |
|MaxSrcBps|String|2015-12-02 17:20|回源带宽峰值。

 |
|TotalAccess|String|1319500|总访问量。

 |
|MaxSrcBpsTime|String|2015-12-02 17:20|回源带宽峰值时刻。

 |
|TotalTraffic|String|1117711832100|总流量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainsUsageByDay
&DomainName=test.com
&StartTime=2015-11-29
&EndTime=2015-11-30
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainsUsageByDayResponse>
	  <UsageTotal>
		    <RequestHitRate>69.92610837438424</RequestHitRate>
		    <MaxSrcBpsTime>2015-12-02 17:20</MaxSrcBpsTime>
		    <MaxBps>1.0747912780000001E8</MaxBps>
		    <MaxSrcBps>2108177.5</MaxSrcBps>
		    <TotalTraffic>1117711832100</TotalTraffic>
		    <TotalAccess>1319500</TotalAccess>
		    <MaxBpsTime>2015-12-02 23:55</MaxBpsTime>
		    <BytesHitRate>97.03110726801242</BytesHitRate>
	  </UsageTotal>
	  <DataInterval>86400</DataInterval>
	  <UsageByDays>
		    <UsageByDay>
			      <TimeStamp>2015-12-01</TimeStamp>
			      <RequestHitRate>70.24770071912111</RequestHitRate>
			      <MaxSrcBpsTime>2015-12-01 22:30</MaxSrcBpsTime>
			      <MaxSrcBps>1044521.5000000001</MaxSrcBps>
			      <MaxBps>1.050307709E8</MaxBps>
			      <TotalTraffic>564300099309</TotalTraffic>
			      <TotalAccess>645093</TotalAccess>
			      <MaxBpsTime>2015-12-01 01:20</MaxBpsTime>
			      <Qps>7.466354166666667</Qps>
			      <BytesHitRate>97.46250599529726</BytesHitRate>
		    </UsageByDay>
		    <UsageByDay>
			      <TimeStamp>2015-12-02</TimeStamp>
			      <RequestHitRate>69.61849446995657</RequestHitRate>
			      <MaxSrcBpsTime>2015-12-02 17:20</MaxSrcBpsTime>
			      <MaxSrcBps>2108177.5</MaxSrcBps>
			      <MaxBps>1.0747912780000001E8</MaxBps>
			      <TotalTraffic>553411732791</TotalTraffic>
			      <TotalAccess>674407</TotalAccess>
			      <MaxBpsTime>2015-12-02 23:55</MaxBpsTime>
			      <Qps>7.805636574074074</Qps>
			      <BytesHitRate>96.59122077803737</BytesHitRate>
		    </UsageByDay>
	  </UsageByDays>
	  <RequestId>C88EF8ED-72F0-45EA-9E86-95114E224FC5</RequestId>
	  <DomainName>example.com</DomainName>
	  <EndTime>2015-12-02T00:00:00Z</EndTime>
	  <StartTime>2015-12-01T00:00:00Z</StartTime>
</DescribeDomainsUsageByDayResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"UsageTotal":{
		"RequestHitRate":"69.92610837438424",
		"MaxSrcBpsTime":"2015-12-02 17:20",
		"MaxSrcBps":"2108177.5",
		"MaxBps":"1.0747912780000001E8",
		"TotalTraffic":"1117711832100",
		"TotalAccess":"1319500",
		"MaxBpsTime":"2015-12-02 23:55",
		"BytesHitRate":"97.03110726801242"
	},
	"UsageByDays":{
		"UsageByDay":[
			{
				"TimeStamp":"2015-12-01",
				"RequestHitRate":"70.24770071912111",
				"MaxSrcBpsTime":"2015-12-01 22:30",
				"MaxBps":"1.050307709E8",
				"MaxSrcBps":"1044521.5000000001",
				"TotalTraffic":"564300099309",
				"TotalAccess":"645093",
				"Qps":"7.466354166666667",
				"MaxBpsTime":"2015-12-01 01:20",
				"BytesHitRate":"97.46250599529726"
			},
			{
				"TimeStamp":"2015-12-02",
				"RequestHitRate":"69.61849446995657",
				"MaxSrcBpsTime":"2015-12-02 17:20",
				"MaxBps":"1.0747912780000001E8",
				"MaxSrcBps":"2108177.5",
				"TotalTraffic":"553411732791",
				"TotalAccess":"674407",
				"Qps":"7.805636574074074",
				"MaxBpsTime":"2015-12-02 23:55",
				"BytesHitRate":"96.59122077803737"
			}
		]
	},
	"DataInterval":"86400",
	"RequestId":"C88EF8ED-72F0-45EA-9E86-95114E224FC5",
	"DomainName":"example.com",
	"EndTime":"2015-12-02T00:00:00Z",
	"StartTime":"2015-12-01T00:00:00Z"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|
|404|InvalidDomain.NotFound|The domain provided does not exist in our records.|域名不存在或不属于当前用户。请检查您填写的域名书写是否正确，或者域名是否在当前账号中，查看域名是否过期。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

