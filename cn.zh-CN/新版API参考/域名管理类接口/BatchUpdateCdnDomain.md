# BatchUpdateCdnDomain {#doc_api_Cdn_BatchUpdateCdnDomain .reference}

调用BatchUpdateCdnDomain批量更新加速域名。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=BatchUpdateCdnDomain&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchUpdateCdnDomain|操作接口名，系统规定参数。取值：**BatchUpdateCdnDomain**。

 |
|DomainName|String|是|example.com|需要接入CDN的域名。

 |
|ResourceGroupId|String|否|abc|资源组ID。

 |
|Sources|String|否|\[\{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80,"weight":"15"\}\]|回源地址列表。

 |
|TopLevelDomain|String|否|example.com|顶级接入域。

 |

Sources各字段含义如下所示。

|参数

|类型

|是否必选

|描述

|
|----|----|------|----|
|type

|String

|是

|源站类型，取值：ipaddr：IP源站；domain：域名源站；oss：OSS Bucket为源站；fc\_domain：函数计算源站。

|
|content

|String

|是

|回源地址，可以是IP或域名。

|
|port

|Integer

|否

|可以指定443、80端口，也可以自定义端口，默认值80。443走https回源。

|
|priority

|String

|否

|源站地址对应的优先级，支持20和30，默认20。20是主，30是备。

|
|weight

|String

|否

|回源权重，100以内，默认10。

|

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=BatchUpdateCdnDomain
&DomainName=example.com,example1.com
&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80}]
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchUpdateCdnDomainResponse>	
      <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
</BatchUpdateCdnDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|EntityNotExists.ResourceGroup|The resource group does not exist.|资源组不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

