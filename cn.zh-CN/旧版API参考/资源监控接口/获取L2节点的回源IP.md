# 获取L2节点的回源IP

调用DescribeL2VipsByDomain查询L2节点vip列表。

**说明：**

-   按域名查询L2节点vip列表，配置白名单后才可以生效。
-   如果您的日峰值带宽大于**1 Gbps**，可[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)申请该接口的调用权限。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeL2VipsByDomain&type=RPC&version=2014-11-11)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeL2VipsByDomain|操作接口名，系统规定参数。取值：**DescribeL2VipsByDomain**。 |
|DomainName|String|是|www.yourdomain.com|加速域名，仅支持单个域名。

 **说明：** 需要配置白名单。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|xxxx.com|域名。 |
|Vips|List|"Vip": \[ "1.1.1.1/25", "2.2.2.2/25" \]|Vip列表。 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。 |

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeL2VipsByDomain
&DomainName=www.yourdomain.com
&<公共请求参数>
```

正常返回示例

`XML`格式

```
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

`JSON`格式

```
{
  "Vips": {
    "Vip": [
      "111.111.111.xxx/25",
      "112.112.112.xxx/25",
      "122.72.33.xxx/25"
    ]
  },
  "RequestId": "820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
  "DomainName": "example.com"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|The specified value of parameter "DomainName" can not be empty.|参数“DomainName”不能为空。|
|400|IllegalOperation|Illegal domain operate is not permitted.|非法操作。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

