# SetDomainServerCertificate {#doc_api_Cdn_SetDomainServerCertificate .reference}

调用SetDomainServerCertificate该接口用于设置某域名下证书功能是否启用及修改证书信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=SetDomainServerCertificate&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetDomainServerCertificate|操作接口名，系统规定参数。取值：**SetDomainServerCertificate**。

 |
|DomainName|String|是|www.yourdomain.com|指定证书所属加速域名，需属于https加速类型。

 |
|ServerCertificateStatus|String|是|on|HTTPS证书是否启用，取值：

 -   **on**：启用。
-   **off**：不启用。

 默认**off**。

 |
|CertName|String|否|myCert1|证书名称。

 |
|CertType|String|否|cas|证书类型：

 -   **upload**：上传证书。
-   **cas**：证书中心证书。
-   **free**：免费证书。

 |
|ForceSet|String|否|1|设置为1时，忽略证书名称重复的校验，覆盖原有同名证书信息。

 |
|PrivateKey|String|否|xxxxxxxx|私钥内容，不启用证书则无需输入，配置证书请输入私钥内容。

 |
|Region|String|否|cn-hangzhou|地区。

 |
|ServerCertificate|String|否|xxxxxx|安全证书内容，不启用证书则无需输入，配置证书请输入证书内容。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.comAction=SetDomainServerCertificate
&DomainName=test.com
&CertName=myCert1
&ServerCertificateStatus=on
&ServerCertificate=xxx
&PrivateKey=yyy
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetDomainServerCertificateResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</SetDomainServerCertificateResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Certificate.NotPermittedOff|Turn off certificate will change domain scheduling, please contact customer service|关闭证书将更改域调度，请与客服联系。|
|400|Certificate.SettedNotEffect|Certificate was successfully setted but does't take effect for protecting current service, please contact customer service|证书已成功安装但不保护当前服务生效，请联系客户服务|
|400|Certificate.NotFind|Not find the certificate info.|证书不存在。|
|400|Certificate.MissMatch|The certificate is not match the private key.|证书与私钥不匹配。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

