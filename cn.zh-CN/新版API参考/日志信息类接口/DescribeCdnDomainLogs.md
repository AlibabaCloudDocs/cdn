# DescribeCdnDomainLogs {#doc_api_Cdn_DescribeCdnDomainLogs .reference}

调用DescribeCdnDomainLogs获取指定域名的原始访问日志的下载地址。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据。
-   同时指定StartTime和EndTime时，按指定的起止时间查询。
-   支持下载最近一个月的日志内容。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainLogs&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|DomainName|String|是|www.yourdomain.com|域名，只支持单个查询。

 |
|Action|String|否|DescribeCdnDomainLogs|操作接口名，系统规定参数，取值：**DescribeCdnDomainLogs**。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|获取日志结束时间。结束时间需大于起始时间，起止时间和结束时间，间隔不超过一年。

 获取日期格式按照ISO8601表示法，并使用UTC时间。

 |
|PageNumber|Long|否|2|取得第几页，取值范围为：大于**1**的任意整数。

 |
|PageSize|Long|否|300|分页大小，默认**300**，最大**1000**，取值：**1**~**1000**。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取日志起始时间点。

 日期格式按照ISO8601表示法，并使用UTC时间。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainLogDetails| | |DomainLogDetail组成的数据。

 |
|DomainName|String|example.com|域名。

 |
|LogCount|Long|10|本页返回的总条数。

 |
|LogInfos| | |LogInfoDetail组成的数据。

 |
|EndTime|String|2015-05-23T14:00:00Z|结束时间。

 |
|LogName|String|gc.ggter.com\_2015\_05\_23\_2100\_2200.gz|日志名称。

 |
|LogPath|String|cdnlog.cn-hangzhou.xxx|日志路径。

 |
|LogSize|Long|258|日志大小。

 |
|StartTime|String|2015-05-23T13:00:00Z|开始时间。

 |
|PageInfos| | |PageInfoDetail组成的数据。

 |
|PageIndex|Long|1|返回数据的页码。

 |
|PageSize|Long|1|整页大小。

 |
|Total|Long|3|总条数。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?Action=DescribeCdnDomainLogs
&DomainName=www.yourdomain.com
&StartTime=2017-12-21T08:00:00:00Z
&EndTime=2017-12-22T08:00:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCdnDomainLogsResponse>
	  <DomainLogModel>
		    <DomainName>gc.ggter.com</DomainName>
		    <PageNumber>1</PageNumber>
		    <TotalCount>3</TotalCount>
		    <PageSize>100</PageSize>
		    <DomainLogDetails>
			      <DomainLogDetail>
				        <EndTime>2015-05-23T04:00:00Z</EndTime>
				        <LogName>gc.ggter.com_2015_05_23_1100_1200.gz</LogName>
				        <LogPath>cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.xxx.com/2015_05_23/gc.ggter.com_2015_05_23_1100_1200.gz?OSSAccessKeyId=3xmgf7JheOfxxxxx&amp;Expires=1432539994&amp;Signature=7Ly4ccKN3afzAGYyWDbxBcOcnxxxx</LogPath>
				        <LogSize>257</LogSize>
				        <StartTime>2015-05-23T03:00:00Z</StartTime>
			      </DomainLogDetail>
			      <DomainLogDetail>
				        <EndTime>2015-05-23T08:00:00Z</EndTime>
				        <LogName>gc.ggter.com_2015_05_23_1500_1600.gz</LogName>
				        <LogPath>cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.xxx.com/2015_05_23/gc.ggter.com_2015_05_23_1500_1600.gz?OSSAccessKeyId=3xmgf7JheOfxxxxx&amp;Expires=1432539994&amp;Signature=dMv7VqPqZHXVbKPmorGIvylC66xxxx</LogPath>
				        <LogSize>194</LogSize>
				        <StartTime>2015-05-23T07:00:00Z</StartTime>
			      </DomainLogDetail>
			      <DomainLogDetail>
				        <EndTime>2015-05-23T14:00:00Z</EndTime>
				        <LogName>gc.ggter.com_2015_05_23_2100_2200.gz</LogName>
				        <LogPath>cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015_05_23/gc.ggter.com_2015_05_23_2100_2200.gz?OSSAccessKeyId=3xmgf7JheOfxxxx&amp;Expires=1432539994&amp;Signature=FpSQCbgNcxCBYIxKVoKC8mxxxx</LogPath>
				        <LogSize>258</LogSize>
				        <StartTime>2015-05-23T13:00:00Z</StartTime>
			      </DomainLogDetail>
		    </DomainLogDetails>
	  </DomainLogModel>
	  <RequestId>1805F349-0A2B-41D9-B4AD-33632AFC27F1</RequestId>
</DescribeCdnDomainLogsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DomainLogModel":{
		"PageNumber":1,
		"TotalCount":3,
		"PageSize":100,
		"DomainLogDetails":{
			"DomainLogDetail":[
				{
					"LogName":"gc.ggter.com_2015_05_23_1100_1200.gz",
					"LogPath":"cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.xxx.com/2015_05_23/gc.ggter.com_2015_05_23_1100_1200.gz?OSSAccessKeyId=3xmgf7JheOfOTUTf&Expires=1432539994&Signature=7Ly4ccKN3afzAGYyWDbxBcOcnxxxx",
					"EndTime":"2015-05-23T04:00:00Z",
					"StartTime":"2015-05-23T03:00:00Z",
					"LogSize":257
				},
				{
					"LogName":"gc.ggter.com_2015_05_23_1500_1600.gz",
					"LogPath":"cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.xxx.com/2015_05_23/gc.ggter.com_2015_05_23_1500_1600.gz?OSSAccessKeyId=3xmgf7JheOfOxxxx&Expires=1432539994&Signature=dMv7VqPqZHXVbKPmorGIvylC6xxxx",
					"EndTime":"2015-05-23T08:00:00Z",
					"StartTime":"2015-05-23T07:00:00Z",
					"LogSize":194
				},
				{
					"LogName":"gc.ggter.com_2015_05_23_2100_2200.gz",
					"LogPath":"cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015_05_23/gc.ggter.com_2015_05_23_2100_2200.gz?OSSAccessKeyId=3xmgf7JheOfOxxxx&Expires=1432539994&Signature=FpSQCbgNcxCBYIxKVoKC8mGxxxx",
					"EndTime":"2015-05-23T14:00:00Z",
					"StartTime":"2015-05-23T13:00:00Z",
					"LogSize":258
				}
			]
		},
		"DomainName":"example.com"
	},
	"RequestId":"1805F349-0A2B-41D9-B4AD-33632AFC27F1"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

