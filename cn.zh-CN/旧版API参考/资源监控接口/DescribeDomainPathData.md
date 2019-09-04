# DescribeDomainPathData {#doc_api_Cdn_DescribeDomainPathData .reference}

调用DescribeDomainPathData接口获取加速域名路径级别的5分钟维度的监控数据，该接口仅限白名单用户使用。

监控数据，包括流量和访问次数。

域名带宽峰值10G以上，或GC6、GC7客户，可以通过工单或者服务经理申请使用。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   不支持批量域名查询。
-   最多可获取最近30天的数据。
-   路径信息不支持模糊匹配。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainPathData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainPathData|操作接口名，系统规定参数。取值：**DescribeDomainPathData**。

 |
|DomainName|String|是|test.test.com|加速域名。

 |
|EndTime|String|否|2016-10-20T04:00:00Z|结束时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   起止时间和结束时间，间隔小于30天。
-   例如：2016-10-20T04:00:00Z。

 |
|PageNumber|Integer|否|1|页号，从1开始。

 |
|PageSize|Integer|否|20|每页大小，不超过1000。

 |
|Path|String|否|/path/|路径，以正斜线（/）开头。

 -   不填表示查询所有路径。
-   如果路径是目录，需要以正斜线（/）结尾。

 |
|StartTime|String|否|2016-10-20T04:00:00Z|开始时间,。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|时间间隔，单位：秒。

 |
|DomainName|String|test.test.com|加速域名。

 |
|EndTime|String|2017-09-30T17:00:00Z|结束时间。

 |
|PageNumber|Integer|1|当前页码，从1开始计数。

 |
|PageSize|Integer|20|页大小。

 |
|PathDataPerInterval| | |路径带宽数据列表。

 |
|UsageData| | |路径带宽数据列表。

 |
|Acc|Integer|10|访问次数。

 |
|Path|String|/path/|路径。

 |
|Time|String|2017-09-30T16:00:00Z|时间点。

 |
|Traffic|Integer|346|流量\(B\)。

 |
|RequestId|String|809A6F10-8238-4A49-BE00-4B2D6305686E|请求ID。

 |
|StartTime|String|2017-09-30T17:00:00Z|起始时间。

 |
|TotalCount|Integer|2|路径带宽数据条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?Action=DescribeDomainPathData
&DomainName=<DomainName>
&PageNumber=1
&PageSize=20
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainPathDataResponse>
      <TotalCount>2</TotalCount>
      <StartTime>2017-09-30T16:00:00Z</StartTime>
      <EndTime>2017-09-30T17:00:00Z</EndTime>
      <DataInterval>300</DataInterval>
      <PathDataPerInterval>
            <UsageData>
                  <Acc>10</Acc>
                  <Path>/path/</Path>
                  <Time>2017-09-30T16:00:00Z</Time>
                  <Traffic>346</Traffic>
            </UsageData>
            <UsageData>
                  <Time>2017-09-30T16:05:00Z</Time>
                  <Traffic>400</Traffic>
                  <Acc>12</Acc>
                  <Path>/path/</Path>
            </UsageData>
      </PathDataPerInterval>
      <PageNumber>1</PageNumber>
      <PageSize>20</PageSize>
</DescribeDomainPathDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":2,
	"DataInterval":300,
	"PageSize":20,
	"PathDataPerInterval":{
		"UsageData":[
			{
				"Time":"2017-09-30T16:00:00Z",
				"Acc":10,
				"Traffic":346,
				"Path":"/path/"
			},
			{
				"Time":"2017-09-30T16:05:00Z",
				"Acc":12,
				"Traffic":400,
				"Path":"/path/"
			}
		]
	},
	"EndTime":"2017-09-30T17:00:00Z",
	"StartTime":"2017-09-30T16:00:00Z"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

