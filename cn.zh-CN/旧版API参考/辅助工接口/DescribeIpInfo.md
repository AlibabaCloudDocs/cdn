# DescribeIpInfo {#doc_api_Cdn_DescribeIpInfo .reference}

调用DescribeIpInfo接口验证指定的IP是否为阿里云CDN节点的IP地址。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeIpInfo&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeIpInfo|操作接口名，系统规定参数。取值：**DescribeIpInfo**。

 |
|IP|String|是|1.2.3.4|指定IP地址，不支持批量。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|1B1D0EE7-9559-489D-BC4E-279495EB8FB8|请求ID

 |
|CdnIp|String|True|是否属于阿里云CDN节点。

 -   **True**：属于
-   **False**：不属于

 |
|ISP|String|电信|所属运营商

 |
|Region|String|中国-贵州省-贵阳市|所属地区

 |
|IspEname|String|telecom|所属运营商英文名称

 |
|RegionEname|String|China-Guizhou-guiyang|所属地区英文名称

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeIpInfo
&IP=1.2.3.4
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RegionEname></RegionEname>
	  <Region></Region>
	  <IspEname></IspEname>
	  <RequestId>397D5620-DF32-441B-9553-2AADCABBA602</RequestId>
	  <ISP></ISP>
	  <CdnIp>False</CdnIp>
</APINAMEResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RegionEname":"",
	"Region":"",
	"IspEname":"",
	"RequestId":"397D5620-DF32-441B-9553-2AADCABBA602",
	"ISP":"",
	"CdnIp":"False"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidIP.ValueNotSupported|The specified value of parameter IP is not supported.|不支持该IP地址，请检查更新后重试。|
|400|MissingParameter|The specified value of parameter "IP" is not valid.|参数“IP”的值无效。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

