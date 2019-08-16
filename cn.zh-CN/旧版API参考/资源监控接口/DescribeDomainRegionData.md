# DescribeDomainRegionData {#doc_api_Cdn_DescribeDomainRegionData .reference}

调用DescribeDomainRegionData接口获取加速域名天粒度的用户区域分布数据统计。

 **调用该接口前，请您注意：** 

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRegionData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainRegionData|操作接口名，系统规定参数。取值：**DescribeDomainRegionData** 。

 |
|DomainName|String|否|test.test.com|需要查询的加速域名，只支持一个域名，不写代表所有。

 |
|EndTime|String|否|2016-03-13|结束时间需大于起始时间，北京时间。

 格式为：YYYY-MM-DD。

 |
|StartTime|String|否|2016-03-13|获取数据起始时间点，北京时间。

 格式为：YYYY-MM-DD。

 不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|86400|时间间隔。

 |
|DomainName|String|test.test.com|加速域名。

 |
|EndTime|String|2016-03-13|获取数据结束时间。

 |
|RequestId|String|2E5AD83F-BD7B-462E-8319-2E30E305519A|请求ID。

 |
|StartTime|String|2016-03-13|获取数据起始时间。

 |
|Value| | |value。

 |
|AvgObjectSize|String|800019.0|响应平均大小。单位：byte。

 |
|AvgResponseRate|String|154.3345765545624|平均响应速度。单位：byte/秒。

 |
|AvgResponseTime|String|5183.666666666667|平均响应时间。单位：毫秒。

 |
|Bps|String|380.9614285714286|带宽。

 |
|ByteHitRate|String|100.0|字节命中率，如返回90即为90%。

 |
|BytesProportion|String|0.003544181046236794|总流量占比，如返回90即为90%。

 |
|Proportion|String|0.01155980271270037|访问占比数据，如返回90即为90%。

 |
|Qps|String|5.9523809523809524E-5|每秒查询率。

 |
|Region|String|日本|地区信息。

 |
|RegionEname|String|japan|地区英文名称。

 |
|ReqErrRate|String|0.0|请求错误率，如返回90即为90%。

 |
|ReqHitRate|String|100.0|请求命中率，如返回0.5即为0.5%。

 |
|TotalBytes|String|2400057|总流量。

 |
|TotalQuery|String|3|总请求次数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainRegionData
&DomainName=example.com
&StartTime=2015-12-05T12:00:00Z
&EndTime=2015-12-07T12:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainRegionDataResponse>
	  <Value>
		    <RegionProportionData>
			      <Bps>380.9614285714286</Bps>
			      <Proportion>0.01155980271270037</Proportion>
			      <TotalBytes>2400057</TotalBytes>
			      <BytesProportion>0.003544181046236794</BytesProportion>
			      <TotalQuery>3</TotalQuery>
			      <RegionEname></RegionEname>
			      <Region>日本</Region>
			      <AvgResponseRate>154.3345765545624</AvgResponseRate>
			      <AvgObjectSize>800019.0</AvgObjectSize>
			      <Qps>5.9523809523809524E-5</Qps>
			      <AvgResponseTime>5183.666666666667</AvgResponseTime>
		    </RegionProportionData>
		    <RegionProportionData>
			      <Bps>25110.431412698414</Bps>
			      <Proportion>0.31211467324291</Proportion>
			      <TotalBytes>158195717</TotalBytes>
			      <BytesProportion>0.23360872886644055</BytesProportion>
			      <TotalQuery>81</TotalQuery>
			      <RegionEname>xizang</RegionEname>
			      <Region>西藏自治区</Region>
			      <AvgResponseRate>1397.1430909315718</AvgResponseRate>
			      <AvgObjectSize>1953033.5543209878</AvgObjectSize>
			      <Qps>0.0016071428571428571</Qps>
			      <AvgResponseTime>1397.8765432098764</AvgResponseTime>
		    </RegionProportionData>
		    <RegionProportionData>
			      <Bps>40343.86242857143</Bps>
			      <Proportion>0.33908754623921084</Proportion>
			      <TotalBytes>254166333</TotalBytes>
			      <BytesProportion>0.37532921137846464</BytesProportion>
			      <TotalQuery>88</TotalQuery>
			      <RegionEname>chongqing</RegionEname>
			      <Region>重庆市</Region>
			      <AvgResponseRate>787.8073097249128</AvgResponseRate>
			      <AvgObjectSize>2888253.7875</AvgObjectSize>
			      <Qps>0.001746031746031746</Qps>
			      <AvgResponseTime>3666.193181818182</AvgResponseTime>
		    </RegionProportionData>
	  </Value>
	  <DataInterval>86400</DataInterval>
	  <RequestId>2E5AD83F-BD7B-462E-8319-2E30E305519A</RequestId>
	  <DomainName>example1.com</DomainName>
	  <EndTime>2015-12-05T12:00:00Z</EndTime>
	  <StartTime>2015-12-07T12:00:00Z</StartTime>
</DescribeDomainRegionDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Value":{
		"RegionProportionData":[
			{
				"RegionEname":"",
				"TotalQuery":"3",
				"Region":"日本",
				"Bps":"380.9614285714286",
				"Proportion":"0.01155980271270037",
				"AvgResponseRate":"154.3345765545624",
				"AvgObjectSize":"800019.0",
				"Qps":"5.9523809523809524E-5",
				"AvgResponseTime":"5183.666666666667",
				"TotalBytes":"2400057",
				"BytesProportion":"0.003544181046236794"
			},
			{
				"RegionEname":"xizang",
				"TotalQuery":"81",
				"Region":"西藏自治区",
				"Bps":"25110.431412698414",
				"Proportion":"0.31211467324291",
				"AvgResponseRate":"1397.1430909315718",
				"AvgObjectSize":"1953033.5543209878",
				"Qps":"0.0016071428571428571",
				"AvgResponseTime":"1397.8765432098764",
				"TotalBytes":"158195717",
				"BytesProportion":"0.23360872886644055"
			},
			{
				"RegionEname":"chongqing",
				"TotalQuery":"88",
				"Region":"重庆市",
				"Bps":"40343.86242857143",
				"Proportion":"0.33908754623921084",
				"AvgResponseRate":"787.8073097249128",
				"AvgObjectSize":"2888253.7875",
				"Qps":"0.001746031746031746",
				"AvgResponseTime":"3666.193181818182",
				"TotalBytes":"254166333",
				"BytesProportion":"0.37532921137846464"
			}
		]
	},
	"DataInterval":"86400",
	"RequestId":"2E5AD83F-BD7B-462E-8319-2E30E305519A",
	"DomainName":"example1.com",
	"EndTime":"2015-12-05T12:00:00Z",
	"StartTime":"2015-12-07T12:00:00Z"
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

