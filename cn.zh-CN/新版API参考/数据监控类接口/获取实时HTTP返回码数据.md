# 获取实时HTTP返回码数据

调用DescribeDomainRealTimeHttpCodeData获取加速域名1分钟粒度HTTP返回码的总数和占比数据。

**说明：**

-   支持获取最近7天的数据。每次查询时**StartTime**和**EndTime**的跨度不能超过24小时。
-   如果您未指定**StartTime**和**EndTime**，该接口默认返回当前时间起一小时内的数据；指定**StartTime**和**EndTime**，返回起止时间的数据。
-   单用户调用频率为10次/秒。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeHttpCodeData&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDomainRealTimeHttpCodeData|系统规定参数。取值：**DescribeDomainRealTimeHttpCodeData**。 |
|DomainName|String|是|example1.com,example2.com|加速域名，多个域名用英文逗号（,）分隔。

 **说明：** 一次最多可以传500个域名。 |
|StartTime|String|否|2019-11-30T05:39:00Z|获取数据的起始时间点。

 日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。 |
|EndTime|String|否|2019-11-30T05:40:00Z|获取数据的结束时间点。

 日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 **说明：** 结束时间需大于起始时间。 |
|IspNameEn|String|否|unicom|运营商英文名。通过[DescribeCdnRegionAndIsp](~~91077~~)获得，默认查询所有运营商。 |
|LocationNameEn|String|否|beijing|地域英文名。通过[DescribeCdnRegionAndIsp](~~91077~~)获得，默认查询所有地域。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|60|每条记录的时间间隔，单位：秒。 |
|DomainName|String|example1.com,example2.com|加速域名信息。 |
|EndTime|String|2019-11-29T05:42:00Z|结束时间。 |
|RealTimeHttpCodeData|Array of UsageData| |每个时间间隔的HTTP返回码占比数据。 |
|UsageData| | | |
|TimeStamp|String|2019-11-29T05:39:00Z|时间片起始时刻。 |
|Value|Array of RealTimeCodeProportionData| |各返回码占比使用数据列表。 |
|RealTimeCodeProportionData| | | |
|Code|String|500|HTTP返回码。 |
|Count|String|100|总数。 |
|Proportion|String|28.4496124031008|占比使用数据。 |
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|请求ID。 |
|StartTime|String|2019-11-29T05:39:00Z|开始时间。 |

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeHttpCodeData
&DomainName=example1.com,example2.com
&StartTime=2019-11-29T05:39:00Z
&EndTime=2019-11-29T05:42:00Z
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeDomainRealTimeHttpCodeDataResponse>
  <DataInterval>60</DataInterval>
  <RequestId>99E690FC-86A3-4533-8F61-CF9E319141A4</RequestId>
  <DomainName>example1.com,example2.com</DomainName>
  <EndTime>2019-11-29T05:42:00Z</EndTime>
  <StartTime>2019-11-29T05:39:00Z</StartTime>
  <RealTimeHttpCodeData>
        <UsageData>
              <TimeStamp>2019-11-29T05:39:00Z</TimeStamp>
              <Value>
                    <RealTimeCodeProportionData>
                          <Count>2</Count>
                          <Proportion>100</Proportion>
                          <Code>200</Code>
                    </RealTimeCodeProportionData>
              </Value>
        </UsageData>
        <UsageData>
              <TimeStamp>2019-11-29T05:40:00Z</TimeStamp>
              <Value>
                    <RealTimeCodeProportionData>
                          <Count>1</Count>
                          <Proportion>50</Proportion>
                          <Code>200</Code>
                    </RealTimeCodeProportionData>
                    <RealTimeCodeProportionData>
                          <Count>1</Count>
                          <Proportion>50</Proportion>
                          <Code>304</Code>
                    </RealTimeCodeProportionData>
              </Value>
        </UsageData>
        <UsageData>
              <TimeStamp>2019-11-29T05:41:00Z</TimeStamp>
              <Value>
                    <RealTimeCodeProportionData>
                          <Count>11</Count>
                          <Proportion>91.66666666666666</Proportion>
                          <Code>200</Code>
                    </RealTimeCodeProportionData>
                    <RealTimeCodeProportionData>
                          <Count>1</Count>
                          <Proportion>8.333333333333332</Proportion>
                          <Code>206</Code>
                    </RealTimeCodeProportionData>
              </Value>
        </UsageData>
  </RealTimeHttpCodeData>
</DescribeDomainRealTimeHttpCodeDataResponse>
```

`JSON`格式

```
{
	"DataInterval": 60,
	"RequestId": "99E690FC-86A3-4533-8F61-CF9E319141A4",
	"DomainName": "example1.com,example2.com",
	"EndTime": "2019-11-29T05:42:00Z",
	"StartTime": "2019-11-29T05:39:00Z",
	"RealTimeHttpCodeData": {
		"UsageData": [
			{
				"TimeStamp": "2019-11-29T05:39:00Z",
				"Value": {
					"RealTimeCodeProportionData": [
						{
							"Count": 2,
							"Proportion": 100,
							"Code": "200"
						}
					]
				}
			},
			{
				"TimeStamp": "2019-11-29T05:40:00Z",
				"Value": {
					"RealTimeCodeProportionData": [
						{
							"Count": 1,
							"Proportion": 50,
							"Code": "200"
						},
						{
							"Count": 1,
							"Proportion": 50,
							"Code": "304"
						}
					]
				}
			},
			{
				"TimeStamp": "2019-11-29T05:41:00Z",
				"Value": {
					"RealTimeCodeProportionData": [
						{
							"Count": 11,
							"Proportion": "91.66666666666666",
							"Code": "200"
						},
						{
							"Count": 1,
							"Proportion": "8.333333333333332",
							"Code": "206"
						}
					]
				}
			}
		]
	}
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

