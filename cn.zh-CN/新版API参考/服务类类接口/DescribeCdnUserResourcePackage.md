# DescribeCdnUserResourcePackage {#doc_api_Cdn_DescribeCdnUserResourcePackage .reference}

调用DescribeCdnUserResourcePackage查询CDN用户当前流量包。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeCdnUserResourcePackage&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnUserResourcePackage|操作接口名，系统规定参数。取值：**DescribeCdnUserResourcePackage**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|84839536-2B7E-457D-9D8C-82E6C7D4E1A3|请求ID。

 |
|ResourcePackageInfos| | |由ResourcePackageInfo组成的数组格式。

 |
|CommodityCode|String|cdnflowbag|资源包商品code。

 |
|CurrCapacity|String|10995089554629|实例当前剩余容量。

 |
|DisplayName|String|CDN流量包（国内版）|套餐包名称。例如：CDN流量包（国内版）。

 |
|EndTime|String|2018-07-01T08:00:00Z|失效时间。

 |
|InitCapacity|String|536870912000|资源包总量。

 |
|InstanceId|String|FP-ilttxc23a|实例ID。

 |
|StartTime|String|2017-12-05T19:10:58Z|生效时间。

 |
|Status|String|valid|资源包状态。取值：

 -   **valid**：有效。
-   **closed**：无效。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?
&Action=DescribeCdnUserResourcePackage
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCdnUserResourcePackageResponse>
	  <ResourcePackageInfos>
		    <ResourcePackageInfo>
			      <Status>closed</Status>
			      <InstanceId>FP-mkqgwsyui</InstanceId>
			      <CommodityCode>cdnflowbag</CommodityCode>
			      <InitCapacity>10995116277760</InitCapacity>
			      <EndTime>2017-01-30T08:00:00Z</EndTime>
			      <StartTime>2016-01-30T03:40:06Z</StartTime>
			      <DisplayName>CDN流量包（国内版）</DisplayName>
			      <CurrCapacity>10995089554629</CurrCapacity>
		    </ResourcePackageInfo>
		    <ResourcePackageInfo>
			      <Status>valid</Status>
			      <InstanceId>FP-ilttxc23a</InstanceId>
			      <CommodityCode>cdnflowbag</CommodityCode>
			      <InitCapacity>536870912000</InitCapacity>
			      <EndTime>2018-07-01T08:00:00Z</EndTime>
			      <StartTime>2017-07-01T01:26:41Z</StartTime>
			      <DisplayName>CDN流量包（国内版）</DisplayName>
			      <CurrCapacity>0</CurrCapacity>
		    </ResourcePackageInfo>
		    <ResourcePackageInfo>
			      <Status>valid</Status>
			      <InstanceId>CDNHTTPSBAG-cn-v0h0dnlq4000m9</InstanceId>
			      <CommodityCode>cdnhttpsbag</CommodityCode>
			      <InitCapacity>10000000</InitCapacity>
			      <EndTime>2018-12-06T08:00:00Z</EndTime>
			      <StartTime>2017-12-05T19:10:58Z</StartTime>
			      <DisplayName>CDN HTTPS请求数资源包</DisplayName>
			      <CurrCapacity>9999645</CurrCapacity>
		    </ResourcePackageInfo>
	  </ResourcePackageInfos>
	  <RequestId>84839536-2B7E-457D-9D8C-82E6C7D4E1A3</RequestId>
</DescribeCdnUserResourcePackageResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"ResourcePackageInfos":{
		"ResourcePackageInfo":[
			{
				"Status":"closed",
				"CommodityCode":"cdnflowbag",
				"InstanceId":"FP-mkqgwsyui",
				"InitCapacity":"10995116277760",
				"EndTime":"2017-01-30T08:00:00Z",
				"StartTime":"2016-01-30T03:40:06Z",
				"DisplayName":"CDN流量包（国内版）",
				"CurrCapacity":"10995089554629"
			},
			{
				"Status":"valid",
				"CommodityCode":"cdnflowbag",
				"InstanceId":"FP-ilttxc23a",
				"InitCapacity":"536870912000",
				"EndTime":"2018-07-01T08:00:00Z",
				"StartTime":"2017-07-01T01:26:41Z",
				"DisplayName":"CDN流量包（国内版）",
				"CurrCapacity":"0"
			},
			{
				"Status":"valid",
				"CommodityCode":"cdnhttpsbag",
				"InstanceId":"CDNHTTPSBAG-cn-v0h0dnlq4000m9",
				"InitCapacity":"10000000",
				"EndTime":"2018-12-06T08:00:00Z",
				"StartTime":"2017-12-05T19:10:58Z",
				"DisplayName":"CDN HTTPS请求数资源包",
				"CurrCapacity":"9999645"
			}
		]
	},
	"RequestId":"84839536-2B7E-457D-9D8C-82E6C7D4E1A3"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

