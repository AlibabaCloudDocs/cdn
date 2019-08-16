# DescribeDomainTopUrlVisit {#doc_api_Cdn_DescribeDomainTopUrlVisit .reference}

调用DescribeDomainTopUrlVisit接口获取加速域名某天内的热门URL列表。

 **调用该接口前，请您注意：** 

-   不指定**StartTime**，默认读取前一天的数据。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainTopUrlVisit&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainTopUrlVisit|操作接口名，系统规定参数。取值：**DescribeDomainTopUrlVisit**。

 |
|DomainName|String|否|test.test.com|只支持一个域名，若参数为空，默认返回所有加速域名合并后数据 。

 |
|SortBy|String|否|pv|排序方式。

 -   支持**traf**和**pv**。
-   默认值：**pv**。

 |
|StartTime|String|否|2015-12-03|获取数据起始时间点，北京时间。

 格式为：YYYY-MM-DD。

 不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AllUrlList| | |全部热门URLlist。

 |
|Flow|String|460486880|流量。单位：byte

 |
|FlowProportion|Float|0.35|流量占比

 |
|UrlDetail|String|http://test.com/nn\_live/nn\_x64/a0.m3u8|完整的Url地址

 |
|VisitData|String|161673|访问次数

 |
|VisitProportion|Float|0.35|访问占比

 |
|DomainName|String|test.com|加速域名。

 |
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|请求ID。

 |
|StartTime|String|2015-12-03|查询指定日期。

 |
|Url200List| | |返回为2xx的Urllist。

 |
|Flow|String|460486880|流量。单位：byte。

 |
|FlowProportion|Float|0.35|流量占比。

 |
|UrlDetail|String|http://test.com/nn\_live/nn\_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8|完整的Url地址。

 |
|VisitData|String|161673|访问次数。

 |
|VisitProportion|Float|0.35|访问占比。

 |
|Url300List| | |返回为3xx的Urllist。

 |
|Flow|String|460486880|流量。单位：byte。

 |
|FlowProportion|Float|0.35|流量占比。

 |
|UrlDetail|String|http://test.com/nn\_live/nn\_x64/a0.m3u8|完整的Url地址。

 |
|VisitData|String|161673|次数。

 |
|VisitProportion|Float|0.35|访问占比。

 |
|Url400List| | |返回为4xx的Urllist。

 |
|Flow|String|460486880|流量。单位：byte。

 |
|FlowProportion|Float|0.35|流量占比。

 |
|UrlDetail|String|http://test.com/nn\_live/nn\_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8|完整的Url地址。

 |
|VisitData|String|1884|次数。

 |
|VisitProportion|Float|0.35|访问占比。

 |
|Url500List| | |返回为5xx的Urllist。

 |
|Flow|String|460486880|流量。单位：byte。

 |
|FlowProportion|Float|0.35|流量占比。

 |
|UrlDetail|String|http://test.com/nn\_live/nn\_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8|完整的Url地址。

 |
|VisitData|String|161673|次数。

 |
|VisitProportion|Float|0.35|访问占比。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainTopUrlVisit
&DomainName=example.com
&StartTime=2018-10-03T16:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainTopUrlVisitResponse>
	  <AllUrlList>
		    <UrlList>
			      <VisitData>161673</VisitData>
			      <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
		    <UrlList>
			      <VisitData>37</VisitData>
			      <UrlDetail>http://example1.com/nn_live/nn_x64/ZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
	  </AllUrlList>
	  <Url300List>
		    <UrlList>
			      <VisitData>161673</VisitData>
			      <UrlDetail>http://example3.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
		    <UrlList>
			      <VisitData>3</VisitData>
			      <UrlDetail>http://example4.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
	  </Url300List>
	  <Url400List>
		    <UrlList>
			      <VisitData>1884</VisitData>
			      <UrlDetail>http://example6.com/nn_live/nn_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
		    <UrlList>
			      <VisitData>1</VisitData>
			      <UrlDetail>http://example7.com/nn_live/nn_x64/aWQ9SEEwODgmpbmRleZPTE,/HNJSMPP360.ts</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
	  </Url400List>
	  <RequestId>64D28B53-5902-409B-94F6-FD46680144FE</RequestId>
	  <DomainName>example.com</DomainName>
	  <Url200List>
		    <UrlList>
			      <VisitData>161673</VisitData>
			      <UrlDetail>http://example8.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
		    <UrlList>
			      <VisitData>3</VisitData>
			      <UrlDetail>http://example9.com/nn_live/nn_x64/aWQ9SE5KU01QUDMlPTIwMTxMDk5ZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
	  </Url200List>
	  <StartTime>2018-10-03T16:00:00Z</StartTime>
	  <Url500List>
		    <UrlList>
			      <VisitData>161673</VisitData>
			      <UrlDetail>http://example10.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
		    <UrlList>
			      <VisitData>3</VisitData>
			      <UrlDetail>http://example11.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </UrlList>
	  </Url500List>
</DescribeDomainTopUrlVisitResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Url300List":{
		"UrlList":[
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"161673",
				"UrlDetail":"http://example3.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
				"FlowProportion":0.35
			},
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"3",
				"UrlDetail":"http://example4.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
				"FlowProportion":0.35
			}
		]
	},
	"AllUrlList":{
		"UrlList":[
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"161673",
				"UrlDetail":"http://example.com/nn_live/nn_x64/a0.m3u8",
				"FlowProportion":0.35
			},
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"37",
				"UrlDetail":"http://example1.com/nn_live/nn_x64/ZXg9MQ,,/HNJSMPP360.ts",
				"FlowProportion":0.35
			}
		]
	},
	"Url400List":{
		"UrlList":[
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"1884",
				"UrlDetail":"http://example6.com/nn_live/nn_x64/aWQ9SE5KU01QUhbGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8",
				"FlowProportion":0.35
			},
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"1",
				"UrlDetail":"http://example7.com/nn_live/nn_x64/aWQ9SEEwODgmpbmRleZPTE,/HNJSMPP360.ts",
				"FlowProportion":0.35
			}
		]
	},
	"RequestId":"64D28B53-5902-409B-94F6-FD46680144FE",
	"DomainName":"example.com",
	"Url200List":{
		"UrlList":[
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"161673",
				"UrlDetail":"http://example8.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcGNfbGl2ZQ,,/HNJSMPP360.m3u8",
				"FlowProportion":0.35
			},
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"3",
				"UrlDetail":"http://example9.com/nn_live/nn_x64/aWQ9SE5KU01QUDMlPTIwMTxMDk5ZXg9MQ,,/HNJSMPP360.ts",
				"FlowProportion":0.35
			}
		]
	},
	"StartTime":"2018-10-03T16:00:00Z",
	"Url500List":{
		"UrlList":[
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"161673",
				"UrlDetail":"http://example10.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
				"FlowProportion":0.35
			},
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"3",
				"UrlDetail":"http://example11.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
				"FlowProportion":0.35
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The specified value of parameter "StartTime" is not valid.|参数“StartTime”的值无效。|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidDomainName.ValueNotSupported|The specified value of parameter DomainName only support one or empty value.|参数DomainName可以为空或最多1个域名。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

