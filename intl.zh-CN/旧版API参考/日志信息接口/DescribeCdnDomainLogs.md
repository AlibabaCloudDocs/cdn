# DescribeCdnDomainLogs {#doc_api_Cdn_DescribeCdnDomainLogs .reference}

调用DescribeCdnDomainLogs接口获取指定域名的原始访问日志的下载地址。

**说明：** 日志内容最长保留一年。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainLogs)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnDomainLogs|操作接口名，系统规定参数，取值：**DescribeCdnDomainLogs**。

 |
|DomainName|String|是|www.yourdomain.com|域名（只支持单个查询）

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|-   结束时间需大于起始时间。
-   起止时间和结束时间，间隔不超过一年。
-   获取日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|LogDay|String|否|2015-05-24|要获取日志日的天。

 -   格式yyyy-MM-dd。
-   **LogDay**与**StartTime**、**EndTime**指定其一即可。
-   默认值：当天

 |
|PageNumber|Long|否|2|取得第几页。

 取值范围：\>1的任意整数。

 |
|PageSize|Long|否|300|分页大小。

 -   最大值：1000
-   取值范围：1~1000之间的任意整数。
-   默认值：300

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取日志起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Long|1|返回数据的页码

 |
|PageSize|Long|100|整页大小

 |
|TotalCount|Long|3|总条数

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |
|DomainLogModel| | |日志模型

 |
|└DomainName|String|gc.ggter.com|域名

 |
|└DomainLogDetails| | |**DomainLogDetail**组成的数据

 |
|└LogPath|String|cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015\_05\_23/gc.ggter.com\_2015\_05\_23\_1100\_1200.gz?OSSAccessKeyId\\u003dxxxxxxx\\u0026Expires\\u003d1432539994\\u0026Signature\\u003d7Ly4ccKN3afzAGYyWDbxBcOcn2I%3D|日志路径

 |
|└StartTime|String|2017-12-21T08:00:00:00Z|开始时间开始时间

 |
|└EndTime|String|2017-12-22T08:00:00:00Z|结束时间结束时间

 |
|└LogSize|Long|257|日志大小

 |
|└LogName|String|gc.ggter.com\_2015\_05\_23\_1100\_1200.gz|日志名称

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeCdnDomainLogs
&DomainName=www.yourdomain.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>A94A4299-D87F-4D91-8068-5D4B4EA8DFAC</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidStartTime.Malformed</Code>
  <Message>Specified StartTime is malformed.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"Specified StartTime is malformed.",
	"RequestId":"A94A4299-D87F-4D91-8068-5D4B4EA8DFAC",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidStartTime.Malformed"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidLogDay.Malformed|LogDay is malformed. the expected format is yyyy-MM-dd|参数LogDay格式错误，请使用yyyy-MM-dd格式。|
|400|InvalidPageNumber.ValueNotSupported|The specified value of parameter PageNumber is not supported.|指定查询的当前页码参数值不合法。|
|400|InvalidPageSize.ValueNotSupported|The specified value of parameter PageSize is not supported.|指定查询的分页大小参数PageSize值不合法。|
|400|MissingParameter|The parameter StartTime miss.|参数StartTime缺失。|
|400|MissingParameter|The parameter EndTime miss.|参数EndTime缺失。|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|请检查时间设置是否正确，结束时间不能小于或等于开始时间。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

