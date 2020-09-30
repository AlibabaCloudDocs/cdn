# 获取WAF全量域名列表

调用DescribeCdnWafDomain获取WAF全量域名列表。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeCdnWafDomain&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnWafDomain|操作接口名，系统规定参数。取值：**DescribeCdnWafDomain**。 |
|RegionId|String|是|cn-hangzhou|WAF管控区域。取值：

 -   **cn-hangzhou**：WAF中国内地（大陆）管控区域。
-   **ap-southeast-1**：WAF非中国内地（大陆）管控区域。

 **说明：** 非中国内地（大陆）包含中国香港、中国澳门、中国台湾以及其他国家和地区。 |
|DomainName|String|否|example.com|待查询的域名。

 仅支持填写单个域名，详细见以下三种填写方式：

 -   填写精确域名：例如example.com，则查询example.com域名的配置信息。
-   填写关键字：例如example，则查询所有包含example的域名配置信息。
-   不填该参数：则默认返回所有开通了WAF的加速域名。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|OutPutDomains|Array of OutPutDomain| |加速域名信息。 |
|AclStatus|String|1|ACL状态。取值：

 -   **0**：关闭。
-   **1**：开通。 |
|CcStatus|String|1|CC状态。取值：

 -   **0**：关闭。
-   **1**：开通。 |
|Domain|String|example.com|域名信息。 |
|Status|String|1|WAF域名状态。取值：

 -   **1**：WAF域名创建成功或WAF域名有效。
-   **10**：WAF域名创建中。
-   **11**：WAF域名创建失败。 |
|WafStatus|String|1|WAF状态。取值：

 -   **0**：关闭。
-   **1**：开通。 |
|RequestId|String|CB1A380B-09F0-41BB-802B-72F8FD6DA2FE|请求ID。 |
|TotalCount|Integer|1|加速域名的数量。 |

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeCdnWafDomain
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeCdnWafDomainResponse>
  <TotalCount>1</TotalCount>
  <OutputDomains>
        <AclStatus>1</AclStatus>
        <CcStatus>1</CcStatus>
        <Domain>example.com</Domain>
        <Status>1</Status>
        <WafStatus>1</WafStatus>
  </OutputDomains>
  <RequestId>CB1A380B-09F0-41BB-802B-72F8FD6DA2FE</RequestId>
</DescribeCdnWafDomainResponse>
```

`JSON` 格式

```
{
  "TotalCount": 1,
  "OutputDomains": [
    {
      "AclStatus": 1,
      "CcStatus": 1,
      "Domain": "example.com",
      "Status": 1,
      "WafStatus": 1
    }
  ],
  "RequestId": "CB1A380B-09F0-41BB-802B-72F8FD6DA2FE"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cdn)查看更多错误码。

