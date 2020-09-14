# 获取CDN证书的详细信息

调用DescribeCdnCertificateDetail查询CDN证书详细信息。

单用户调用频率：20次/秒。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeCdnCertificateDetail&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnCertificateDetail|操作接口名，系统规定参数。取值：**DescribeCdnCertificateDetail**。 |
|CertName|String|是|cert-15480655xxxx|证书名称，仅支持查询单个。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Cert|String|-----BEGIN CERTIFICATE-----\\nMIIFzDCCBLSgAwIBxxxx|证书。 |
|CertId|Long|881049|证书ID。 |
|CertName|String|cert-15480655xxxx|证书名称。 |
|Key|String|xxxx|证书KEY。 |
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。 |

## 示例

请求示例

```
http://cdn.aliyuncs.com?Action=DescribeCdnCertificateDetail
&CertName=cert-15480655xxxx
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeCdnCertificateDetailResponse>
  <CertId>881049</CertId>
  <RequestId>34D625D3-E316-460C-B87D-85BB5AD8AEAD</RequestId>
  <CertName>cert-15480655xxxx</CertName>
  <Cert>-----BEGIN CERTIFICATE-----
MIIFzDCCBLSgAwIBxxxx</Cert>
  <Key>xxxx</Key>
</DescribeCdnCertificateDetailResponse>
```

`JSON` 格式

```
{
	"CertId": 881049,
	"RequestId": "34D625D3-E316-460C-B87D-85BB5AD8AEAD",
	"CertName": "cert-15480655xxxx",
	"Cert": "-----BEGIN CERTIFICATE-----\nMIIFzDCCBLSgAwIBxxxx",
    "Key":"xxxx"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cdn)查看更多错误码。

