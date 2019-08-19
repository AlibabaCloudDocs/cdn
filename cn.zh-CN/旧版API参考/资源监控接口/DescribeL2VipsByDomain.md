# DescribeL2VipsByDomain {#doc_api_Cdn_DescribeL2VipsByDomain .reference}

调用DescribeL2VipsByDomain接口查询L2节点vip列表。

按域名查询L2节点vip列表，配置白名单后才可以生效。

**说明：** 

-   支持日峰值带宽为**1Gbps**以上的用户提工单申请该接口调用权限，请单击[立即申请](https://workorder.console.aliyun.com/console.htm?lang=#/ticket/add?productCode=cdn)。
-   使用场景介绍，请参见[回源的CDN节点的IP有哪些？](https://helpcdn.aliyun.com/knowledge_detail/40205.html)

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeL2VipsByDomain&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeL2VipsByDomain|操作接口名，系统规定参数。取值：**DescribeL2VipsByDomain**。

 |
|DomainName|String|是|www.yourdomain.com|域名。只支持单个域名，需加白名单。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|xxxx.com|域名。

 |
|Vips| |"Vip": \[ "1.1.1.1/25", "2.2.2.2/25" \]|Vip列表。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com?Action=DescribeL2VipsByDomain
&DomainName=www.yourdomain.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeL2VipsByDomainResponse>
	  <Vips>
		    <Vip>111.111.111.xxx/25</Vip>
		    <Vip>112.112.112.xxx/25</Vip>
		    <Vip>122.72.33.xxx/25</Vip>
	  </Vips>
	  <RequestId>820E7900-5CA9-4AEF-B0DD-20ED5F64BE55</RequestId>
	  <DomainName>example.com</DomainName>
</DescribeL2VipsByDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Vips":{
		"Vip":[
			"111.111.111.xxx/25",
			"112.112.112.xxx/25",
			"122.72.33.xxx/25"
		]
	},
	"RequestId":"820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
	"DomainName":"example.com"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The specified value of parameter "DomainName" can not be empty.|参数“DomainName”不能为空。|
|400|IllegalOperation|Illegal domain operate is not permitted.|非法操作。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

