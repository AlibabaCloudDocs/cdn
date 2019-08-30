# DescribeRealtimeDeliveryAcc {#doc_api_Cdn_DescribeRealtimeDeliveryAcc .reference}

调用DescribeRealtimeDeliveryAcc查询实时日志投递次数。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeRealtimeDeliveryAcc&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeRealtimeDeliveryAcc|操作接口名，系统规定参数，取值：**DescribeRealtimeDeliveryAcc**。

 |
|EndTime|String|否|2016-10-20T04:00:00Z|结束时间需大于起始时间。起止时间和结束时间，间隔不超过一年。

 获取日期格式按照ISO8601表示法，并使用UTC时间。

 |
|Interval|String|否|300|查询数据的时间粒度，支持**300**、**3600**、**86400**秒。

 -   不传和传的值不支持时，时间跨度不超过3天，默认值**300**秒。
-   超过3天不超过30天默认值**3600**秒。
-   超过30天默认值**86400**秒。

 |
|LogStore|String|否|LogStore|实时日志投递的Logstore。

 |
|Project|String|否|Project|实时日志投递的Project。

 |
|StartTime|String|否|2016-10-20T04:00:00Z|获取日志起始时间点。

 日期格式按照ISO8601表示法，并使用UTC时间。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ReatTimeDeliveryAccData| | |实时日志信息。

 |
|FailedNum|Integer|2|实时日志投递失败次数。

 |
|SuccessNum|Integer|2|实时日志投递成功次数。

 |
|TimeStamp|String|2018-09-03T06:00:00Z|时间片起始时刻。

 |
|RequestId|String|684306D2-2511-4977-991D-CE97E91FD7C0|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeRealtimeDeliveryAcc
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:05:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeRealtimeDeliveryAccResponse>
	  <RequestId>684306D2-2511-4977-991D-CE97E91FD7C0</RequestId>
	  <ReatTimeDeliveryAccData>
		    <AccData>
			      <TimeStamp>2018-09-03T06:00:00Z</TimeStamp>
			      <FailedNum>0</FailedNum>
			      <SuccessNum>321321</SuccessNum>
		    </AccData>
		    <AccData>
			      <TimeStamp>2018-09-03T07:00:00Z</TimeStamp>
			      <FailedNum>0</FailedNum>
			      <SuccessNum>32943</SuccessNum>
		    </AccData>
	  </ReatTimeDeliveryAccData>
</DescribeRealtimeDeliveryAccResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"684306D2-2511-4977-991D-CE97E91FD7C0",
	"ReatTimeDeliveryAccData":{
		"AccData":[
			{
				"TimeStamp":"2018-09-03T06:00:00Z",
				"FailedNum":0,
				"SuccessNum":321321
			},
			{
				"TimeStamp":"2018-09-03T07:00:00Z",
				"FailedNum":0,
				"SuccessNum":32943
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

