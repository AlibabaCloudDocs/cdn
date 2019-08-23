# DescribeTagResources {#doc_api_Cdn_DescribeTagResources .reference}

调用DescribeTagResources查询资源对应的标签。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeTagResources&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeTagResources|操作接口名，系统规定参数，取值：**DescribeTagResources**。

 |
|ResourceId.N|RepeatList|是|ResourceId.1|资源ID，CDN为域名，N的取值范围为**1**~**50**。

 |
|ResourceType|String|是|DOMAIN|固定值：**DOMAIN**。

 |
|RegionId|String|否|ch-hangzhou|地域ID。

 |
|Tag.N.Key|String|否|Tag.1.Key|标签键。N的取值范围为**1**~**20**。

 |
|Tag.N.Value|String|否|Tag.2.Value|标签值。N的取值范围为**1**~**20**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|34AB41F1-04A5-496F-8C8D-634BDBE6A9FB|请求ID。

 |
|TagResources| | |标签资源。

 |
|ResourceId|String|example.com|资源ID。

 |
|Tag| | |标签组合。

 |
|Key|String|env|标签键。

 |
|Value|String|product|标签值。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com/?Action=DescribeTagResources
&ResourceId.1=example.com
&ResourceType=DOMAIN
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeTagResources>
	  <TagResources>
		    <ResourceId>example.com</ResourceId>
		    <Tag>
			      <Value>product</Value>
			      <Key>env</Key>
		    </Tag>
	  </TagResources>
	  <RequestId>34AB41F1-04A5-496F-8C8D-634BDBE6A9FB</RequestId>
</DescribeTagResources>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TagResources":[
		{
			"ResourceId":"example.com",
			"Tag":[
				{
					"Value":"product",
					"Key":"env"
				}
			]
		}
	],
	"RequestId":"34AB41F1-04A5-496F-8C8D-634BDBE6A9FB"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

