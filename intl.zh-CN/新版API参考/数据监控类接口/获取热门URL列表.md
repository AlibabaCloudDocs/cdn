# 获取热门URL列表

调用DescribeDomainTopUrlVisit获取加速域名某个指定时间段内的热门URL列表（TOP100）。

**说明：**

-   如果您不指定StartTime和EndTime，该接口默认读取过去24小时的数据；指定StartTime和EndTime时，按指定的起止时间查询。
-   支持获取最近90天的数据。
-   该接口只支持查询一个域名或当前账户下所有域名。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTopUrlVisit&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainTopUrlVisit|操作接口名，系统规定参数。取值：**DescribeDomainTopUrlVisit**。 |
|DomainName|String|是|example.com|待查询的域名。 |
|StartTime|String|否|2019-10-04T00:00:00Z|开始获取数据的时间点。日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 查询某天的数据，建议传参格式为yyyy-MM-ddT16:00:00Z。 |
|EndTime|String|否|2019-10-04T16:00:00Z|获取数据结束时间点。日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 **说明：** 结束时间需大于开始时间，并且结束时间和开始时间相差不超过7天。 |
|SortBy|String|否|pv|排序方式，默认值为**pv**。取值：

 -   **traf**：流量。
-   **pv**：访问量。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|AllUrlList|Array of UrlList| |全部热门URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量。单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|完整的URL地址。 |
|VisitData|String|161673|访问次数。 |
|VisitProportion|Float|0.35|访问占比。 |
|DomainName|String|example.com|加速域名。 |
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|请求ID。 |
|StartTime|String|2019-10-03T16:00:00Z|查询指定日期。 |
|Url200List|Array of UrlList| |返回为2xx的URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量。单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8|完整的URL地址。 |
|VisitData|String|161673|访问次数。 |
|VisitProportion|Float|0.35|访问占比。 |
|Url300List|Array of UrlList| |返回为3xx的URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量。单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|完整的URL地址。 |
|VisitData|String|161673|次数。 |
|VisitProportion|Float|0.35|访问占比。 |
|Url400List|Array of UrlList| |返回为4xx的URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量。单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8|完整的URL地址。 |
|VisitData|String|1884|次数。 |
|VisitProportion|Float|0.35|访问占比。 |
|Url500List|Array of UrlList| |返回为5xx的URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量。单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8|完整的URL地址。 |
|VisitData|String|161673|次数。 |
|VisitProportion|Float|0.35|访问占比。 |

## 示例

请求示例

```
http://cdn.aliyuncs.com?Action=DescribeDomainTopUrlVisit
&DomainName=example.com
&StartTime=2019-10-04T00:00:00Z
&EndTime=2019-10-04T16:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDomainTopUrlVisitResponse>
  <Url300List>
</Url300List>
  <AllUrlList>
        <UrlList>
              <Flow>9304</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>2</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
        <UrlList>
              <Flow>3986</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
        <UrlList>
              <Flow>784</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
  </AllUrlList>
  <Url400List>
        <UrlList>
              <Flow>3986</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
        <UrlList>
              <Flow>784</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
  </Url400List>
  <RequestId>8E7A2ABF-1BB0-4E46-AE3E-58DB3151080C</RequestId>
  <DomainName>example.com</DomainName>
  <Url200List>
        <UrlList>
              <Flow>9304</Flow>
              <VisitProportion>0</VisitProportion>
              <VisitData>2</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <FlowProportion>0</FlowProportion>
        </UrlList>
  </Url200List>
  <StartTime>2019-10-04T00:00:00Z</StartTime>
  <Url500List>
</Url500List>
</DescribeDomainTopUrlVisitResponse>
```

`JSON` 格式

```
{
	"Url300List": {
		"UrlList": []
	},
	"AllUrlList": {
		"UrlList": [
			{
				"Flow": 9304,
				"VisitProportion": 0,
				"VisitData": 2,
				"UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
				"FlowProportion": 0
			},
			{
				"Flow": 3986,
				"VisitProportion": 0,
				"VisitData": 1,
				"UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
				"FlowProportion": 0
			},
			{
				"Flow": 784,
				"VisitProportion": 0,
				"VisitData": 1,
				"UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
				"FlowProportion": 0
			}
		]
	},
	"Url400List": {
		"UrlList": [
			{
				"Flow": 3986,
				"VisitProportion": 0,
				"VisitData": 1,
				"UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
				"FlowProportion": 0
			},
			{
				"Flow": 784,
				"VisitProportion": 0,
				"VisitData": 1,
				"UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
				"FlowProportion": 0
			}
		]
	},
	"RequestId": "8E7A2ABF-1BB0-4E46-AE3E-58DB3151080C",
	"DomainName": "example.com",
	"Url200List": {
		"UrlList": [
			{
				"Flow": 9304,
				"VisitProportion": 0,
				"VisitData": 2,
				"UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
				"FlowProportion": 0
			}
		]
	},
	"StartTime": "2019-10-04T00:00:00Z",
	"Url500List": {
		"UrlList": []
	}
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cdn)查看更多错误码。

