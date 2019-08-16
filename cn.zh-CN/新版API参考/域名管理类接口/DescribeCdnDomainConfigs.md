# DescribeCdnDomainConfigs {#doc_api_Cdn_DescribeCdnDomainConfigs .reference}

调用DescribeCdnDomainConfigs查询域名配置，一次可查询多个功能配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainConfigs&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnDomainConfigs|操作接口名，系统规定参数，取值：**DescribeCdnDomainConfigs**。

 |
|DomainName|String|是|example.com|加速域名。

 |
|FunctionNames|String|否|aliauth|功能列表名称，用逗号（,）分隔。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainConfigs| | |域名配置。

 |
|ConfigId|String|6295|配置id。

 |
|FunctionArgs| | |各个function。

 |
|ArgName|String|auth\_type|配置名称。

 |
|ArgValue|String|req\_auth|配置值。

 |
|FunctionName|String|aliauth|function名称。

 |
|Status|String|success|状态，包括**success**、**testing**、**failed**、**configuring**。

 |
|RequestId|String|C80705BF-0F76-41FA-BAD1-5B59296A4E59|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com/?Action=DescribeCdnDomainConfigs
&DomainName=www.xxx.org.cn
&FunctionNames=aliauth
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCdnDomainConfigsResponse>
	  <RequestId>C80705BF-0F76-41FA-BAD1-5B59296A4E59</RequestId>
	  <DomainConfigs>
		    <DomainConfig>
			      <Status>success</Status>
			      <FunctionArgs>
				        <FunctionArg>
					          <ArgName>auth_type</ArgName>
					          <ArgValue>req_auth</ArgValue>
				        </FunctionArg>
				        <FunctionArg>
					          <ArgName>ali_auth_dual</ArgName>
					          <ArgValue>on</ArgValue>
				        </FunctionArg>
			      </FunctionArgs>
			      <ConfigId>6295</ConfigId>
			      <FunctionName>aliauth</FunctionName>
		    </DomainConfig>
	  </DomainConfigs>
</DescribeCdnDomainConfigsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C80705BF-0F76-41FA-BAD1-5B59296A4E59",
	"DomainConfigs":{
		"DomainConfig":[
			{
				"Status":"success",
				"FunctionArgs":{
					"FunctionArg":[
						{
							"ArgName":"auth_type",
							"ArgValue":"req_auth"
						},
						{
							"ArgName":"ali_auth_dual",
							"ArgValue":"on"
						}
					]
				},
				"FunctionName":"aliauth",
				"ConfigId":6295
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|此方法不支持。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

