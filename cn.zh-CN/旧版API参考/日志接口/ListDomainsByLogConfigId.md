# ListDomainsByLogConfigId {#doc_api_Cdn_ListDomainsByLogConfigId .reference}

调用ListDomainsByLogConfigId接口查询应用某自定义日志格式的所有域名列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=ListDomainsByLogConfigId&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ListDomainsByLogConfigId|操作接口名，系统规定参数，取值：**ListDomainsByLogConfigId**。

 |
|ConfigId|String|是|123|自定义配置ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Domains| |\[ "abc.com", "a.b.c.com" \]|域名列表。

 |
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?Action=ListDomainsByLogConfigId
&ConfigId=9732E117-8A37-49FD-A36F-ABBB87556CA7
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ListDomainsByLogConfigIdResponse>
	  <RequestId>9732E117-8A37-49FD-A36F-ABBB87556CA7</RequestId>
	  <Domains>
		    <Domain>example1.com</Domain>
		    <Domain>example.com</Domain>
	  </Domains>
</ListDomainsByLogConfigIdResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"9732E117-8A37-49FD-A36F-ABBB87556CA7",
	"Domains":{
		"Domain":[
			"example1.com",
			"example.com"
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

