# BatchStopCdnDomain {#doc_api_Cdn_BatchStopCdnDomain .reference}

调用BatchStopCdnDomain批量停用加速域名，将DomainStatus变更为Offline。

**说明：** 

-   停用该加速域名后，该条加速域名信息仍保留，针对加速域名的请求系统将做自动回源处理。
-   如果暂时不需要对某域名进行加速，推荐使用StopDomain接口，暂停域名加速效果。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=BatchStopCdnDomain&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchStopCdnDomain|操作接口名，系统规定参数，取值：**BatchStopCdnDomain**。

 |
|DomainNames|String|是|example.com|需要接入CDN的域名，多个用逗号（,）分隔。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|324AEFFF-308C-4DA7-8CD3-01B277B98F28|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=BatchStopCdnDomain
&DomainNames=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchStopCdnDomainResponse>
	  <RequestId>324AEFFF-308C-4DA7-8CD3-01B277B98F28</RequestId>
</BatchStopCdnDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"324AEFFF-308C-4DA7-8CD3-01B277B98F28"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

