# DescribeDomainHttpCodeData {#doc_api_Cdn_DescribeDomainHttpCodeData .reference}

调用DescribeDomainHttpCodeData接口获取加速域名最小5分钟粒度的HTTP返回码占比数据。

 **调用该接口前，请您注意：** 

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainHttpCodeData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainHttpCodeData|操作接口名，系统规定参数。取值：**DescribeDomainHttpCodeData** 。

 |
|DomainName|String|否|test.test.com|需要查询的加速域名，支持批量，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2015-11-30T05:40Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|Interval|String|否|300|查询数据的时间粒度。

 -   支持300, 3600, 14400, 28800和86400秒。
-   不传和传的值不支持时，使用默认值300秒 。

 |
|IspNameEn|String|否|unicom|运营商英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

 |
|StartTime|String|否|2015-11-30T05:33Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟。

 |
|TimeMerge|String|否|on|取值：

 -   **on**：默认值，每条记录的时间间隔会根据时间跨度做合并。
-   **off**：返回5分钟粒度数据，最大时间跨度为31天。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|时间间隔。

 |
|DomainName|String|test.test.com|域名。

 |
|EndTime|String|2015-11-30T05:40Z|结束时间。

 |
|HttpCodeData| | |数据。

 |
|TimeStamp|String|2015-11-30T05:30:00Z|时间戳。

 |
|Value| | |value。

 |
|Code|String|200|http返回码。

 |
|Count|String|300|总数。

 |
|Proportion|String|66.046511627907|占比使用数据。

 |
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|请求ID。

 |
|StartTime|String|2015-11-30T05:33Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainHttpCodeData
&DomainName=example1.com,example2.com
&StartTime=2015-11-30T05:33:00Z
&EndTime=2015-11-30T05:40:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainHttpCodeDataResponse>
	  <HttpCodeData>
		    <UsageData>
			      <TimeStamp>2015-11-30T05:40:00Z</TimeStamp>
			      <Value>
				        <CodeProportionData>
					          <Proportion>66.046511627907</Proportion>
					          <Code>200</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>4.72868217054264</Proportion>
					          <Code>206</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>0.155038759689922</Proportion>
					          <Code>302</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>0.62015503875969</Proportion>
					          <Code>304</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>28.4496124031008</Proportion>
					          <Code>500</Code>
				        </CodeProportionData>
			      </Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-30T05:35:00Z</TimeStamp>
			      <Value>
				        <CodeProportionData>
					          <Proportion>64.7822765469824</Proportion>
					          <Code>200</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>3.74331550802139</Proportion>
					          <Code>206</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>0.152788388082506</Proportion>
					          <Code>302</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>1.90985485103132</Proportion>
					          <Code>304</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>29.4117647058824</Proportion>
					          <Code>500</Code>
				        </CodeProportionData>
			      </Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-30T05:30:00Z</TimeStamp>
			      <Value>
				        <CodeProportionData>
					          <Proportion>67.1458998935037</Proportion>
					          <Code>200</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>12.6730564430245</Proportion>
					          <Code>206</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>0.053248136315229</Proportion>
					          <Code>302</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>0.958466453674121</Proportion>
					          <Code>304</Code>
				        </CodeProportionData>
				        <CodeProportionData>
					          <Proportion>19.1693290734824</Proportion>
					          <Code>500</Code>
				        </CodeProportionData>
			      </Value>
		    </UsageData>
	  </HttpCodeData>
	  <DataInterval>300</DataInterval>
	  <RequestId>BC858082-736F-4A25-867B-E5B67C85ACF7</RequestId>
	  <DomainName>example1.com,example2.com</DomainName>
	  <EndTime>2015-11-30T05:40:00Z</EndTime>
	  <StartTime>2015-11-30T05:33:00Z</StartTime>
</DescribeDomainHttpCodeDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"HttpCodeData":{
		"UsageData":[
			{
				"TimeStamp":"2015-11-30T05:40:00Z",
				"Value":{
					"CodeProportionData":[
						{
							"Proportion":"66.046511627907",
							"Code":"200"
						},
						{
							"Proportion":"4.72868217054264",
							"Code":"206"
						},
						{
							"Proportion":"0.155038759689922",
							"Code":"302"
						},
						{
							"Proportion":"0.62015503875969",
							"Code":"304"
						},
						{
							"Proportion":"28.4496124031008",
							"Code":"500"
						}
					]
				}
			},
			{
				"TimeStamp":"2015-11-30T05:35:00Z",
				"Value":{
					"CodeProportionData":[
						{
							"Proportion":"64.7822765469824",
							"Code":"200"
						},
						{
							"Proportion":"3.74331550802139",
							"Code":"206"
						},
						{
							"Proportion":"0.152788388082506",
							"Code":"302"
						},
						{
							"Proportion":"1.90985485103132",
							"Code":"304"
						},
						{
							"Proportion":"29.4117647058824",
							"Code":"500"
						}
					]
				}
			},
			{
				"TimeStamp":"2015-11-30T05:30:00Z",
				"Value":{
					"CodeProportionData":[
						{
							"Proportion":"67.1458998935037",
							"Code":"200"
						},
						{
							"Proportion":"12.6730564430245",
							"Code":"206"
						},
						{
							"Proportion":"0.053248136315229",
							"Code":"302"
						},
						{
							"Proportion":"0.958466453674121",
							"Code":"304"
						},
						{
							"Proportion":"19.1693290734824",
							"Code":"500"
						}
					]
				}
			}
		]
	},
	"DataInterval":"300",
	"RequestId":"BC858082-736F-4A25-867B-E5B67C85ACF7",
	"DomainName":"example1.com,example2.com",
	"EndTime":"2015-11-30T05:40:00Z",
	"StartTime":"2015-11-30T05:33:00Z"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

