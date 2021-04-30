# 获取每秒访问次数QPS

调用DescribeDomainQpsData获取5分钟计算粒度加速域名的每秒访问次数QPS，支持获取最近90天的数据。

**说明：**

-   如果您不指定StartTime和EndTime，该接口返回过去24小时的数据；指定StartTime和EndTime，返回起止时间的数据。
-   单用户调用频率：100次/秒。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainQpsData&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDomainQpsData|系统规定参数。取值：**DescribeDomainQpsData**。 |
|DomainName|String|否|test.test.com|加速域名，多个域名用英文逗号（,）分隔。

 默认查询所有加速域名。 |
|StartTime|String|否|2019-11-30T05:33:00Z|获取数据起始时间点。日期格式按照ISO8601表示法，并使用UTC时间。格式为yyyy-MM-ddTHH:mm:ssZ。 |
|EndTime|String|否|2019-11-30T05:40:00Z|获取数据结束时间点。日期格式按照ISO8601表示法，并使用UTC时间。格式为yyyy-MM-ddTHH:mm:ssZ。

 结束时间需大于起始时间。 |
|Interval|String|否|300|查询数据的时间粒度，单位：秒。根据您指定**StartTime**和**EndTime**两者的时间跨度，该参数取值如下：

 -   3天以内（不包含3天整）：支持**300**、**3600**、 **86400**，如果不传该参数，默认值为**300**。
-   3~31天（不包含31天整）：支持**3600**和**86400**，如果不传该参数，默认值为**3600**。
-   31天及以上：支持**86400**，如果不传该参数，默认值为**86400**。 |
|IspNameEn|String|否|unicom|运营商英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得，默认查询所有运营商。 |
|LocationNameEn|String|否|beijing|地域英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得，默认查询所有地域。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。 |
|DomainName|String|test.test.com|加速域名信息。 |
|StartTime|String|2019-11-30T05:33:00Z|开始时间。 |
|EndTime|String|2019-11-30T05:40:00Z|结束时间。 |
|RequestId|String|B8333EDB-4595-46E0-AFE9-29BAA290D0E0|请求ID。 |
|QpsDataInterval|Array of DataModule| |每个时间间隔的每秒访问次数QPS。 |
|DataModule| | | |
|AccDomesticValue|String|0|中国内地访问次数。 |
|AccOverseasValue|String|0|全球（不包含中国内地）访问次数。 |
|AccValue|String|0|总访问次数。 |
|DomesticValue|String|0|中国内地QPS。 |
|HttpsAccDomesticValue|String|1|L1节点中国内地HTTPS请求数。 |
|HttpsAccOverseasValue|String|1|L1节点全球（不包含中国内地）HTTPS请求数。 |
|HttpsAccValue|String|1|L1节点HTTPS请求数。 |
|HttpsDomesticValue|String|1|L1节点HTTPS中国内地QPS值。 |
|HttpsOverseasValue|String|1|L1节点HTTPS全球（不包含中国内地）QPS值。 |
|HttpsValue|String|1|L1节点HTTPS的QPS值。 |
|OverseasValue|String|0|全球（不包含中国内地）QPS。 |
|TimeStamp|String|2019-11-30T05:40:00Z|时间片起始时刻。 |
|Value|String|0|总QPS。 |

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeDomainQpsData
&DomainName=test.com
&StartTime=2019-11-30T05:33:00Z
&EndTime=2019-11-30T05:40:00Z
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeDomainQpsDataResponse>
  <QpsDataInterval>
        <DataModule>
              <HttpsOverseasValue>0</HttpsOverseasValue>
              <TimeStamp>2019-11-30T05:35:00Z</TimeStamp>
              <HttpsAccOverseasValue>0</HttpsAccOverseasValue>
              <Value>0.006666666666666667</Value>
              <OverseasValue>0</OverseasValue>
              <HttpsDomesticValue>0</HttpsDomesticValue>
              <AccOverseasValue>0</AccOverseasValue>
              <AccValue>2</AccValue>
              <HttpsAccValue>0</HttpsAccValue>
              <DomesticValue>0.006666666666666667</DomesticValue>
              <HttpsAccDomesticValue>0</HttpsAccDomesticValue>
              <HttpsValue>0</HttpsValue>
        </DataModule>
  </QpsDataInterval>
  <DataInterval>300</DataInterval>
  <RequestId>C2416D6C-B10A-474C-8FE8-0F9EF7ACA674</RequestId>
  <EndTime>2019-11-30T05:40:00Z</EndTime>
  <StartTime>2019-11-30T05:33:00Z</StartTime>
</DescribeDomainQpsDataResponse>
```

`JSON`格式

```
{
	"QpsDataInterval": {
		"DataModule": [
			{
				"HttpsOverseasValue": 0,
				"TimeStamp": "2019-11-30T05:35:00Z",
				"HttpsAccOverseasValue": 0,
				"Value": "0.006666666666666667",
				"OverseasValue": 0,
				"HttpsDomesticValue": 0,
				"AccOverseasValue": 0,
				"AccValue": 2,
				"HttpsAccValue": 0,
				"DomesticValue": "0.006666666666666667",
				"HttpsAccDomesticValue": 0,
				"HttpsValue": 0
			}
		]
	},
	"DataInterval": 300,
	"RequestId": "C2416D6C-B10A-474C-8FE8-0F9EF7ACA674",
	"EndTime": "2019-11-30T05:40:00Z",
	"StartTime": "2019-11-30T05:33:00Z"
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

