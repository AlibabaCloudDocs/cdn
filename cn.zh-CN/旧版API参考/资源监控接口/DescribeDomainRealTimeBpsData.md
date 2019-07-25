# DescribeDomainRealTimeBpsData {#doc_api_Cdn_DescribeDomainRealTimeBpsData .reference}

调用DescribeDomainRealTimeBpsData接口获取域名1分钟粒度带宽数据。

-   可以查询7天内的数据，单次查询**StartTime**和**EndTime**跨度不能超过24小时。
-   如果**StartTime**和**EndTime**均未指定，默认返回当前时间起一小时内的数据.。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeBpsData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainRealTimeBpsData|操作接口名，系统规定参数。取值：**DescribeDomainRealTimeBpsData**。

 |
|DomainName|String|是|test.test.com|加速域名

 |
|EndTime|String|否|2016-10-20T04:00:00Z|结束时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z.2016-10-20T04:00:00Z。
-   不填默认查询从**StartTime**起一小时内的数据。

 |
|IspNameEn|String|否|telecom|运营商英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

 |
|StartTime|String|否|2016-10-20T04:00:00Z|起始时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从EndTime起一小时内的数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Data| | |返回数据

 |
|Bps|Float|16710625.733333332|带宽数据。单位：bit/second。

 |
|TimeStamp|String|2018-01-02T11:04:00Z|数据时间戳。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|RequestId|String|B49E6DDA-F413-422B-B58E-2FA23F286726|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeDomainRealTimeBpsData
&DomainName=test.test.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
	  <RequestId>0F2DBA09-A6B7-4D4E-85FE-9E27FC4FBEF3</RequestId>
	  <HostId>cdn.aliyuncs.com</HostId>
	  <Code>InvalidDomain.NotFound</Code>
	  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"0F2DBA09-A6B7-4D4E-85FE-9E27FC4FBEF3",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidTime.Malformed|Specified StartTime or EndTime is malformed.|开始时间或结束时间格式错误。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

