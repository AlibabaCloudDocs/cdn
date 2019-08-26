# DescribeCdnCertificateDetail {#doc_api_Cdn_DescribeCdnCertificateDetail .reference}

调用DescribeCdnCertificateDetail查询cdn证书详细信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeCdnCertificateDetail&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnCertificateDetail|操作接口名，系统规定参数。取值：**DescribeCdnCertificateDetail**。

 |
|CertName|String|是|xxx|证书名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Cert|String|xxxxx|证书。

 |
|CertId|Long|881049|证书ID。

 |
|CertName|String|test|证书名。

 |
|Key|String|xxxxx|证书KEY。

 |
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeCdnCertificateDetail
&CertName=xxxx
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCdnCertificateDetailResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
	  <Cert>xxxxx</Cert>
	  <Key>xxxxx</Key>
	  <CertId>881049</CertId>
	  <CertName>test</CertName>
</DescribeCdnCertificateDetailResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"CertId":"881049",
	"Key":"xxxxx",
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9",
	"CertName":"test",
	"Cert":"xxxxx"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

