# DescribeCdnService {#doc_api_Cdn_DescribeCdnService .reference}

调用DescribeCdnService查询CDN服务状态。包括：当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeCdnService&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnService|操作接口名，系统规定参数，取值：**DescribeCdnService**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|InternetChargeType|String|PayByTraffic|计费类型：

 -   **PayByTraffic**：流量。
-   **PayByBandwidth**：带宽峰值。

 |
|OpeningTime|String|2014-02-28T13:11:49Z|开通服务时间，ISO 8601时间格式。

 |
|ChangingChargeType|String|PayByTraffic|下次生效的计费类型：

 -   **PayByTraffic**：流量。
-   **PayByBandwidth**：带宽峰值。

 |
|ChangingAffectTime|String|2014-11-27T16:00:00Z|GMT时间。

 |
|OperationLocks| | |业务锁定状态，例如：欠费，安全等。

 |
|LockReason|String|financial|业务锁定的原因。

 |
|InstanceId|String|aliuid|实例ID。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?&Action=DescribeCdnService
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCdnServiceResponse>
	  <ChangingAffectTime>2014-11-27T16:00:00Z</ChangingAffectTime>
	  <ChangingChargeType>PayByBandwidth</ChangingChargeType>
	  <InternetChargeType>PayByTraffic</InternetChargeType>
	  <OpeningTime>2014-02-28T13:11:49Z</OpeningTime>
	  <OperationLocks></OperationLocks>
	  <RequestId>BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23</RequestId>
</DescribeCdnServiceResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"OpeningTime":"2014-02-28T13:11:49Z",
	"ChangingChargeType":"PayByBandwidth",
	"RequestId":"BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23",
	"ChangingAffectTime":"2014-11-27T16:00:00Z",
	"OperationLocks":{
		"LockReason":[]
	},
	"InternetChargeType":"PayByTraffic"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|UnsupportedParameter|There is unsupported parameters|不支持该参数，请您检查该参数是否正确。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

