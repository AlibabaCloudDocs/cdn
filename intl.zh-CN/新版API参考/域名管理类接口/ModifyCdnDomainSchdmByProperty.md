# ModifyCdnDomainSchdmByProperty {#doc_api_Cdn_ModifyCdnDomainSchdmByProperty .reference}

调用ModifyCdnDomainSchdmByProperty修改加速域名。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=ModifyCdnDomainSchdmByProperty&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyCdnDomainSchdmByProperty|操作接口名，系统规定参数。取值：**ModifyCdnDomainSchdmByProperty**。

 |
|DomainName|String|是|example.com|需修改加速区域的域名。

 |
|Property|String|是|\{"coverage":"overseas"\}|调度域属性。\{"coverage":"overseas"\} 中coverage参数支持**domestic**、**overseas**、**global**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http(s)://cdn.aliyuncs.com/?Action=ModifyCdnDomainSchdmByProperty
&DomainName=example.com
&Property={"coverage":"overseas"}
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyCdnDomainSchdmByPropertyResponse>
	  <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
</ModifyCdnDomainSchdmByPropertyResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cdn)查看更多错误码。

