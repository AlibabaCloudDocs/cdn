# 设置加速域名的HTTPS证书

调用SetCdnDomainCSRCertificate设置指定域名下的HTTPS证书。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetCdnDomainCSRCertificate&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetCdnDomainCSRCertificate|操作接口名，系统规定参数。取值：**SetCdnDomainCSRCertificate**。 |
|DomainName|String|是|example.com|要设置的加速域名，需属于https加速类型。 |
|ServerCertificate|String|是|xxx|证书内容。该证书必须是通过[CreateCdnCertificateSigningRequest](~~144478~~)接口创建的Csr对应的签名证书，内部必须是pem格式的证书，base64编码后再通过encodeURIComponent。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。 |

## 示例

请求示例

```
http://cdn.aliyuncs.com?Action=SetCdnDomainCSRCertificate
&DomainName=example.com
&ServerCertificate=xxx
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<SetCdnDomainCSRCertificateResponse>
  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</SetCdnDomainCSRCertificateResponse>
```

`JSON` 格式

```
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Certificate.MissingParameter|You must specify the Certificate parameter.|Certificate参数缺失|
|400|Certificate.EncodeError|An error occurred while encoding the certificate.|证书编码错误|
|400|Certificate.DecodeError|An error occurred while decoding the certificate.|证书解码失败|
|400|Certificate.FormatError|The format of the certificate is invalid.|证书格式错误|
|400|Certificate.MissMatch|The certificate does not match the domain.|证书和域名不匹配|
|400|Certificate.NoPrivateKey|The private key of the certificate does not exist.|私钥不存在|
|500|Internal.ForbidError|You cannot modify the configurations when some features of the domain are in a canary deployment.|该域名有功能在灰度，不能进行变更|
|500|Internal.ConfigError|An error occurred while configuring the certificate.|配置接口调用失败|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

