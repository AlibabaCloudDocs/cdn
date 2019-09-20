# DescribeDomainHitRateData {#doc_api_Cdn_DescribeDomainHitRateData .reference}

调用DescribeDomainHitRateData获取加速域名的字节命中率（命中字节百分比）。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。同时指定StartTime和EndTime时，按指定的起止时间查询。
-   支持批量域名查询，多个域名用逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainHitRateData&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDomainHitRateData|操作接口名，系统规定参数。取值：**DescribeDomainHitRateData**。

 |
|DomainName|String|否|www.yourdomain.com|需要查询的加速域名，只支持一个域名。不填代表查询当前用户下所有域名。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|获取数据结束时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。

 |
|Interval|String|否|300|查询数据的时间粒度，支持**300**、 **3600**和**86400**秒。

 -   3天以内（不包含3天整）支持**300**、**3600**、 **86400**。
-   3-31天（不包含31天整）支持**3600**和**86400**。
-   31天以上支持**86400**。

 不传和传的值不支持时，使用默认值。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟，不写默认读取过去24小时数据。

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
|HitRateInterval| | |每个时间间隔的字节命中百分占比。

 |
|DataModule| | |每个时间间隔的字节命中百分占比。

 |
|TimeStamp|String|2017-12-22T08:00:00:00Z|时间片起始时刻。

 |
|Value|String|100.0|详细使用数据。

 |
|HttpsValue|String|50.0|https字节命中率。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainHitRateData
&DomainName=test.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainHitRateDataResponse>
	  <DomainName>example.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <RequestId>5ADA5190-EE5B-4EF2-BE00-DC441B8D81DD</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T21:00:00Z</EndTime>
	  <HitRateInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T21:00:00Z</TimeStamp>
			      <Value>100.0</Value>
			      <HttpsValue>50.0</HttpsValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:35:00Z</TimeStamp>
			      <Value>100.0</Value>
			      <HttpsValue>50.0</HttpsValue>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:50:00Z</TimeStamp>
			      <Value>99.99932881437826</Value>
			      <HttpsValue>50.0</HttpsValue>
		    </DataModule>
	  </HitRateInterval>
</DescribeDomainHitRateDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"300",
	"RequestId":"5ADA5190-EE5B-4EF2-BE00-DC441B8D81DD",
	"DomainName":"example.com",
	"EndTime":"2015-12-10T21:00:00Z",
	"StartTime":"2015-12-10T20:00:00Z",
	"HitRateInterval":{
		"DataModule":[
			{
				"TimeStamp":"2015-12-10T21:00:00Z",
				"Value":"100.0",
				"HttpsValue":"50.0"
			},
			{
				"TimeStamp":"2015-12-10T20:35:00Z",
				"Value":"100.0",
				"HttpsValue":"50.0"
			},
			{
				"TimeStamp":"2015-12-10T20:50:00Z",
				"Value":"99.99932881437826",
				"HttpsValue":"50.0"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

