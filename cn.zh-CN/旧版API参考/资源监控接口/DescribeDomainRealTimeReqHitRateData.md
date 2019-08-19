# DescribeDomainRealTimeReqHitRateData {#doc_api_Cdn_DescribeDomainRealTimeReqHitRateData .reference}

调用DescribeDomainRealTimeReqHitRateData接口获取域名1分钟粒度请求命中率数据。

**说明：** 

-   由于存在多域名合并存储的情况，可能会导致命中率数据不准确，具体情况以配置为准。
-   可以查询7天内的数据，单次查询**StartTime**和**EndTime**跨度不能超过24小时。
-   如果**StartTime**和**EndTime**均未指定，默认返回当前时间起一小时内的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeReqHitRateData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainRealTimeReqHitRateData|操作接口名，系统规定参数，取值：**DescribeDomainRealTimeReqHitRateData**。

 |
|DomainName|String|是|test.test.com|加速域名。

 |
|EndTime|String|否|2016-10-20T04:00:00Z|结束时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|StartTime|String|否|2016-10-20T04:00:00Z|起始时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Data| | |返回数据。

 |
|ReqHitRate|Float|0.8956940476262277|请求命中率数据。

 |
|TimeStamp|String|2018-01-02T11:25:00Z|数据时间戳。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|RequestId|String|70A26B11-3673-479C-AEA8-E03FC5D3496D|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeReqHitRateData
&DomainName=example.com
&EndTime=2016-10-20T04:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainRealTimeReqHitRateDataResponse>
	  <Data>
		    <ReqHitRateModel>
			      <TimeStamp>2018-01-02T11:26:00Z</TimeStamp>
			      <ReqHitRate>0.8956940476262277</ReqHitRate>
		    </ReqHitRateModel>
		    <ReqHitRateModel>
			      <TimeStamp>2018-01-02T11:25:00Z</TimeStamp>
			      <ReqHitRate>0.8429129920796812</ReqHitRate>
		    </ReqHitRateModel>
	  </Data>
	  <RequestId>70A26B11-3673-479C-AEA8-E03FC5D3496D</RequestId>
</DescribeDomainRealTimeReqHitRateDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"ReqHitRateModel":[
			{
				"TimeStamp":"2018-01-02T11:26:00Z",
				"ReqHitRate":0.8956940476262277
			},
			{
				"TimeStamp":"2018-01-02T11:25:00Z",
				"ReqHitRate":0.8429129920796812
			}
		]
	},
	"RequestId":"70A26B11-3673-479C-AEA8-E03FC5D3496D"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidTime.Malformed|Specified StartTime or EndTime is malformed.|开始时间或结束时间格式错误。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

