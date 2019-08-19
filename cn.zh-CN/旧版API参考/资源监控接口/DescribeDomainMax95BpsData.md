# DescribeDomainMax95BpsData {#doc_api_Cdn_DescribeDomainMax95BpsData .reference}

调用DescribeDomainMax95BpsData接口获取加速域名95带宽峰值监控数据。

获取数据单位：bit/second。

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   支持批量域名查询，多个域名用逗号（半角）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainMax95BpsData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainMax95BpsData|操作接口名，系统规定参数。取值：**DescribeDomainMax95BpsData**。

 |
|DomainName|String|否|www.yourdomain.com|如果参数为空，默认返回所有加速域名合并后数据。

 -   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2017-12-22T08:00:00:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。

 |
|StartTime|String|否|2017-12-21T08:00:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mmZ。
-   最小数据粒度为5分钟， 不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|test.com|加速域名信息。

 |
|StartTime|String|2015-12-10T20:00Z|开始时间。

 |
|EndTime|String|2015-12-10T21:00Z|结束时间。

 |
|Max95Bps|String|16777590.28|95带宽峰值。

 |
|DomesticMax95Bps|String|16777590.28|国内95带宽峰值。

 |
|OverseasMax95Bps|String|0|海外95带宽峰值。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainMax95BpsData
&DomainName=example.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainMax95BpsDataResponse>
	  <DomainName>example.com</DomainName>
	  <RequestId>3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F</RequestId>
	  <StartTime>2015-12-10T20:00Z</StartTime>
	  <EndTime>2015-12-10T21:00Z</EndTime>
	  <Max95Bps>16777590.28</Max95Bps>
	  <DomesticMax95Bps>16777590.28</DomesticMax95Bps>
	  <OverseasMax95Bps>0</OverseasMax95Bps>
</DescribeDomainMax95BpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Max95Bps":"16777590.28",
	"DomesticMax95Bps":"16777590.28",
	"RequestId":"3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F",
	"OverseasMax95Bps":"0",
	"DomainName":"example.com",
	"EndTime":"2015-12-10T21:00Z",
	"StartTime":"2015-12-10T20:00Z"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|
|404|InvalidDomain.NotFound|The domain provided does not exist in our records.|域名不存在或不属于当前用户。请检查您填写的域名书写是否正确，或者域名是否在当前账号中，查看域名是否过期。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

