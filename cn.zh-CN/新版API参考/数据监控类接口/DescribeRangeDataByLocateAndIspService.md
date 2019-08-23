# DescribeRangeDataByLocateAndIspService {#doc_api_Cdn_DescribeRangeDataByLocateAndIspService .reference}

调用DescribeRangeDataByLocateAndIspService获取加速域名的在某个时刻不同Locate和Isp上的带宽数据。

获取带宽数据单位：bit/second。

-   不支持批量域名查询。
-   时间精确到5分钟粒度。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeRangeDataByLocateAndIspService&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeRangeDataByLocateAndIspService|操作接口名，系统规定参数。取值：**DescribeRangeDataByLocateAndIspService**。

 |
|DomainNames|String|是|abc.com|要查询的域名，不能为空。

 |
|EndTime|String|是|2017-12-22T08:00:00:00Z|获取数据结束时间点。

 -   结束时间大于开始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mmZ。

 |
|StartTime|String|是|2017-12-22T07:00:00:00Z|获取数据开始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。

 |
|IspNames|String|否|unicom,telecom|需要查询目标Isp列表，用逗号（,）隔开，不能为空。

 ISP名通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得。

 |
|LocationNames|String|否|liaoning,guangxi|需要查询目标区域列表，用逗号（,）隔开，不能为空。

 Location名通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|JsonResult|String|\{"1505973300":\{"苏丹":\{"其他":\{"http\_codes":\{"000":0,"200":6,"400":0\},"rt":4183,"bandwidth":46639,"avg\_speed":7773,"pv":6,"hit\_rate":0.93,"request\_hit\_rate":0.66\}\}\}\}|json格式的返回结果。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeRangeDataByLocateAndIspService
&DomainNames=abc.com
&LocationNames=liaoning,guangxi
&IspNames=unicom,telecom
&startTime=2016-08-01T22:00Z
&EndTime=2016-08-02T22:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeRangeDataByLocateAndIspServiceResponse>
      <JsonResult>
			    <天津市>
				      <电信>
					        <bandwidth>7024681.44</bandwidth>
					        <pv>5819</pv>
					        <hit_rate>0</hit_rate>
					        <http_codes>			
					</http_codes>
					        <rt>0</rt>
				      </电信>
			    </天津市>
	  </JsonResult>
	  <RequestId>16A96B9A-F203-4EC5-8E43-CB92E68F4CD8</RequestId>
</DescribeRangeDataByLocateAndIspServiceResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8",
	"JsonResult":[
		{
			"1472659500":{
				"天津市":{
					"移动":{},
					"联通":{},
					"电信":{
						"http_codes":{
							"503":0,
							"504":0,
							"302":3,
							"200":5716,
							"304":72,
							"000":0,
							"206":11,
							"501":0,
							"502":0,
							"500":0,
							"408":0,
							"416":0,
							"405":0,
							"404":0,
							"400":1,
							"403":16,
							"412":0
						},
						"rt":0,
						"pv":5819,
						"hit_rate":0,
						"bandwidth":7024681.44
					}
				}
			},
			"1472659200":{
				"北京市":{
					"移动":{},
					"联通":{},
					"电信":{
						"http_codes":{
							"503":0,
							"504":0,
							"302":5,
							"200":5675,
							"304":45,
							"000":0,
							"206":5,
							"501":0,
							"502":0,
							"500":0,
							"408":0,
							"416":0,
							"405":0,
							"404":0,
							"400":1,
							"403":8,
							"412":0
						},
						"rt":0,
						"pv":5739,
						"hit_rate":0,
						"bandwidth":9889849.592
					}
				},
				"天津市":{
					"移动":{},
					"联通":{},
					"电信":{
						"http_codes":{
							"503":0,
							"504":0,
							"302":5,
							"200":5675,
							"304":45,
							"000":0,
							"206":5,
							"501":0,
							"502":0,
							"500":0,
							"408":0,
							"416":0,
							"405":0,
							"404":0,
							"400":1,
							"403":8,
							"412":0
						},
						"rt":0,
						"pv":5739,
						"hit_rate":0,
						"bandwidth":9889849.592
					}
				}
			}
		}
	]
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

