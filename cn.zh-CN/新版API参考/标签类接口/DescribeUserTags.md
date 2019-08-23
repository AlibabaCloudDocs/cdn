# DescribeUserTags {#doc_api_Cdn_DescribeUserTags .reference}

调用DescribeUserTags查询用户标签。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeUserTags&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeUserTags|操作接口名，系统规定参数，取值：**DescribeUserTags**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|34AB41F1-04A5-496F-8C8D-634BDBE6A9FB|请求ID。

 |
|Tags| | |标签。

 |
|Key|String|env|标签键。

 |
|Value| |product|标签值。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com/?Action=DescribeUserTags
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUserTagsResponse>
	  <Tags>
		    <Key>env</Key>
		    <Value>product</Value>
		    <Value>pre</Value>
		    <Value>daily</Value>
	  </Tags>
	  <Tags>
		    <Key>region</Key>
		    <Value>hangzhou</Value>
	  </Tags>
	  <RequestId>34AB41F1-04A5-496F-8C8D-634BDBE6A9FB</RequestId>
</DescribeUserTagsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Tags":[
		{
			"Value":[
				"product",
				"pre",
				"daily"
			],
			"Key":"env"
		},
		{
			"Value":[
				"hangzhou"
			],
			"Key":"region"
		}
	],
	"RequestId":"34AB41F1-04A5-496F-8C8D-634BDBE6A9FB"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

