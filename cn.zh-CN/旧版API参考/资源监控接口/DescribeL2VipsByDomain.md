# DescribeL2VipsByDomain {#doc_api_Cdn_DescribeL2VipsByDomain .reference}

调用DescribeL2VipsByDomain接口查询L2节点vip列表。

按域名查询L2节点vip列表，配置白名单后才可以生效。

**说明：** 

-   支持日峰值带宽为**1Gbps**以上的用户提工单申请该接口调用权限，请单击[立即申请](https://workorder.console.aliyun.com/console.htm?lang=#/ticket/add?productCode=cdn)。
-   使用场景介绍，请参见[回源的CDN节点的IP有哪些？](https://helpcdn.aliyun.com/knowledge_detail/40205.html)

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeL2VipsByDomain)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeL2VipsByDomain|操作接口名，系统规定参数。取值：**DescribeL2VipsByDomain**。

 |
|DomainName|String|是|www.yourdomain.com|域名。只支持单个域名，需加白名单。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|xxxx.com|域名

 |
|Vips| |"Vip": \[ "1.1.1.1/25", "2.2.2.2/25" \]|Vip列表

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

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
<APINAMEResponse>
  <RequestId>CC6986CB-7A85-4094-B1E1-D65A9AAB8A4E</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"CC6986CB-7A85-4094-B1E1-D65A9AAB8A4E",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The specified value of parameter "DomainName" can not be empty.|参数“DomainName”不能为空。|
|400|IllegalOperation|Illegal domain operate is not permitted.|非法操作。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)

