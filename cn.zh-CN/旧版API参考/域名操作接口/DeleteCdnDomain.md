# DeleteCdnDomain {#doc_api_Cdn_DeleteCdnDomain .reference}

调用DeleteCdnDomain接口删除已添加的加速域名。

**说明：** 

-   请慎重操作（建议在进行域名删除前到域名解析服务商处恢复域名A记录），以免导致删除操作后此域名不可访问。
-   **DeleteCdnDomain**调用成功后将删除本条加速域名的全部相关记录，对于仅需要暂停使用该加速域名，推荐**StopCdnDomain**接口。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DeleteCdnDomain&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteCdnDomain|操作接口名，系统规定参数。取值：**DeleteCdnDomain**。

 |
|DomainName|String|是|www.yourdomain.com|要删除的CDN的域名。

 |
|ResourceGroupId|String|否|your resourceGroupId|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DeleteCdnDomain
&DomainName=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteCdnDomainResponse>
    <RequestId>4785C948-233E-45FD-BA27-1C2119BBC2CC</RequestId>
</DeleteCdnDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"94E3559F-7B6A-4A5E-AFFD-44E2A208A249"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidDomainName.Malformed|The specific value of parameter DomainName is malformed.|域名不存在或不属于当前用户。请检查您填写的域名书写是否正确，或者域名是否在当前账号中，查看域名是否过期。|
|400|InvalidParameter|Delete live region parameters have error.|删除直播区域异常。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

